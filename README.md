# Terraform-AWS-Training

- First a providers.tf file is created where the providers details (in this case AWS)

<img width="524" alt="providersfile" src="https://user-images.githubusercontent.com/35227449/178838220-b1e7eb37-a47f-498b-a080-59a90e12f1fe.png">

- For authentication, once in AWS, create a user and get the **access key** and **secret key** and add them to the providers.tf file

- Then, **terraform init** command needs to be run in the terminal and Terraform will be up and running

- When running this command a binary file is created for Mac/Linux and for Windows is an .exe file. This file is the provider

![terraform init](https://user-images.githubusercontent.com/35227449/178357610-be9492be-a6d5-43a3-a4ac-056c1cbda217.png)

*** One important thing to highlight is that when creating an AWS account, there will be a default VPC created. So in order to avoid going over the limit of Free tier, remove the default one and proceed to create the VPC through the Terraform command since only 1 VPC should be running (750h/month).

- In order to create the VPC on AWS, a main.tf file is added

<img width="322" alt="mainfile" src="https://user-images.githubusercontent.com/35227449/178837830-0eac734b-3fcb-49e2-91a2-ac3836246461.png">

- Then the **terraform plan** command is ran to see what we are planning to build

![terrafomr plan](https://user-images.githubusercontent.com/35227449/178357718-cb0fb470-0a9e-4879-a472-8111341e5592.png)

- Once checked the content of the plan, the **terraform apply** command will be run to create the VPC resource on AWS

<img width="985" alt="terraform apply" src="https://user-images.githubusercontent.com/35227449/178838954-087a0389-a682-4ad3-8668-1ef0f841fd2c.png">

- Then the VPC on AWS will be created 

<img width="1160" alt="awsvpc" src="https://user-images.githubusercontent.com/35227449/178840916-c19a2759-f943-4883-8490-5c74534b3595.png">

- Another way to check if the VPC was created is to check on AWS on VsCode. 

<img width="333" alt="Screenshot 2022-07-13 at 22 26 24" src="https://user-images.githubusercontent.com/35227449/178839720-a5dce870-b69e-4992-ac79-c9fcf6b0b369.png">

- If we click on the VPC resource on VsCode, it will display the details of it 

<img width="774" alt="Screenshot 2022-07-13 at 22 32 10" src="https://user-images.githubusercontent.com/35227449/178841089-88660af5-29b1-4283-9c89-392b0b6e8253.png">

-------------------------

- Now we need to understand the concept of State on Terraform
https://www.terraform.io/language/state

- In the project, a .tfstate file will be created with all the data brought from AWS. Normally this file would be created on terraform cloud or aws, not locally.

<img width="1087" alt="Screenshot 2022-07-13 at 22 49 48" src="https://user-images.githubusercontent.com/35227449/178842819-ddd93477-be0f-4d09-ab16-49b63bae249e.png">

- To check the state through the command line use **terraform state list** to check the available resources. In this case the only one that will appear will be the aws VPC that was just created.

<img width="552" alt="Screenshot 2022-07-13 at 22 55 48" src="https://user-images.githubusercontent.com/35227449/178843629-780d28a6-a430-4108-9ed7-bd147d564f9f.png">

