# VPC CloudFormation Template
This is a CloudFormation template for creating a VPC with public and private subnets in two availability zones. It also creates an Internet Gateway, NAT Gateways, and routing tables.

## public-private-subnet-igw-ec2.yaml

### Parameters
| Parameter Key | Default Value | Description |
|--------------|---------------|-------------|
| KeyName      | Key pair      | Key pair name |
| InstanceType | t2.micro      | EC2 instance type |
| Vpc | String |     
| Subnet | String |        
| EC2Name | String        | Name of EC2 instance |

### Created Services
| Service             | Tag               | Description                                |
|---------------------|-------------------|--------------------------------------------|
| Security Group      | MyCloud-SG        | Inbound: http / https / SSH, Outbound: All |
| EC2 Instance        | MyCloud-EC2       | Type: t2.micro, Subnet: public subnet      |

