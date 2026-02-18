# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. To initiate testing, the following requirements have been established for App server 1 in the Stratos Datacenter:
>
> Install the required SELinux packages.
>
> Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.
>
> No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.
>
> Disregard the current status of SELinux via the command line; the final status after the reboot should be disabled.

# Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. Install SELinux

    sudo yum install selinux-policy selinux-policy-targeted policycoreutils setroubleshoot

3. change selinux to disable via config file, since called out in prompt to avoid cli

    sudo vi /etc/selinux/config

    ensure the following:

    SELINUX=disabled

4.  Submit

# My Comments
Had to look up exact package to install via my own notes from homelab deployments, using 'yum search selinux' returned to many results to know 100% what was the best to install.
