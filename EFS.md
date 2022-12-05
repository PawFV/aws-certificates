- [EFS - Elastic File System](#efs---elastic-file-system)
  - [Overview](#overview)
    - [Protocols Supported for File Transfer](#protocols-supported-for-file-transfer)
    - [Availability \& Durability](#availability--durability)
    - [Use Cases](#use-cases)
    - [File Systems](#file-systems)
  - [Features](#features)
    - [Storage Classes and Lifecycle Management](#storage-classes-and-lifecycle-management)
    - [Performance Modes](#performance-modes)
    - [Throughput Modes](#throughput-modes)
    - [Encryption](#encryption)
    - [Containers and Serverless File Storage](#containers-and-serverless-file-storage)

# EFS - Elastic File System

## Overview

Is a secure transfer service that enables you to transfer files into and out of AWS storage services.

It manages file storage infrastructure, meaning you avoid the complexity of deploying, patching & maintaining complex file system configurations.

### Protocols Supported for File Transfer

- Secure Shell (SSH) File Transfer Protocol (SFTP): version 3
- File Transfer Protocol Secure (FTPS)
- File Transfer Protocol (FTP)
- Applicability Statement 2 (AS2)

![](./assets/2022-12-05-11-10-05.png)

Is highly scalable, it scales on demand of petabytes without disrupting applications, growing and shrinking automatically as you add or remove files.

Is designed to provide massively parallel shared access to thousands of EC2 instances where they can access the data in EFS at the same time. This enables applications to achieve high levels of aggregate throughput and IOPS with consistent low latencies.

![](./assets/2022-12-05-11-19-12.png)

### Availability & Durability

It stores data across multiple AZs and you can access across diferent AZs and VPCs. 

On premises servers can acces using AWS Direct Connect or AWS VPN.

![](./assets/2022-12-05-11-22-18.png)

### Use Cases

- Home directories
- Business critical applications
- Web Serving
- Content management
- Big Data Analytics
- Application development and testing
- Media and Entertainment workflows
- Database Backups
- Container Storage

### File Systems

It is designed for Linux type of application. It offers two File Systems to choose from.

- Amazon FSx for Windows File Server.
- Amazon FSx for Lustre. (For compute intensive workloads)

![](./assets/2022-12-05-11-30-48.png)

## Features

### Storage Classes and Lifecycle Management

EFS offers two storage classes.

**Standard Storage Class** 

Used to access frequently accessed stored files.

**Infrequent Access Storage Class (EFS IA)**

It is a lower cost designed to storing files not accessed everyday. 

You can start using it by enabling EFS Lifecycle management, when enabled it migrates files from STD to IA after a set period of time with defined Lifecycle Policy.

Using the Industry Accepted Estimate where 20% of data is actively used and 80% is infrequently accessed you can store your files in EFS at an effective price of $0.08 / GB-month.

![](./assets/2022-12-05-11-53-54.png)

### Performance Modes 

There are 2 performance modes to choose from:

**General Performance**

Provides the lowest latencies per file system operation and achieve this for random or sequential IO patterns.

**MAX IO**

Can achieve higher aggregate throughput and operations per sec and is ideal for highly parallelized applications that can scale up to thousands of EC2 instances 

### Throughput Modes

They help determine the system overall throughput can achieve. It offers 2 trhoughput modes.

**Bursting**

The throughput scales with the size of the file system dynamically bursting to support the spiky nature of many File-based workloads.

**Provisioned**

Designed to support applications that require higher dedicated throughput than the default bursting mode.

Can be configured independently with the amount of data stored in the file system.

![](./assets/2022-12-05-12-00-48.png)

### Encryption

Supports encryption of data in transit at rest, providing comprehensive encryption solution.

Data at rest is transparently encrypted using encryption keys managed by AWS Key Management Service (KMS).

Encryption of data in transit uses industry standard Transport Layer Security (TLS), to secure Network traffic without having to modify your applications.

![](./assets/2022-12-05-12-07-42.png)

### Containers and Serverless File Storage

It's integrated with Serverless Compute Services from AWS that require shared storage for Latency-sensitive and IOPS-heavy workloads at any scale.

In a single step EFS provides applications running on ECS, EKS, Fargate & Lambda access to shared file system for stateful workloads.

![](./assets/2022-12-05-12-08-07.png)