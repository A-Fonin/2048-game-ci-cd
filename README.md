# 2048 Game CI/CD Pipeline on AWS

## 🌥️ Project Overview
#### This project demonstrates how to set up a complete CI/CD pipeline to deploy a Dockerized version of the 2048 game on AWS using ECS with Fargate. It covers:

- Building and pushing a Docker image of the 2048 game to Amazon ECR

- Setting up AWS CodePipeline to automate the build and deployment process

- Deploying the container to Amazon ECS using the Fargate launch type


![Architecture Diagram](https://imgur.com/KrDbVxx.png)


## 🧱 Project Steps
### 1️⃣ Docker Setup & ECR Integration
- Install Docker

- Configure AWS CLI

- Clone the 2048 game source code

- Build the Docker image  

![Docker-Image](https://imgur.com/9uQXsH4.png)

- Push the image to Amazon ECR
   
![ECR](https://imgur.com/0h7ioAT.png)  


### 2️⃣ ECS Fargate Deployment
- Create an ECS Cluster with Fargate launch type

- Define a Task Definition using the Docker image from ECR

- Deploy the service and access the 2048 game via the ECS public URL

![ECS/TASK](https://imgur.com/QQQzf7u.png)

![Verify Functionality](https://imgur.com/DRbF2Vq.png)

### 3️⃣ CI/CD with AWS CodePipeline & CodeBuild
- Create an IAM Role for CodeBuild

- Create an S3 Bucket for storing build artifacts

- Create and test a CodeBuild Project

- Set up an AWS CodePipeline connected to your GitHub repo

- Push changes to GitHub to trigger automatic deployment
   
![CODE-BUILD](https://imgur.com/aNF86zH.png)
![S3 Bucket](https://imgur.com/lTCcijl.png)
![Commit-Push](https://imgur.com/v6gMp5w.png)
![Game Pipeline](https://imgur.com/11f66I8.png)


### ➡️ Final Result

![2048-game-ci-cd](https://imgur.com/2DadIUr.png)


## 🧾 Conclusion
This project showcases a practical implementation of DevOps and cloud-native application deployment using AWS services. Key takeaways:

- Built a CI/CD pipeline using CodePipeline and CodeBuild

- Containerized the app and deployed to Amazon ECS with Fargate

- Reduced manual steps and ensured fast, reliable deployments


#### 🧹 Clean-up Resources
To avoid incurring unnecessary AWS charges:

###### Delete CodePipeline:
- Navigate to the AWS CodePipeline Console and delete the pipeline.

###### Delete CodeBuild Project:
- Go to the CodeBuild Console and remove the project.

###### Remove IAM Roles/Policies:
- Delete roles and policies created for CodeBuild and CodePipeline.

###### Delete S3 Bucket:
- Remove the bucket used for storing build artifacts if no longer needed.

###### Delete ECR Repository:
- Go to the ECR Console and delete the image repository.

###### Delete ECS Services and Cluster:
- Remove ECS services and the cluster (e.g., 2048-game-cluster, 2048-service) from the ECS Console.
