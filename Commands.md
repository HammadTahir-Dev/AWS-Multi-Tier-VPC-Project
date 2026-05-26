# AWS Multi Tier VPC Project Commands

## Connect to EC2

### Amazon Linux
ssh -i "VPC-keypair.pem" ec2-user@PUBLIC-IP``

# Update Server
sudo yum update -y

# Install Apache Web Server
sudo yum install httpd -y

# Start Apache
sudo systemctl start httpd
sudo systemctl enable httpd

# Check Apache Status
sudo systemctl status httpd

# Create Website Page
echo "<html><body><h1>AWS Multi Tier Project</h1><h3>Developer: Muhammad Hammad</h3></body></html>" | sudo tee /var/www/html/index.html

# Restart Apache
sudo systemctl restart httpd

# Test Website
http://PUBLIC-IP

# Security Group Rules
| Type | Port | Source |
|------|------|---------|
| SSH | 22 | Your IP |
| HTTP | 80 | 0.0.0.0/0 |

# Route Table Rule
| Destination | Target |
|-------------|--------|
| 0.0.0.0/0 | Internet Gateway |

# Project Components
- Custom VPC
- Public Subnet
- Private Subnet
- Internet Gateway
- Route Table
- EC2 Public Web Server
- EC2 Private Backend Server
- Security Groups