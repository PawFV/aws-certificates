# VPC - [Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

![](./assets/VPC-diagram.png)

It's like your own private cloud but within AWS.

- It allows to launch resources in a virtual network that you define.
- AWS account comes with predefined default VPC in each region, you can launch resources on default VPC right away. 

![](./assets/2022-12-01-10-17-36.png)

For creating it you assign a range of IP address, it spans all AZ in a region, you can add subnets in each AZ.

## Subnet

It's a partition of a VPC IP address range.
![](./assets/2022-12-01-10-30-57.png)

![](./assets/2022-12-01-10-49-11.png)

## VPC Example

![](./assets/2022-12-01-10-57-32.png)