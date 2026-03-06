# Default GUI Boot Configuration
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> With the installation of new tools on the app servers within the Stratos Datacenter, certain functionalities now necessitate graphical user interface (GUI) access.
>
> Adjust the default runlevel on all App servers in Stratos Datacenter to enable GUI booting by default. It's imperative not to initiate a server reboot after completing this task.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh tony@stapp01

2. review runlevel options, I could not remember which of the levels allows GUI

    man runlevel

3. see current runlevel

    systemctl get-default

4. set run level to 5 (GUI)

    sudo systemctl set-default graphical.target

5. validate new runlevel

    systemctl get-default

6. complete changes on other app servers

7. submit


## My Comments
Rarely interacted with runlevels, had to review how to change this with a systemd system.


