# Security Analysis

This lab focused on AWS Identity and Access Management (IAM), one of the most critical security components in AWS environments.

---

# Principle of Least Privilege

One of the main security concepts observed in this lab was the Principle of Least Privilege (PoLP).

Users, groups, and roles should only receive the minimum permissions necessary to perform their tasks.

Overprivileged accounts significantly increase security risks.

---

# IAM Users and Roles

IAM allows the creation of:

- Users
- Groups
- Roles
- Policies

Improperly configured IAM entities may lead to privilege escalation or unauthorized access to AWS resources.

Access control is one of the core pillars of cloud security.

---

# Policy Misconfiguration Risks

IAM policies define what actions are allowed or denied.

Misconfigured policies may accidentally expose sensitive resources or administrative permissions.

Careful policy auditing is essential to maintain secure environments.

---

# Root Account Security

AWS root accounts possess unrestricted permissions.

Using the root account for daily administrative tasks is considered a major security risk.

Best practices include:

- MFA enablement
- Minimal root account usage
- Delegating permissions through IAM users and roles

---

# Multi-Factor Authentication (MFA)

MFA provides an additional security layer for AWS accounts.

Even if credentials become compromised, MFA helps prevent unauthorized access.

This is one of the most important security controls in cloud environments.

---

# Identity-Based Security

IAM demonstrates how cloud security heavily depends on identity and permission management.

Strong authentication and authorization policies are essential to protecting cloud infrastructure.

---

# Final Security Considerations

This lab provided practical exposure to cloud identity security concepts related to:

- Least privilege
- Access control
- IAM policies
- MFA
- Privilege management
- Authentication security
