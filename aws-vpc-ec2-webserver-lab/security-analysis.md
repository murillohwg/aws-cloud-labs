# Security Analysis

This lab demonstrated important cloud networking and infrastructure security concepts using Amazon VPC and EC2.

---

# Network Segmentation

Amazon VPC enables logical network isolation inside AWS environments.

Subnet separation improves security by limiting exposure between different infrastructure components.

Network segmentation is a fundamental cloud security practice.

---

# Public and Private Exposure

The lab demonstrated how EC2 instances may become publicly accessible depending on:

- Route tables
- Internet Gateway configuration
- Public IP assignment
- Security Group rules

Misconfigurations in these components may unintentionally expose services to the internet.

---

# Security Groups and Traffic Filtering

Security Groups were used to control network traffic reaching the EC2 instance.

Only required ports should be exposed publicly.

Unnecessary open ports increase the infrastructure attack surface.

---

# Internet Gateway Risks

The Internet Gateway enables communication between the VPC and the internet.

Although necessary for public web servers, improper exposure increases security risks.

Public-facing environments require careful monitoring and hardening.

---

# Web Server Exposure

Hosting a web server publicly introduces several security considerations, including:

- Web application vulnerabilities
- Unauthorized access attempts
- Port scanning
- Service enumeration

Public infrastructure should always follow security hardening practices.

---

# Infrastructure Visibility

This lab provided visibility into how AWS networking components interact, including:

- VPCs
- Subnets
- Route tables
- Security Groups
- Internet Gateways

Understanding these relationships is critical for secure cloud architecture design.

---

# Final Security Considerations

This lab provided practical exposure to cloud networking security concepts related to:

- Network segmentation
- Public infrastructure exposure
- Traffic filtering
- Web server security
- Internet-facing architectures
- AWS network isolation
