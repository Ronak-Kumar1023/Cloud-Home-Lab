# Cloud Home Lab

This is an automated cloud home lab environment on AWS using Terraform. It includes a VPC, subnets, an internet gateway, security groups, and 3 EC2 instances for different roles, such as a Windows workstation, Kali Linux attacker, and a security tools box.

## Network Topology

![image](https://github.com/user-attachments/assets/0c1a099a-f87f-4c3f-919d-dc9b78f4b2e6)


## Features

- **VPC Creation**: A Virtual Private Cloud with a public subnet.
- **Internet Access**: An internet gateway for external connectivity.
- **Security Groups**: Configured for different EC2 instances with appropriate ingress and egress rules.
- **EC2 Instances**: Windows 10 Workstation, Kali Linux Attacker, and a Linux Security Tools instance.
- **Outputs**: Public IP addresses of the created instances for easy access.

## Technologies Used

- **Terraform**: Infrastructure as Code (IaC) tool for defining and provisioning the infrastructure.
- **AWS**: Cloud service provider for hosting the resources.
- **AMI Images**: Specific Amazon Machine Images for Windows, Kali Linux, and Security Tools.

## Setup Instructions

1. **Clone the Repository:**
```bash
git clone https://github.com/Ronak-Kumar1023/Cloud-Home-Lab.git
```

2. Initialize Terraform:

```bash
terraform init
```
3. Plan the Deployment:
```bash
terraform plan
```

4. Apply the Configuration:
```bash
terraform apply
```

5. Access Your Instances: Once the deployment is complete, Terraform will output the public IP addresses of the created EC2 instances.

## Configuration Details
- Provider: AWS (Region: us-east-2)

- VPC CIDR Block: 10.0.0.0/16

- Public Subnet CIDR Block: 10.0.1.0/24

- Internet Gateway: Attached to the VPC

- Security Groups:
    - Windows and Kali Security Group: Allows SSH (port 22), RDP (port 3389), and ICMP
    - Linux Security Tools Security Group: Allows HTTP (port 80), VNC (ports 5900-5920), RDP (port 3389 UDP), SSH (port 22), and custom TCP port (9997)

- EC2 Instances:
    - Windows 10 Workstation:
        - AMI: ami-03f5152d831db85a0
        - Instance Type: t2.micro
        - Volume Size: 30 GB
    - Kali Attacker:
        - AMI: ami-01cf4a347420d3cb7
        - Instance Type: t2.micro
        - Volume Size: 12 GB
    - Security Tools:
        - AMI: ami-04911b1f694f455b8
        - Instance Type: t3.large
        - Volume Size: 30 GB

## Outputs
- Windows 10 Workstation IP Address:
- Kali Attacker IP Address:
- Security Tools EC2 IP Address:

## Future Improvements
- User Data Scripts: Enhance automation with additional setup scripts.
- Monitoring: Integrate monitoring and alerting for security and performance.
- Scalability: Add more instances and resources as needed for expanded functionality.

## Acknowledgements
This project was inspired by "Cybersecurity Home Lab" by Grant Collins
