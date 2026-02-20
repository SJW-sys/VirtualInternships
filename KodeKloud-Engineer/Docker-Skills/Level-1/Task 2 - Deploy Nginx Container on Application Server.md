# Deploy Nginx Container on Application Server
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> The Nautilus DevOps team is conducting application deployment tests on selected application servers. They require a nginx container deployment on Application Server 1. Complete the task with the following instructions:
>
> On Application Server 1 create a container named nginx_1 using the nginx image with the alpine tag. Ensure container is in a running state.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. check docker is installed

    sudo systemctl status docker

3. pull down containers image with the alpine tag

    sudo docker pull nginx:alpine

4. launch container with the name

    sudo docker run -d --name nginx_1 nginx:alpine

5. ensure running as expected

    sudo docker ps

6. submit

## My Comments
NA


