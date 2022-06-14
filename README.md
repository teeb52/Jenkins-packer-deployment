# Techpet DevOps challenge part 2
## Jenkins-packer-deployment
For this exercise follow the instructions below.
## Intructions
1. Fork this repo.
2. Deploy Jenkins to an EC2 (with or without docker).
3. After successfully Deploying Jenkins, bake the image with Hashicorp Packer.
4. Deploy the baked custom AMI to an EC2.
5. For each of the proccesses above provide screenshots
6. Organize your code.
7. write a proper Readme.Md to explain your choices and the process.

#My Processes and Choices

Steps 1 & 2:

I forked the repo for my firststep and launched an ec2 ubuntu instance on aws after which deployed jenkins into docker container on the Ubuntu ec2 instance.
![ec2 dashboard](https://user-images.githubusercontent.com/78386380/173275387-c90702e9-c190-4f8c-81a4-4935d786ba04.PNG)
To do so, i pull docker image using "docker pull jenkins/jenkins" ![image](https://user-images.githubusercontent.com/78386380/173279004-fa5fc23f-d076-4601-a649-ab86e3ffd9ed.png)
After which i ran "docker run -p 8080:8080 -p 50000:50000 --restart=on-failure jenkins/jenkins:lts-jdk11" ![image](https://user-images.githubusercontent.com/78386380/173279335-ad4c325c-9993-4b88-9911-cf1c4cda50a5.png) which enabled me use the inital password to setup jenkins ![image](https://user-images.githubusercontent.com/78386380/173279469-06968924-f030-42f3-ab78-0f1c68624b91.png)

Steps 3 & 4:

I baked the custom AMI(Ubuntu source type) with hashicorp parker by firstly authenticating my IAM usercredentials using secret access key and access key id then created a directory named 'packer_techpet'. After moving into 'packer_techpet', i created a packer config file 'aws-ubuntu.pkr.hcl' with various blocks of Hashicorp Configuration Language code, defining the image build and how to be built. After successfully creating the packer config file, i ran "packer init ." command to initialize the packer configuration then the "packer fmt && packer validate" to format and validate the file. Finally , i ran the build command "packer build aws-ubuntu.pkr.hcl" which created, started and shut-down a temporary ec2 instance and deployed the image to my ec2 region along with the snapshot.
![image](https://user-images.githubusercontent.com/78386380/173683308-cf330fd0-1ca8-41eb-840c-788e04fb4885.png)

![image](https://user-images.githubusercontent.com/78386380/173686318-ce1c4374-0660-4dfd-b490-b7545027b9d0.png)

![image](https://user-images.githubusercontent.com/78386380/173683659-5559fd90-77fb-4296-93b3-60ff303e1220.png)
