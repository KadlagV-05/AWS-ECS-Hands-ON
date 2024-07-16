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
1.Creating a Cluster using EC2 Launch type.<br>
2.Create a Task Definition File.<br>
3.Create a service.<br>
4.Set up Load Balancer.<br>
