###
✅ 1. AWS CLI Command to List EC2 Instances
aws ec2 describe-instances \
  --query "Reservations[*].Instances[*].{ID:InstanceId,State:State.Name,IP:PublicIpAddress,Name:Tags[?Key=='Name']|[0].Value}" \
  --output table
  
✅ 2. Terraform Script to Deploy EC2 Instance

provider "aws" {
  region = "ap-southeast-1" # change as needed
}

resource "aws_key_pair" "my_key" {
  key_name   = "my-key"
  public_key = file("~/.ssh/id_rsa.pub") # Adjust path if needed
}

resource "aws_instance" "my_ec2" {
  ami           = "ami-0c02fb55956c7d316" # Amazon Linux 2 AMI (us-east-1)
  instance_type = "t2.micro"

  key_name = aws_key_pair.my_key.key_name

  tags = {
    Name = "Terraform-Instance"
  }

  # Optional security group
  vpc_security_group_ids = [aws_security_group.allow_ssh.id]
}

resource "aws_security_group" "allow_ssh" {
  name        = "allow_ssh"
  description = "Allow SSH inbound traffic"

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

output "public_ip" {
  description = "Public IP of the EC2 instance"
  value       = aws_instance.my_ec2.public_ip
}

✅ 3. SSH Script to Connect Using Terraform Output
Save this as ssh-to-ec2.sh:

bash
Copy
Edit
#!/bin/bash

# Get public IP from Terraform output
PUBLIC_IP=$(terraform output -raw public_ip)

# SSH into the EC2 instance
ssh -i ~/.ssh/id_rsa ec2-user@$PUBLIC_IP
Make it executable:

bash
Copy
Edit
chmod +x ssh-to-ec2.sh
🔁 Quick Steps to Use:
bash
Copy
Edit
terraform init
terraform apply -auto-approve
./ssh-to-ec2.sh


terraform plan -out=tfplan
terraform apply tfplan 

# Get public IP from Terraform output
PUBLIC_IP=$(terraform output -raw public_ip)

# SSH into the EC2 instance
ssh -i ~/.ssh/id_rsa ubuntu@$(terraform output -raw public_ip)