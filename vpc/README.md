# VPC CloudFormation Template
This is a CloudFormation template for creating a VPC with public and private subnets in two availability zones. It also creates an Internet Gateway, NAT Gateways, and routing tables.

## public-private-subnet-igw-ec2.yaml

### Parameters
| Parameter Key | Default Value | Description |
|--------------|---------------|-------------|
| KeyName      | MyCloudKey    | Key pair name |
| VpcCidr      | 10.0.0.0/16   | CIDR for VPC |
| PublicSubnet | 10.0.0.0/24 | CIDR for public subnet |   
| PrivateSubnet| 10.0.1.0/24   | CIDR for private subnet |

### Created Services
| Service             | Tag               | Description                            |
|---------------------|-------------------|----------------------------------------|
| VPC                 | MyCloud-VPC       | CIDR: 10.0.0.0/16                      |
| Public Subnet       | MyCloudPublic-SN  | CIDR: 10.0.0.0/24, AZ: ap-northeast-2a |
| Private Subnet      | MyCloudPrivate-SN | CIDR: 10.0.1.0/24, AZ: ap-northeast-2c |
| NAT Gateway         | MyCloud-NATGW     | EIP: vpc, Subnet: public subnet        |
| Internet Gateway    | MyCloud-IGW       | Attachment: public subnet              |
| Public Route Table  | MyCloudPublic-RT  | Route: 0.0.0.0 -> IGW                  |
| Private Route Table | MyCloudPrivate-RT | Route: Public subnet -> NAT Gateway    |
| EC2 Instance        | MyCloud-EC2       | Type: t2.micro, Subnet: public subnet  |
| EC2 Instance        | MyCloud-EC2       | Type: t2.micro, Subnet: private subnet |

