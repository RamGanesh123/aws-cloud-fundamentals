# Amazon Web Services (AWS) – Beginner Friendly Professional Guide

This guide is designed to give **a clear, at-a-glance understanding of AWS** for beginners, while remaining **formal, structured, and industry‑grade**. It includes:

* Top **25 AWS services** (what they do + when to use them)
* **Important AWS URLs & documentation**
* **AWS CLI installation** (Windows / macOS / Linux)
* Clear **mental models** and **conceptual diagrams** (described for GitHub usage)

---

## 1. What is AWS? (Big Picture)

**Amazon Web Services (AWS)** is a cloud platform that provides **on‑demand computing resources** such as servers, storage, databases, networking, security, and AI—without owning physical hardware.

**Core Idea:**

> *You rent IT infrastructure instead of buying it.*

**Simple Flow:**

```
User → AWS Cloud → Compute / Storage / Network → Secure & Scale → Pay as You Go
```

---

## 2. AWS Global Infrastructure (Mental Model)

* **Region** → Physical geographic area (e.g., us-east-1)
* **Availability Zone (AZ)** → One or more isolated data centers inside a region
* **Edge Location** → Used by CloudFront for low‑latency delivery

**Conceptual Image:**

> World map → Regions → AZ blocks → Edge nodes

Docs:

