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
I forked the repo for my firststep and launched an ec2 ubuntu instance on aws after which deployed jenkins into docker container on the Ubuntu ec2 instance.
![ec2 dashboard](https://user-images.githubusercontent.com/78386380/173275387-c90702e9-c190-4f8c-81a4-4935d786ba04.PNG)
To do so, i pull docker image using "docker pull jenkins/jenkins" ![image](https://user-images.githubusercontent.com/78386380/173279004-fa5fc23f-d076-4601-a649-ab86e3ffd9ed.png)
After which i ran "docker run -p 8080:8080 -p 50000:50000 --restart=on-failure jenkins/jenkins:lts-jdk11" ![image](https://user-images.githubusercontent.com/78386380/173279335-ad4c325c-9993-4b88-9911-cf1c4cda50a5.png) which enabled me use the inital password to setup jenkins ![image](https://user-images.githubusercontent.com/78386380/173279469-06968924-f030-42f3-ab78-0f1c68624b91.png)
