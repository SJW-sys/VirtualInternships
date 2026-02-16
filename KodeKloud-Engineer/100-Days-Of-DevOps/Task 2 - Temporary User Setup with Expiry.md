# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

>As part of the temporary assignment to the Nautilus project, a developer named mark requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:
>
>Create a user named mark on App Server 3 in Stratos Datacenter. Set the expiry date to 2027-01-28, ensuring the user is created in lowercase as per standard protocol.
>
>Note: You can find the infrastructure details by clicking on the Details of all Users and Servers button on the top-right section of the page.

# Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh banner@stapp03

2. Create account with Expiration

    sudo useradd -e 2027-01-28 mark

3. Validate expiration date set

    sudo chage -l mark

4. Submit

# My Comments
had to call | sudo useradd --help | to get option syntax for setting expiration.
had to use | apropos expire password | to find chage, which I then used --help with to get info on how to use command

