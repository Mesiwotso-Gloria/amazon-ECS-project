# Deploy docker containers on ECS

## Overview
Amazon Elastic Container Service (Amazon ECS) is the AWS service you use to run Docker applications. In this project, you will learn how to run a Docker-enabled sample application on an Amazon ECS cluster behind a load balancer and test the sample application.

## Set up your first run with Amazon ECS
1. To launch the Amazon ECS first-run wizard, choose the "Get started" button.

## Create container and task definition
A task definition is like a blueprint for your application. In this step, you will specify a task definition so Amazon ECS knows which Docker image to use for containers, how many containers to use in the task, and the resource allocation for each container.
1. In the "Container definition" field, select "sample-app". The task definition comes preloaded with default configuration values.
2. Review the default values and choose "Next".

## Define your service
Now that you have created a task definition, you will configure the Amazon ECS service. A service launches and maintains copies of the task definition in your cluster. 

NB: Service options come preloaded with default configuration values

1. `Service name`: The default sample-app-service is a web-based "Hello World" application provided by AWS. It is meant to run indefinitely; because it is running as a service, it will restart if the task becomes unhealthy or unexpectedly stops.
2. `Number of desired tasks`: Leave the default value of 1. This will create one copy of your task
3.  `Load balancing`: You have the option to use a load balancer with your service. Amazon ECS can create an Elastic Load Balancing (ELB) load balancer to distribute the traffic across the container instances your task is launched on. Select the `Application Load Balancer` option.
4.  Review your settings and choose `Next`.

## Configure your cluster
Your Amazon ECS tasks run on a cluster, which uses "AWS Fargate" to provide the compute engine so that you do not need to manage servers. In this step, you will configure the cluster. 
1. In the Cluster name field, enter sample-cluster and choose Next

## Launch and view your resources
In this step, you will review, launch, and view the resources you create.You have a final chance to review your task definition, task configuration, and cluster configuration before launching.
1. Click "create".

## Open the sample application
In this step, you will verify that the sample application is up and running by pointing your browser to the load balancer DNS name. 

1. On the sample-app-service page, select the "Details" tab and select the entry under "Target Group Name".
2. On the "Target groups" page, select the target group name.
3. In the "Details" section, choose the "Load balancer" link.
4. In the "Description" tab, select the two page icon next to the load balancer DNS to copy the DNS name to your clipboard.
5. Paste it into a new browser window, and press enter to view the sample application (in this case, a static webpage).

Your sample application should look like the below:
![](https://github.com/Mesiwotso-Gloria/amazon-ECS-project/blob/main/ecs_wizard_step_6.png?raw=true)