* [https://aws.amazon.com/about-aws/global-infrastructure/](https://aws.amazon.com/about-aws/global-infrastructure/)

---

## 3. Top 25 AWS Services (Beginner-Friendly)

### 3.1 Compute Services

| Service               | What It Does                 | When to Use                                  |
| --------------------- | ---------------------------- | -------------------------------------------- |
| **EC2**               | Virtual servers in the cloud | Run applications, websites, backend services |
| **Lambda**            | Serverless functions         | Event‑driven tasks, automation, APIs         |
| **Elastic Beanstalk** | Managed app deployment       | Deploy apps without managing servers         |
| **ECS**               | Container orchestration      | Run Docker containers                        |
| **EKS**               | Managed Kubernetes           | Kubernetes workloads                         |

Docs:

* EC2: [https://docs.aws.amazon.com/ec2/](https://docs.aws.amazon.com/ec2/)
* Lambda: [https://docs.aws.amazon.com/lambda/](https://docs.aws.amazon.com/lambda/)

---

### 3.2 Storage Services

| Service     | What It Does          | When to Use                      |
| ----------- | --------------------- | -------------------------------- |
| **S3**      | Object storage        | Images, backups, static websites |
| **EBS**     | Block storage for EC2 | Persistent disk for servers      |
| **EFS**     | File system storage   | Shared storage across EC2        |
| **Glacier** | Archival storage      | Long‑term backups                |

Docs:

* S3: [https://docs.aws.amazon.com/s3/](https://docs.aws.amazon.com/s3/)

---

### 3.3 Database Services

| Service         | Type                   | Use Case                    |
| --------------- | ---------------------- | --------------------------- |
| **RDS**         | Relational DB          | MySQL, PostgreSQL apps      |
| **Aurora**      | High‑performance RDBMS | Enterprise workloads        |
| **DynamoDB**    | NoSQL                  | Serverless, high scale apps |
| **ElastiCache** | In‑memory cache        | Speed up applications       |

Docs:

* RDS: [https://docs.aws.amazon.com/rds/](https://docs.aws.amazon.com/rds/)

---

### 3.4 Networking & Content Delivery

| Service        | Purpose                       |
| -------------- | ----------------------------- |
| **VPC**        | Private cloud network         |
| **Route 53**   | DNS service                   |
| **CloudFront** | CDN for fast content delivery |
| **ELB / ALB**  | Load balancing                |

Docs:

* VPC: [https://docs.aws.amazon.com/vpc/](https://docs.aws.amazon.com/vpc/)

---

### 3.5 Security & Identity

| Service     | Purpose                   |
| ----------- | ------------------------- |
| **IAM**     | Users, roles, permissions |
| **Cognito** | User authentication       |
| **KMS**     | Encryption keys           |
| **WAF**     | Web firewall              |

Docs:

* IAM: [https://docs.aws.amazon.com/iam/](https://docs.aws.amazon.com/iam/)

---

### 3.6 Monitoring & Management

| Service        | Purpose               |
| -------------- | --------------------- |
| **CloudWatch** | Logs, metrics, alarms |
| **CloudTrail** | API activity auditing |
| **AWS Config** | Resource compliance   |

Docs:

* CloudWatch: [https://docs.aws.amazon.com/cloudwatch/](https://docs.aws.amazon.com/cloudwatch/)

---

### 3.7 DevOps & Automation

| Service            | Purpose                |
| ------------------ | ---------------------- |
| **CodeCommit**     | Git repositories       |
| **CodeBuild**      | Build automation       |
| **CodePipeline**   | CI/CD pipelines        |
| **CloudFormation** | Infrastructure as Code |

Docs:

* CloudFormation: [https://docs.aws.amazon.com/cloudformation/](https://docs.aws.amazon.com/cloudformation/)

---

## 4. AWS CLI (Most Important Tool)

### 4.1 What is AWS CLI?

A command‑line tool to manage AWS services from your terminal.

---

### 4.2 Install AWS CLI

### Windows

1. Download MSI:
   [https://aws.amazon.com/cli/](https://aws.amazon.com/cli/)
2. Run installer
3. Verify:

```bash
aws --version
```

---

### macOS

```bash
brew install awscli
aws --version
```

Docs:

* [https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

---

### Linux

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
```

---

### 4.3 Configure AWS CLI

```bash
aws configure
```

You will need:

* Access Key
* Secret Key
* Region
* Output format

Docs:

* [https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

---

## 5. Beginner Conceptual Diagrams (For GitHub)

These diagrams are intentionally **simple, minimal, and professional**, suitable for GitHub READMEs.

### Diagram 1: AWS Core Architecture

```
User
  ↓
Route 53 (DNS)
  ↓
Application Load Balancer
  ↓
EC2 / Lambda (Compute)
  ↓
RDS / DynamoDB (Database)
  ↓
S3 (Storage)
```

**Concept:** Request flow from user to backend services

---

### Diagram 2: AWS Networking (VPC)

```
VPC
 ├── Public Subnet (ALB, Bastion)
 └── Private Subnet (EC2, RDS)
```

**Concept:** Secure isolation of resources

---

### Diagram 3: AWS Security Model

```
IAM User
  ↓
IAM Role
  ↓
IAM Policy
  ↓
AWS Service Access
```

**Concept:** Permission-based access control

---

### Diagram 4: DevOps CI/CD on AWS

```
GitHub
  ↓
CodePipeline
  ↓
CodeBuild
  ↓
EC2 / ECS / EKS
```

**Concept:** Automated build and deployment

---

## 6. How Beginners Should Learn AWS (Recommended Order)

1. IAM & Security basics
2. EC2 + S3
3. VPC & Networking
4. RDS & DynamoDB
5. CloudWatch & Monitoring
6. CI/CD & Infrastructure as Code
7. Serverless & AI services

---

## 7. Hands-On Beginner Labs 

### Lab 1: Launch an EC2 Instance

* Create key pair
* Choose Amazon Linux
* Connect via SSH

Docs:
[https://docs.aws.amazon.com/ec2/latest/userguide/EC2_GetStarted.html](https://docs.aws.amazon.com/ec2/latest/userguide/EC2_GetStarted.html)

---

### Lab 2: Create an S3 Static Website

* Create bucket
* Enable static hosting
* Upload HTML

Docs:
[https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)

---

### Lab 3: IAM User & Role

* Create IAM user
* Attach policy
* Test permissions

Docs:
[https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html)

---

## 8. Official AWS Learning Links

* AWS Docs: [https://docs.aws.amazon.com/](https://docs.aws.amazon.com/)
* AWS Free Tier: [https://aws.amazon.com/free/](https://aws.amazon.com/free/)
* AWS Skill Builder: [https://skillbuilder.aws/](https://skillbuilder.aws/)

---
**AWS Blogs (Stay Current)**

**🔹 Official AWS Blog (MOST IMPORTANT)**

🔗 https://aws.amazon.com/blogs/aws/

Covers

New AWS service launches

Architecture best practices

Real-world AWS use cases

---

**🔹 AWS Architecture Blog**

🔗 https://aws.amazon.com/blogs/architecture/

Focus

Reference architectures

Design trade-offs

AWS Well-Architected examples

---

**🔹 AWS Security Blog**

🔗 https://aws.amazon.com/blogs/security/

Focus

IAM best practices

Encryption & compliance

Real security incidents and prevention

---

**🔹 AWS DevOps Blog**

🔗 https://aws.amazon.com/blogs/devops/

Focus

CI/CD pipelines

Infrastructure as Code (CloudFormation, CDK)

---

**AWS Whitepapers **

🔗 Whitepapers Portal
https://aws.amazon.com/whitepapers/

Top Whitepapers (Beginner → Architect)

Overview of AWS
Complete AWS service landscape

AWS Well-Architected Framework
Core design principles & trade-offs

AWS Security Best Practices
Security fundamentals

Architecting for the Cloud
Cloud-native design patterns

Direct PDF Links

AWS Overview
https://d1.awsstatic.com/whitepapers/aws-overview.pdf

AWS Well-Architected Framework
https://d0.awsstatic.com/whitepapers/architecture/AWS-Well-Architected-Framework.pdf

---

**Architecture & Design Resources**

🔗 AWS Architecture Center
https://aws.amazon.com/architecture/

Includes

Reference architectures

Industry-specific designs

Multi-tier, serverless, and hybrid patterns

---

**DevOps & Automation on AWS**

🔗 AWS DevOps Overview
https://aws.amazon.com/devops/

Key Services

CodeCommit – Git repositories

CodeBuild – Build automation

CodePipeline – CI/CD orchestration

CloudFormation – Infrastructure as Code

CDK – IaC using programming languages

📘 Documentation
https://docs.aws.amazon.com/devops/

---

**Security & IAM Learning** (CRITICAL)

🔗 IAM User Guide
https://docs.aws.amazon.com/IAM/latest/UserGuide/

Learn These Concepts First

IAM Users vs Roles

Managed vs Inline Policies

Least privilege principle

Multi-Factor Authentication (MFA)

🔗 AWS Security Hub
https://aws.amazon.com/security-hub/

---

**Cost Optimization & Billing**

🔗 AWS Pricing Overview
https://aws.amazon.com/pricing/

🔗 AWS Cost Management
https://aws.amazon.com/aws-cost-management/

📘 Cost Optimization Pillar (Well-Architected)
https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/

---

**AWS Certification – SAA-C03 Focus**

🔗 Official Exam Page
https://aws.amazon.com/certification/certified-solutions-architect-associate/

Exam-Heavy Services

EC2, S3, RDS, DynamoDB

VPC, IAM, Application Load Balancer

Lambda, API Gateway

📘 Official Exam Guide (PDF)
https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS_Certified_Solutions_Architect_Associate_Exam_Guide.pdf

---

**Hands-On Workshops & Labs**

🔗 AWS Workshops
https://workshops.aws/

🔗 Hands-On Tutorials
https://aws.amazon.com/getting-started/hands-on/

Recommended Labs

Build a 3-tier web application

Serverless REST API

CI/CD pipeline implementation

---

**AWS Icons & Images (For GitHub Diagrams)**

🎨 Official AWS Architecture Icons
🔗 https://aws.amazon.com/architecture/icons/

Formats

SVG (recommended for GitHub)

PNG

🖼 Reference Architecture Diagrams
🔗 https://aws.amazon.com/architecture/reference-architecture-diagrams/

---

### Final Thought

> **AWS is not about memorizing services — it’s about understanding patterns.**


