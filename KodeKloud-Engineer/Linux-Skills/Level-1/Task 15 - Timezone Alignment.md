# Timezone Alignment
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> In the daily standup, it was noted that the timezone settings across the Nautilus Application Servers in the Stratos Datacenter are inconsistent with the local datacenter's timezone, currently set to Africa/Asmara.
>
> Synchronize the timezone settings to match the local datacenter's timezone (Africa/Asmara).

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. see the current timezone

    timedatectl

3. change timezone

    sudo timedatectl set-timezone Africa/Asmara

4. Verify new timezone

    timedatectl

5. Complete step 2-4 on the other app servers

6. submit

## My Comments
In theory If this was in a prod environment, It might be worth to review any templates (terraform/packer/etc) or ansible setups to ensure the timezones are accurate to what we want for our base systems. Sounds like we want to review options to set it based on local datacenter timezones.


