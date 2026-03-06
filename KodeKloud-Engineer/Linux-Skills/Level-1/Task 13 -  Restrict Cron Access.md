# Restrict Cron Access
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> In alignment with security compliance standards, the Nautilus project team has opted to impose restrictions on crontab access. Specifically, only designated users will be permitted to create or update cron jobs.
>
> Configure crontab access on App Server 2 as follows: Allow crontab access to rose user while denying access to the garrett user.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh steve@stapp02

2. Allow users access to crontab

    sudo vim /etc/cron.allow

    add a single user per line. Add the following:

    rose

3. Deny users access to crontab

    sudo vim /etc/cron.deny

    add a single user per line. Add the following:

    garrett

4. verfy

    su garrett crontab -l

    su rose crontab -l

5. submit


## My Comments
I have never had to lock down crontab in such a manner, had to do some review on this.


