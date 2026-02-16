# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

>To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:
>
>Create a user named james with a non-interactive shell on App Server 1.
>
>Note: You can find the infrastructure details by clicking on the Details of all Users and Servers button on the top-right section of the page.

# Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. Create user without interactive shell

    sudo useradd -s /sbin/nologin james

3. Validate user setup with correct shell

    sudo cat /etc/passwd | grep "james"

4. Submit

# My Comments
Knew the command was useradd, and reviewed --help page for shell option (-s), had to google search path to call inactive shell (ie. unable to login, ideal for service accounts)

