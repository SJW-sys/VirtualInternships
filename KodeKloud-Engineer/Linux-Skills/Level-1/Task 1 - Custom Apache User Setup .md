# Custom Apache User Setup
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> In response to heightened security concerns, the xFusionCorp Industries security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:
>
> a. Create a user named anita on App server 1 within the Stratos Datacenter.
>
> b. Assign a unique UID 1421 and designate the home directory as /var/www/anita.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. add user

    sudo useradd -b /var/www/anita -u 1421 anita

3. (optional) check home directory and its permissions

    sudo ls -al /var/www/anita

4. (optional) check user

    sudo cat /etc/passwd | grep "anita"

5. submit

## My Comments
NA


