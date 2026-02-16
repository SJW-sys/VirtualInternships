# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 1 within the Stratos Datacenter.
>
> Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 1. Additionally, ensure that all users have the capability to execute it.

# Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. (optional) review current file permissions

    ls -al /tmp/xfusioncorp.sh 

3. set file permissions so owner,group and other users have execute permissions

    sudo chmod 755 /tmp/xfusioncorp.sh

4. (optional) review current file permissions

    ls -al /tmp/xfusioncorp.sh

5. Submit

# My Comments
Had an issue where the file was not readable per default settings, so running | chmod +a | against the file will not work as you need to ensure read permissions for users.

