# AWS Elastic Beanstalk Deployment Models

## 📌 Project Overview

In this project, I learned how to deploy an application using **AWS Elastic Beanstalk**.

Elastic Beanstalk makes application deployment easier because AWS manages many of the resources required to run the application, such as EC2 instances, load balancing, and Auto Scaling.

Instead of creating and configuring every resource manually, we can upload our application and let Elastic Beanstalk create and manage the required environment.

---

## ☁️ AWS Services

The project uses or covers these AWS services:

* AWS Elastic Beanstalk
* Amazon EC2
* Amazon VPC
* Application Load Balancer (ALB)
* Auto Scaling Group (ASG)
* Security Groups
* IAM Roles
* Amazon S3
* Amazon CloudWatch

---

## 🔄 How Elastic Beanstalk Works

The basic process is:

```text
Application Code
       ↓
Upload to Elastic Beanstalk
       ↓
Elastic Beanstalk creates the environment
       ↓
EC2 Instances
       ↓
Load Balancer
       ↓
Application URL
```

Elastic Beanstalk manages the infrastructure needed to run the application.

---

## 🚀 Deployment Models

### 1. Single Instance

A single EC2 instance is used to run the application.

This is useful for:

* Learning
* Development
* Testing
* Small applications

### 2. High Availability

Multiple EC2 instances are used along with an Application Load Balancer and Auto Scaling.

This is more suitable for production applications because the application can continue running even if one instance has a problem.

---

## 🔀 Deployment Policies

Elastic Beanstalk provides different ways to deploy a new application version.

### All at Once

The new version is deployed to all instances at the same time.

**Advantage:** Fast deployment
**Disadvantage:** Can cause downtime

### Rolling

The instances are updated in batches.

This helps reduce downtime during deployment.

### Rolling with Additional Batch

A new batch of instances is used while the existing instances continue running.

This helps maintain application availability during deployment.

### Immutable

New EC2 instances are created for the new application version.

After the new version is working correctly, it can replace the old version.

This provides a safer way to deploy an application.

---

## 🔵🟢 Blue-Green Deployment

Blue-Green deployment uses two separate environments.

**Blue** = Current application version

**Green** = New application version

The new version is deployed to the Green environment and tested.

After confirming that everything works correctly, traffic can be switched from Blue to Green.

```text
Blue Environment
(Current Version)
       ↓
     Users

Green Environment
(New Version)
       ↓
   Test First

After Testing
       ↓
Switch Traffic
       ↓
Green becomes Live
```

This approach makes rollback easier if there is a problem with the new version.

---

## 🏗️ Architecture

The architecture contains:

* Developer
* Application package
* AWS Elastic Beanstalk
* EC2 instances
* VPC
* Security Groups
* Application Load Balancer
* Auto Scaling Group
* IAM Roles
* S3
* CloudWatch
* Application URL

See the architecture diagram in the **architecture** folder.

---

## 🎯 What I Learned

Through this project, I learned:

* What AWS Elastic Beanstalk is
* How to deploy applications using Elastic Beanstalk
* How Elastic Beanstalk manages EC2 resources
* Single Instance deployment
* High Availability deployment
* All-at-Once deployment
* Rolling deployment
* Immutable deployment
* Blue-Green deployment
* Auto Scaling
* Load Balancing
* Basic AWS application deployment concepts

---

## 📂 Project Files

```text
2.AWS Elastic Beanstalk Deployment Models
│
├── README.md
├── Documentation.txt
│
├── architecture
│   └── elastic-beanstalk-architecture.png
│
└── screenshots
```

---

## ✅ Conclusion

AWS Elastic Beanstalk makes application deployment easier by managing the infrastructure needed to run an application.

I learned how different deployment methods can be used depending on the application's requirements and how Blue-Green deployment can help reduce deployment risk and make rollback easier.
