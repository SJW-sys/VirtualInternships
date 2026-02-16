# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.
> 
> Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.


# Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to first app server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. modify ssh server global config file to block root access

    sudo vi /etc/ssh/sshd_config

3. modify the "PermitRootLogin" to be disable, the line should look like this:

    PermitRootLogin no

4. Write (Save) and exit the file

5. reload SSH server for changes to take affect.

    sudo systemctl reload sshd

6. Exit ssh connection back to jumphost

    exit
    
7. repeat steps 1-6 with correct logins for the other 2 app servers, when done, submit.

# My Comments
NA

