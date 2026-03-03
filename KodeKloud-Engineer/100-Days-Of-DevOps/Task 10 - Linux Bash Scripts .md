# Linux Bash Scripts
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> The production support team of xFusionCorp Industries is working on developing some bash scripts to automate different day to day tasks. One is to create a bash script for taking websites backup. They have a static website running on App Server 2 in Stratos Datacenter, and they need to create a bash script named ecommerce_backup.sh which should accomplish the following tasks. (Also remember to place the script under /scripts directory on App Server 2).
>
> a. Create a zip archive named xfusioncorp_ecommerce.zip of /var/www/html/ecommerce directory.
> 
> b. Save the archive in /backup/ on App Server 2. This is a temporary storage, as backups from this location will be clean on weekly basis. Therefore, we also need to save this backup archive on Nautilus Backup Server.
>
> c. Copy the created archive to Nautilus Backup Server server in /backup/ location.
>
> d. Please make sure script won't ask for password while copying the archive file. Additionally, the respective server user (for example, tony in case of App Server 1) must be able to run it.
>
> e. Do not use sudo inside the script.
> Note:The zip package must be installed on given App Server before executing the script. This package is essential for creating the zip archive of the website files. Install it manually outside the script.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh steve@stapp02

2. install zip

    sudo yum install zip -y

3. check /scripts and /backup exist

    ls -al / | grep -e "scripts" -e "backup"

    if they don't exist, then make them using:
        mkdir -p /PATH

4. make the script

    touch /scripts/ecommerce_backup.sh

5. Set the permissions

    chmod a+x /scripts/ecommerce_backup.sh

6. validate script exist with correct permissions

    ls -al /scripts

7. setup ssh key pair for script without passkey, only one shared users on both servers which is why this will work, you would normally consider strict permission service accounts and a vault to pull in any secrets like passkeys

    ssh-keygen -t ed25519 -a 100 -f ~/.ssh/id_scriptbackup_ed25519

8. copy public key to backup server

    ssh-copy-id -i ~/.ssh/id_scriptbackup_ed25519.pub clint@stbkp01

9. check if ssh config allows keys to work, if failure you will need to connect to remote server and correct

    ssh -i .ssh/id_scriptbackup_ed25519 clint@stbkp01

    exit from the server

10. write script on app server

    vi /scripts/ecommerce_backup.sh


    Add the following, this is a bare bones solution, for a more robust add outputs at cli, logging, error catching, etc.
        #!/bin/bash
        #zipping files to local backup
        zip -r /backup/xfusioncorp_ecommerce.zip /var/www/html/ecommerce
        #sending local backup of zip to remote backup
        scp -i .ssh/id_scriptbackup_ed25519 /backup/xfusioncorp_ecommerce.zip clint@stbkp01:/backup

    be sure to write out and save

11. test

    bash /scripts/ecommerce_backup.sh

12. validate on local machine

    ls -al /backup

13. Validate on target

    ssh -i .ssh/id_scriptbackup_ed25519 clint@stbkp01
    ls -al /backup

14. submit

## My Comments
NA


