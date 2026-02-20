# 🚀 Roboshop Infra Setup

## Create EC2 + Route53 Records

ansible-playbook -i localhost, aws-infra-ec2-r53/main.yml \
-e '{"instances":["mongodb","catalogue","redis","user","cart","mysql","shipping","rabbitmq","payment","frontend"]}' \
-e action=create


## Destroy EC2 + Route53 Records

ansible-playbook -i localhost, aws-infra-ec2-r53/main.yml \
-e '{"instances":["mongodb","catalogue","redis","user","cart","mysql","shipping","rabbitmq","payment","frontend"]}' \
-e action=destroy

## Command to Configure ONE Service

ansible-playbook -i inventory.ini roboshop.yml -e component=mongodb

## If You Want To Configure All Services (Run One by One)

ansible-playbook -i inventory.ini roboshop.yml -e component=mongodb
ansible-playbook -i inventory.ini roboshop.yml -e component=redis
ansible-playbook -i inventory.ini roboshop.yml -e component=mysql
ansible-playbook -i inventory.ini roboshop.yml -e component=rabbitmq
ansible-playbook -i inventory.ini roboshop.yml -e component=catalogue
ansible-playbook -i inventory.ini roboshop.yml -e component=user
ansible-playbook -i inventory.ini roboshop.yml -e component=cart
ansible-playbook -i inventory.ini roboshop.yml -e component=shipping
ansible-playbook -i inventory.ini roboshop.yml -e component=payment
ansible-playbook -i inventory.ini roboshop.yml -e component=frontend
