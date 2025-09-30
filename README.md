```markdown
# ALB-Ansible & S3 Hosting Project

This project demonstrates two distinct methods for deploying a static website on AWS:
1.  A highly available, automated infrastructure using an Application Load Balancer (ALB), EC2 instances, and Ansible.
2.  A serverless, cost-effective approach using Amazon S3 Static Website Hosting.

 Architecture Overview

Method 1: ALB & EC2 with Ansible
- AWS Application Load Balancer (ALB):** `TechSolutions-ALB` routes HTTP traffic.
- EC2 Web Servers: Two instances (`Web-server-1`, `Web-server-2`) in an Auto Scaling Group across two AZs.
- nsible Playbook: Automates the installation of NGINX and deployment of the `index.html` file.
- Endpoint: `http://TechSolutions-ALB-1898000649.eu-west-1.elb.amazonaws.com`

Method 2: S3 Static Website Hosting
- Amazon S3  Bucket: `techsolutions-s3-bucket` stores the `index.html` file.
- S3 Website Hosting: The bucket is configured for static website hosting with a public read policy.
- Endpoint:  `http://techsolutions-s3-bucket.s3-website-eu-west-1.amazonaws.com`

Project Files

- `NginixDeploy.yml` - The Ansible playbook that configures EC2 servers.
- `inventory.ini` - Ansible inventory file.
- `index.html` - The source code for the "TechSolutions" website.

Live Demos

Both deployments are live and serve the identical "TechSolutions" website:

- 🔧 EC2 & Ansible Deployment: [http://TechSolutions-ALB-1898000649.eu-west-1.elb.amazonaws.com](http://TechSolutions-ALB-1898000649.eu-west-1.elb.amazonaws.com)
- ☁️ S3 Static Hosting Deployment: [http://techsolutions-s3-bucket.s3-website-eu-west-1.amazonaws.com](http://techsolutions-s3-bucket.s3-website-eu-west-1.amazonaws.com) *(Note: URL may vary slightly)*

## Deployment Comparison

| Aspect | ALB + EC2 + Ansible | S3 Static Hosting |
| :--- | :--- | :--- |
| Complexity | High | Low |
| Management| Manual (Automated by Ansible) | Fully Managed by AWS |
| Cost | Higher (EC2 & ALB charges) | Lower (Storage & Requests) |
| Scalability | Manual scaling required | Automatic & infinite |
| Use Case | Dynamic applications | Pure static sites |

Purpose

This project was designed to compare and contrast two fundamental hosting patterns on AWS, highlighting the trade-offs between control/ flexibility (EC2) and simplicity/cost (S3).

---
```
