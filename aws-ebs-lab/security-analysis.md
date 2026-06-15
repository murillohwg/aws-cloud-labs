# Security Analysis — AWS EBS Snapshot & Restore Lab

## Overview

This document provides a brief security analysis of the AWS EBS Snapshot & Restore lab environment and highlights important cloud security considerations related to Amazon EBS volumes, snapshots, and EC2 instances.

---

# Security Considerations

## 1. Availability Zone Restrictions

Amazon EBS volumes can only be attached to EC2 instances located in the same Availability Zone (AZ).

This design improves:
- performance
- low latency access
- infrastructure isolation

However, it also introduces operational constraints during disaster recovery scenarios.

---

## 2. Snapshot Persistence

Amazon EBS snapshots are stored independently from the original volume.

Even after deleting:
- files
- partitions
- mounted volumes

the snapshot still preserves the original data state.

### Security Impact

Snapshots may unintentionally retain:
- sensitive files
- credentials
- logs
- deleted data

Improper snapshot management may lead to data exposure risks.

---

## 3. Principle of Least Privilege (PoLP)

Permissions related to:
- `ec2:CreateSnapshot`
- `ec2:CreateVolume`
- `ec2:AttachVolume`

should be restricted using IAM policies.

Excessive permissions could allow:
- unauthorized data recovery
- snapshot exfiltration
- unauthorized volume cloning

---

## 4. Data Exposure Risks

If a snapshot is accidentally shared publicly or with another AWS account, sensitive data may become accessible.

### Recommended Controls

- Restrict snapshot sharing
- Encrypt EBS volumes
- Enable snapshot encryption
- Monitor IAM activity with CloudTrail

---

## 5. Linux Mount Persistence

The lab configured automatic mounting using `/etc/fstab`.

While useful operationally, incorrect configurations may:
- prevent system boot
- mount unintended devices
- expose sensitive directories

### Recommendation

Use UUID-based mounting instead of raw device names.

Example:

```bash
UUID=<volume-uuid> /mnt/data-store ext3 defaults,noatime 1 2
```

---

## 6. Session Manager Security Benefits

Using AWS Systems Manager Session Manager provides several advantages over traditional SSH access:

- No public SSH port exposure
- No SSH key management
- Centralized session logging
- IAM-based access control

This reduces attack surface significantly.

---

# Security Best Practices

## Recommended Best Practices

- Encrypt EBS volumes by default
- Encrypt snapshots
- Use IAM least privilege policies
- Enable AWS CloudTrail logging
- Avoid public snapshot sharing
- Rotate credentials regularly
- Use Session Manager instead of SSH whenever possible
- Regularly audit unused snapshots and volumes

---

# Conclusion

This lab demonstrated not only how Amazon EBS storage works operationally, but also highlighted important security concepts involving:

- storage persistence
- backup recovery
- snapshot exposure risks
- access management
- filesystem configuration

Understanding these concepts is essential for secure cloud infrastructure management in AWS environments.
