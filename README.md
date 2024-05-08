Install CodeDeploy Agent in EC2 Instance Step URL
URL: https://docs.aws.amazon.com/codedeploy/latest/userguide/codedeploy-agent-operations-install-linux.html

###Sample###


#!/bin/bash -xe
yum update -y

yum install httpd -y

echo 'Hello' >> /var/www/html/index.html

systemctl restart httpd

## Code Deploy Agent Bootstrap Script##
sudo yum update -y

sudo yum install ruby -y

sudo yum install wget -y

cd /home/ec2-user

wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install

chmod +x ./install

sudo ./install auto

systemctl start codedeploy-agent

systemctl status codedeploy-agent
