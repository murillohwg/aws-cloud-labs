![AWS](https://img.shields.io/badge/AWS-EC2-orange?logo=amazonaws)
![Linux](https://img.shields.io/badge/Linux-Amazon%20Linux%202023-yellow?logo=linux)
![Monitoring](https://img.shields.io/badge/Monitoring-CloudWatch-blue)
![Security](https://img.shields.io/badge/Security-Groups-red)
![EBS](https://img.shields.io/badge/Storage-EBS-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

# AWS EC2 Hands-On Lab

Practical hands-on lab using Amazon EC2 on AWS Academy focused on:
- EC2 deployment
- Security Groups
- User Data automation
- Monitoring
- EBS resizing
- Instance protection
- Basic troubleshooting

---

# Technologies & Services

- Amazon EC2
- Amazon EBS
- Amazon CloudWatch
- Security Groups
- Amazon Linux 2023

---

# Skills Demonstrated

- EC2 instance deployment
- Linux web server provisioning
- Apache HTTP Server configuration
- Security Group management
- HTTP traffic configuration
- EC2 monitoring
- EBS volume resizing
- Instance type resizing
- Stop protection configuration
- AWS troubleshooting

---

# Task 1 — Launch EC2 Instance

An EC2 instance named `Web Server` was launched using Amazon Linux 2023.

## Configuration

| Setting | Value |
|---|---|
| Region | us-east-1 |
| Instance Type | t2.micro |
| AMI | Amazon Linux 2023 |
| Key Pair | vockey |
| VPC | Lab VPC |

![Editing Instance](images/1-edit-instance.png)

---

## Security Group

A custom Security Group was created:

- Name: `Web Server security group`
- Initial inbound rules: none

![Security Group](images/2-edit-instance.png)

This intentionally blocked inbound HTTP traffic.

---

## User Data Script

The following bootstrap script was used during instance launch:

![Editing User Data](images/3-edit-instance.png)

```bash
#!/bin/bash
dnf install -y httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```

## Purpose

The script:
- installs Apache
- starts the service
- enables startup on boot
- creates a simple HTML page

---

# Task 2 — Monitor Your Instance

The EC2 instance was monitored using built-in AWS monitoring tools.

## Status Checks

The following checks were verified:

- System reachability
- Instance reachability

Both checks passed successfully.

---

## CloudWatch Metrics

The Monitoring tab was used to observe:
- CPU utilization
- Network traffic
- EC2 metrics

This demonstrated integration between EC2 and Amazon CloudWatch.

---

## System Logs

The instance system logs were accessed through:

```text
Actions → Monitor and troubleshoot → Get system log
```

The logs confirmed that the Apache HTTP package was installed successfully from the User Data script.

---

## Instance Screenshot

The EC2 screenshot feature was tested through:

```text
Actions → Monitor and troubleshoot → Get instance screenshot
```

This feature can help diagnose:
- boot issues
- unreachable instances
- graphical console problems

---

# Task 3 — Configure Security Group and Access Web Server

Initially, the web server could not be accessed from the browser.

## Cause

The Security Group contained no inbound HTTP rule.

As a result:
- port 80 traffic was blocked.

---

## Solution

An inbound HTTP rule was added:

| Type | Protocol | Port | Source |
|---|---|---|---|
| HTTP | TCP | 80 | 0.0.0.0/0 |

---

## Security Group Modification

![Edit Inbound Rules](images/edit-inbound-rules.png)

---

## Result

After updating the Security Group rules, the web server became accessible from the browser.

![Web Server Running](images/4-webserver-is-running.png)

---

# Task 4 — Resize Instance and EBS Volume

The EC2 instance was resized to simulate infrastructure scaling.

---

## Stop Instance

The instance was stopped before resizing operations.

### Instance Stop (t2.micro)

![Stop Instance](images/stop-webserver-micro2.png)

---

## Change Instance Type

The instance type was changed:

```text
t2.micro → t2.small
```

### Instance Resize Process

![Resize Step 1](images/1-edit-instance.png)

![Resize Step 2](images/2-edit-instance.png)

![Resize Step 3](images/3-edit-instance.png)

---

## Enable Stop Protection

Stop protection was enabled to prevent accidental shutdowns.

### Enable Stop Protection

![Enable Stop Protection](images/changed-stop-protection(enable).png)

---

## Stop Protection Error

When attempting to stop the protected instance, AWS blocked the action.

![Stop Protection Error](images/error-cantbestop-protectionrules.png)

---

## Disable Stop Protection

Stop protection was then disabled.

![Disable Stop Protection](images/change-stop-instance-protection.png)

---

## Stop Instance Successfully

The instance could then be stopped successfully.

![Stopped Instance](images/stop-webserver-small2.png)

---

## Resize EBS Volume

The root EBS volume was resized:

```text
8 GiB → 10 GiB
```

### Storage Resize

![Storage Modified](images/storage-modified.png)

---

# Task 5 — Explore EC2 Limits

AWS Service Quotas were explored to understand EC2 limits.

The lab demonstrated:
- regional EC2 quotas
- On-Demand instance limitations
- service quota visibility

---

# Key Concepts Learned

## EC2
- Instance lifecycle
- Compute resizing
- User Data automation

## Monitoring
- CloudWatch metrics
- Status checks
- System logs

## Security
- Security Groups
- HTTP traffic filtering
- Inbound rules

## Storage
- EBS volumes
- Persistent storage
- Volume resizing

## Protection Mechanisms
- Stop protection
- Termination protection

---

# Final Notes

This lab provided practical exposure to core AWS infrastructure administration concepts using Amazon EC2.

The activities simulated real-world cloud administration tasks commonly performed by:
- Cloud Engineers
- DevOps Engineers
- Infrastructure Analysts
- Cloud Security Professionals
