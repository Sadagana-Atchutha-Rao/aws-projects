# AWS Blue-Green Deployment using EC2

## Project Overview

This project demonstrates Blue-Green Deployment using AWS EC2,
Application Load Balancer, Route 53 and AWS Certificate Manager (ACM).

The Blue environment represents the current production environment,
while the Green environment represents the new application environment.

Traffic can be switched between the Blue and Green environments
through the Application Load Balancer.

## AWS Services Used

- Amazon EC2
- Application Load Balancer
- Route 53
- AWS Certificate Manager (ACM)
- Security Groups
- Apache HTTP Server

## Architecture

Developer/User
    |
    v
Route 53
    |
    v
Application Load Balancer
    |
    +-------------------+
    |                   |
    v                   v
Blue Environment   Green Environment
    |                   |
EC2 Server 1        EC2 Server 3
EC2 Server 2        EC2 Server 4

## Blue Environment

The Blue environment contains two EC2 servers running the
Villa Agency application.

## Green Environment

The Green environment contains two EC2 servers running the
Klassy Cafe application.

## Deployment Strategy

Blue = Current/Production Environment

Green = New Environment

After testing the Green environment, traffic can be switched
from Blue to Green through the load balancer.

## HTTPS

AWS Certificate Manager is used to provide the SSL/TLS certificate.

Route 53 is used for DNS management.

The Application Load Balancer listens on HTTPS port 443
and uses the ACM certificate.

## EC2 Configuration

### Blue Servers

The Blue servers install Apache HTTP Server and deploy the
Villa Agency website.

### Green Servers

The Green servers install Apache HTTP Server and deploy the
Klassy Cafe website.

## Learning Outcomes

- EC2 instance configuration
- Apache web server setup
- Application Load Balancer
- Route 53 DNS
- HTTPS configuration
- AWS Certificate Manager
- Blue-Green Deployment
- Traffic switching
- Zero-downtime deployment concepts
