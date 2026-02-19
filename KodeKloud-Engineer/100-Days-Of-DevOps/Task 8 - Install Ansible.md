# Install Ansible
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> During the weekly meeting, the Nautilus DevOps team discussed about the automation and configuration management solutions that they want to implement. While considering several options, the team has decided to go with Ansible for now due to its simple setup and minimal pre-requisites. The team wanted to start testing using Ansible, so they have decided to use jump host as an Ansible controller to test different kind of tasks on rest of the servers.
>
> Install ansible version 4.7.0 on Jump host using pip3 only. Make sure Ansible binary is available globally on this system, i.e all users on this system are able to run Ansible commands.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. install ansible using pip3

    pip3 install ansible==4.7.0

2. submit


## My Comments
I am use to installing via apt, had to lookup the exact pip format to ensure I called the version number correctly.

Forgot to setup globally on first attempt, added the 'sudo -H' on second attempt.

I should spend more time with pip installs to avoid this user error in the future.