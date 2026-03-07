# Firewall Configuration
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> The Nautilus system administrators team has rolled out a web UI application for their backup utility on the Nautilus application server 3 within the Stratos Datacenter. This application runs on port 5000 and appropriate firewall rules must be configured to allow incoming traffic. To achieve this, firewalld needs to be installed and configured on the application server. To ensure proper functionality, the following requirements have been identified:
>
> Install and enable the firewalld service.
> Allow all incoming connections on port 5004/tcp.
> Ensure the zone is set to public.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh banner@stapp03

2. update system and install firewalld

    sudo yum install -y firewalld

3. enabled firewalld

    sudo systemctl enable firewalld

4. start firewalld

    sudo systemctl start firewalld

5. allow all incoming connections on the public zone to port 5000/tcp

    sudo firewall-cmd --zone=public --permanent --add-port=5004/tcp

6. reload firewalld

    sudo firewall-cmd --reload

7. verfiy ports added

    sudo firewall-cmd --list-ports --zone=public


## My Comments
For some reason this failed the task on the first attempt, but the 2nd attempt I did the same steps and it worked just fine.


