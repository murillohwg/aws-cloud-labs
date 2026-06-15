# Security Analysis

During this lab, several important cloud security concepts could be observed in practice.

## Security Groups

Elastic Beanstalk automatically created security groups to control inbound and outbound traffic for the EC2 instances hosting the application.

Port 80 was exposed to allow HTTP access to the deployed web application.

---

## Managed Infrastructure

One important security advantage of Elastic Beanstalk is the reduction of manual infrastructure configuration.

AWS automatically handled:

- Environment provisioning
- Load balancing
- Auto Scaling
- Instance configuration

This reduces the probability of infrastructure misconfiguration.

---

## Load Balancer Exposure

The application was publicly accessible through an Elastic Beanstalk domain endpoint.

This demonstrates how internet-facing applications are exposed through AWS-managed load balancing infrastructure.

---

## EC2 Visibility

Although Elastic Beanstalk abstracts infrastructure management, the underlying EC2 instances remain fully accessible for inspection, monitoring, and auditing.

This provides operational flexibility while maintaining managed deployment capabilities.

---

## Scalability and Availability

The environment included an Auto Scaling Group configured to dynamically adjust the number of EC2 instances according to traffic demand.

This improves:

- Availability
- Fault tolerance
- Service resilience

---
