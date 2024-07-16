# AWS-ECS-Hands-ON

## Project Description:

## Overview :

<img width="670" alt="image" src="https://github.com/user-attachments/assets/bb894c3f-42c5-459f-a6be-d047821a8ee8">

# ECS
Amazon Elastic Container Service (ECS) is a fully managed container orchestration service provided by Amazon Web Services (AWS). It allows you to easily run, stop, and manage Docker containers on a cluster. ECS eliminates the need for you to install, operate, and scale your own cluster management infrastructure. Instead, you can focus on defining and running your applications.

# Key concepts related to ECS

## Task Definition

A task definition is a blueprint for your application. It defines various parameters, including the Docker image, CPU and memory requirements, network settings, and other configurations.It is used to create tasks, which represent the running containers in your cluster.

## Service

A service is a long-running task definition that runs and maintains a specified number of instances of a task definition. It ensures that the desired number of tasks are constantly running in the cluster.
Services enable you to define the desired state of your applications, such as the number of tasks, the task definition to use, and the network configuration.

## ECS Cluster

An ECS cluster is a logical grouping of tasks or services. It is the compute infrastructure that ECS uses to run your applications. A cluster can span multiple Availability Zones for high availability.

## Application Load Balancer (ALB)

An Application Load Balancer is a service that automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, and IP addresses.
It plays a crucial role in ensuring that traffic is evenly distributed among the tasks running in your ECS cluster.

## High Level Steps:
1.Creating a Cluster using EC2 Launch type. <br>
2.Create a Task Definition File. <br>
3.Create a service. <br>
4.Set up Load Balancer. <br>

## Step-by-Step Implementation:
## Steps :
1.Open aws account , and in the search bar type ECS. <br>
2.You will see something like then click on cluster button. <br>

<img width="1792" alt="1" src="https://github.com/user-attachments/assets/a75ea8c1-f4f7-4ed0-a11d-70f7948b188e">

3.Select or type all the selected/higlighed options . I have named cluster ECS-cluster but you can name it anything. We are going to use EC2 launch type for our running our container instance. <br>

<img width="1792" alt="2" src="https://github.com/user-attachments/assets/97434fa6-0eb2-4e3f-88fb-a99bdb25a1dd">

4.This is going to create a auto scaling template for our cluster . We can practically select any AMI but I have decide to select latest AMI by aws and for sake of saving money I have selected t2.micro instance as this is free under free tier. <br>

<img width="1792" alt="3" src="https://github.com/user-attachments/assets/db219de9-5ef9-4673-823c-bf4ee0a98be8">

5.Rest option we will leave as default and click on create cluster. <br>

<img width="1792" alt="4" src="https://github.com/user-attachments/assets/53febaea-c43d-4647-b8aa-51564cc2bc05">


6.It will take some time to create cluster.In the meantime, we will create our task definition. <br>

7.Now click on create task definition.

<img width="1792" alt="5" src="https://github.com/user-attachments/assets/375d1848-1224-4835-a552-5e6f79758f16">

8.Click on create task definition , and select the following values.<br>
we will name our task MY-task. <br> 
Again we specify that we want to run our task on EC2 instance. <br>

<img width="1792" alt="6" src="https://github.com/user-attachments/assets/3a9efa68-e681-4642-b1e2-23bc10169ae9">





10.We will select linux as the operating system ,and select awsvpc as the networking model.<br>

We will select 0.25 as the vCPU , and 0.25 GB RAM as in t2.micro instance we have 1 vCPU and 1GB ram. <br>

11.Now we have to select image for our container , I have selected inderharrysingh/netflix image , this is being host on the docker hub . You can select any image on the docker or even on the ecr , and as this is a public image , we don’t need to provide any credentials . We have selected the same RAM and CPU specification as we did in case of task. <br>

12.We will keep all other things as default. And Click on create. <br>


<img width="1792" alt="7" src="https://github.com/user-attachments/assets/ba58404c-643d-4ed7-9f03-262696c45c97">

<img width="1792" alt="8" src="https://github.com/user-attachments/assets/f813cd2d-f753-4779-bf9b-89ed520c96aa">

<img width="1792" alt="9" src="https://github.com/user-attachments/assets/5d17d003-ae06-47cf-9351-7be89aa488c1">





## wait

12.Now both our task and cluster has been created. Its time to create a service to deploy on our cluster and configure load balancer. <br>

13.Now go back to the cluster , and click on it.

<img width="1792" alt="10" src="https://github.com/user-attachments/assets/5a26ef7c-beac-4b8e-813d-b49c5472cda9">

14.Click on create service.

<img width="1792" alt="11" src="https://github.com/user-attachments/assets/f177f7e4-1fd7-4882-91fe-4f75e92b035b">

15.We will keep most of the setting default.

<img width="1792" alt="12" src="https://github.com/user-attachments/assets/ec813fcf-3b5e-4692-a49e-49fd42386b81">

16.In the family section , we will select the task we have just created and we will keep desired task to 1 , this refer to number of tasks we want to run in this service.

<img width="1792" alt="13" src="https://github.com/user-attachments/assets/eb168b48-b76c-4812-b17b-95a45b2bf969">

17.Now we will configure the load balancer , scroll down you can find the load balancer option.

<img width="1792" alt="14" src="https://github.com/user-attachments/assets/1e51b535-979b-4e68-bb45-ca3ae26bb56d">

18.Select these settings, most of the option are pre filled we just have to specify the name of the target group.

<img width="1792" alt="15" src="https://github.com/user-attachments/assets/52b793a9-ad2b-451d-be00-6713277c7d3f">




















