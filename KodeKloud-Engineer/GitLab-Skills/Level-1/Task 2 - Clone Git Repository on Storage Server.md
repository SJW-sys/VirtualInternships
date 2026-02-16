# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

>The DevOps team established a new Git repository last week, which remains unused at present. However, the Nautilus application development team now requires a copy of this repository on the Storage Server in the Stratos DC. Follow the provided details to clone the repository:
>
>The repository to be cloned is located at /opt/apps.git
>
>Clone this Git repository to the /usr/src/kodekloudrepos directory. Perform this task using the natasha user, and ensure that no modifications are made to the repository or existing directories, such as changing permissions or making unauthorized alterations.


# Solution
While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to storage server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh natasha@ststor01

2. Cd to target directory (targeting via the git command worked, but never validated for me in kodekloud task checker)

    cd /usr/src/kodekloudrepos/

3. (optional) check in correct directory

    pwd

4. Clone the repo

    git clone /opt/apps.git/

5. Check repo is there

    ls -al

6. CD in to check files

    cd apps/

7. (optional) check in correct directory

    pwd

8. Check it is there

    ls -al

9. Submit


# My Comments
NA