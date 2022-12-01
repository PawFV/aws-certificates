# VPC - [Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

![](./assets/VPC-diagram.png)

It's like your own private cloud but within AWS.

- It allows to launch resources in a virtual network that you define.
- AWS account comes with predefined default VPC in each region, you can launch resources on default VPC right away. 

![](./assets/2022-12-01-10-17-36.png)

For creating it you assign a range of IP address, it spans all AZ in a region, you can add subnets in each AZ.

**Subnet**

It's a partition of a VPC IP address range.

![](./assets/2022-12-01-10-30-57.png)

![](./assets/2022-12-01-10-49-11.png)

**VPC Example**

![](./assets/2022-12-01-10-57-32.png)

**Security**

VPC is secured through security groups, ie: store data in S3 and allow access only to instances inside VPC.

## Internet Gateway

It **allows communication** between **internet** and **VPC**.

Is **horizontally scaled**, **redundant** and **highly available** by default.

### Enable Internet Access to instances in a VPC subnet

1. Attach Internet Gateway to the VPC.
2. Add a Route to the subnet Route Table and point the Route to the Internet Gateway.
3. Make sure your instances have public IPv4, IPv6 or Elastic IP Address (static IPv4 address that can be moved from one instance to another).
4. Make sure that Security Groups and Network Access Control Lists (NACLs) that allow relevant traffic to float out of the instances.

![](./assets/2022-12-01-11-23-30.png)

