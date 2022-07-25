# Terraform-AWS Training

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

- State is the important feature on Terraform

- In the project, a .tfstate file will be created with all the data brought from AWS. Normally this file would be created on terraform cloud or aws, not locally.

<img width="1087" alt="Screenshot 2022-07-13 at 22 49 48" src="https://user-images.githubusercontent.com/35227449/178842819-ddd93477-be0f-4d09-ab16-49b63bae249e.png">

- To check the state through the command line use **terraform state list** to check the available resources. In this case the only one that will appear will be the aws VPC that was just created.

<img width="552" alt="Screenshot 2022-07-13 at 22 55 48" src="https://user-images.githubusercontent.com/35227449/178843629-780d28a6-a430-4108-9ed7-bd147d564f9f.png">

- Another way to check the individual resource details through the command line is by running **terraform state show resource-name**, where resource name in this case will be _aws_vpc.mtc_vpc_

- If we instead type **terraform show** it will display everything that terraform has

![terraform show](https://user-images.githubusercontent.com/35227449/180850135-96dff011-3d94-4880-8ad5-dc6ab80c3cd3.png)

---------------

- To remove elements from terraform we'll use **terraform destroy -auot-approve** using the flag to skip approval step

![Screenshot 2022-07-25 at 19 43 59](https://user-images.githubusercontent.com/35227449/180851113-6421f41d-e2f4-4208-9f3e-454e0d0fe130.png)

- After destroying the vpc, it was also removed from AWS

![Screenshot 2022-07-25 at 19 45 49](https://user-images.githubusercontent.com/35227449/180851431-6f166876-1086-4e4c-926e-c785ed414b11.png)

---------------
- In order to continue the training, we'll create a new vpc using the command **terraform apply -auto-approve**

![Screenshot 2022-07-25 at 19 48 07](https://user-images.githubusercontent.com/35227449/180852015-3533fc39-1774-44fe-93b8-08592c6fa39b.png)

- Having a new vpc created on AWS 

![Screenshot 2022-07-25 at 19 50 04](https://user-images.githubusercontent.com/35227449/180852237-b4d3a42f-70c9-4fee-9351-b3f6b5441ba9.png)

