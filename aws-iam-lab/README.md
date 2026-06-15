![AWS](https://img.shields.io/badge/AWS-IAM-orange)
![Cloud Security](https://img.shields.io/badge/Cloud-Security-blue)
![EC2](https://img.shields.io/badge/Amazon-EC2-yellow)
![S3](https://img.shields.io/badge/Amazon-S3-green)
![Status](https://img.shields.io/badge/Status-Completed-success)
## Evidence

### IAM Groups Configuration
Demonstrating the IAM groups created for role separation:
- S3-Support
- EC2-Support
- EC2-Admin

![IAM Groups](images/01-iam-groups.png)

---

### User Assignment – S3 Support
Adding `user-1` to the `S3-Support` group.

![User1 S3](images/02-add-user1-s3-support.png)

---

### User Assignment – EC2 Support
Adding `user-2` to the `EC2-Support` group.

![User2 EC2](images/03-add-user2-ec2-support.png)

---

### User Assignment – EC2 Admin
Adding `user-3` to the `EC2-Admin` group.

![User3 Admin](images/04-add-user3-ec2-admin.png)

---

### Access Restriction Validation – user-1
`user-1` was unable to stop EC2 instances due to insufficient permissions.

![Denied User1](images/05-user1-stop-instance-denied.png)

---

### Access Restriction Validation – user-2
`user-2` had read-only EC2 permissions and could not stop instances.

![Denied User2](images/06-user2-stop-instance-denied.png)

---

### Administrative Access Validation – user-3
`user-3` successfully stopped the EC2 instance due to administrative permissions.

![Success User3](images/07-user3-stop-instance-success.png)

## Skills Demonstrated

- AWS IAM administration
- Role-Based Access Control (RBAC)
- IAM group management
- Managed and inline policies
- Permission validation
- EC2 access control
- S3 read-only access configuration
- Principle of Least Privilege

---

## Related Projects

- [AWS VPC + EC2(WebServer) Lab](https://github.com/murillohwg/aws-vpc-ec2-webserver-lab/tree/main)
