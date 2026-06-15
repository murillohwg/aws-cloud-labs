# Security Analysis

This lab introduced important security concepts related to Amazon EC2 instances and cloud infrastructure management.

---

# Security Groups

Security Groups act as virtual firewalls for EC2 instances.

They control inbound and outbound traffic and represent one of the primary network security mechanisms in AWS.

Improperly configured Security Groups may expose services directly to the internet.

Restricting unnecessary ports is an important security best practice.

---

# SSH Exposure Risks

EC2 instances commonly use SSH for remote administration.

Exposing SSH (port 22) publicly increases the attack surface and may lead to:

- Brute-force attacks
- Credential abuse
- Unauthorized access attempts

Using restricted IP ranges and strong authentication methods improves security.

---

# Key Pair Management

AWS EC2 uses key pairs for authentication.

Private keys must be securely stored because unauthorized access to the private key may compromise the instance entirely.

Key management is a critical operational security responsibility.

---

# Public IP Exposure

Instances configured with public IP addresses become internet-accessible.

This demonstrates the importance of:

- Network segmentation
- Firewall configuration
- Access control policies

Publicly exposed services should always be monitored and hardened.

---

# Instance Visibility and Monitoring

EC2 instances provide direct visibility into:

- Operating systems
- Networking
- Resource utilization
- Security configurations

Monitoring solutions such as CloudWatch improve visibility and incident detection.

---

# Shared Responsibility Model

This lab also demonstrated AWS's Shared Responsibility Model.

AWS secures the cloud infrastructure itself, while customers remain responsible for:

- Instance configuration
- Access control
- Operating system security
- Application hardening

---

# Final Security Considerations

This lab provided practical exposure to infrastructure security concepts related to:

- Security Groups
- SSH access
- Public network exposure
- Authentication mechanisms
- Infrastructure monitoring
- Cloud access control
