# Terraform-AWS-Training

First a providers.tf file is created where the providers details (in this case AWS)

<img width="524" alt="providersfile" src="https://user-images.githubusercontent.com/35227449/178838220-b1e7eb37-a47f-498b-a080-59a90e12f1fe.png">

For authentication, once in AWS, create a user and get the **access key** and **secret key** and add them to the providers.tf file

- Then, **terraform init** command needs to be run in the terminal and Terraform will be up and running

- When running this command a binary file is created for Mac/Linux and for Windows is an .exe file. This file is the provider

![terraform init](https://user-images.githubusercontent.com/35227449/178357610-be9492be-a6d5-43a3-a4ac-056c1cbda217.png)

In order to create the components on AWS, in this case the VPC, a main.tf file is added

<img width="322" alt="mainfile" src="https://user-images.githubusercontent.com/35227449/178837830-0eac734b-3fcb-49e2-91a2-ac3836246461.png">

- Then the **terraform plan** command is ran to see what we are planning to build

![terrafomr plan](https://user-images.githubusercontent.com/35227449/178357718-cb0fb470-0a9e-4879-a472-8111341e5592.png)

- Once checked the content of the plan, the **terraform apply** command will be run to create the resource on AWS, in this case it will create the VPC

<img width="985" alt="terraform apply" src="https://user-images.githubusercontent.com/35227449/178838954-087a0389-a682-4ad3-8668-1ef0f841fd2c.png">

- Then the VPC on AWS will be created 

<img width="1160" alt="awsvpc" src="https://user-images.githubusercontent.com/35227449/178839024-70747158-7213-475f-adf7-9f808f9e7758.png">

