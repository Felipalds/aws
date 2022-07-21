# Elastic Container Service
    Docker containers in AWS

- managed by AWS Fargate or AWS EC2

## Clusters
- logical grouping of tasks or services

## Containers and images
- containers are the standardized unit of software development that holds everything that your software application requires to run
- images are a read-only template to create containers

	images are stored in cloud, in containers registries, like DockerHub or Amazon ECR

## Task definitions
- text file that describes one or more containers that form your application (10 max)
- specify parameters like operational system, ports to open or data volumes

## Task
- the instantization of a task definition within a cluster
- you can run a standalone task or you can run a task as part of a service

## Service
- ECS services are up to run and maintain your desired tasks simultaneously in a cluster
