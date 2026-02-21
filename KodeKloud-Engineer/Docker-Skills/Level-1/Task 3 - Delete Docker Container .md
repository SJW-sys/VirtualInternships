# Delete Docker Container 
## Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

> A container named kke-container was created by one of the Nautilus project developers on App Server 2. It was solely for testing purposes and now requires deletion. Execute the following task:
> 
> Delete the kke-container on App Server 2 in Stratos DC.

## Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to target server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh steve@stapp02

2. Verify containers

    sudo docker ps

3. stop requested container, this container took almost a full minute to stop for me

    sudo docker stop kke-container

4. remove container, not touching volume since we would want to confirm data is not needed. Its a test so most likely fine, but you never know.

    sudo docker rm kke-container

5. verify container removed

    sudo docker ps -a

6. submit

## My Comments
NA


