# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

>Sarah created a new file named notes-t1q9.txt under /home/sarah/story-blog-t1q9 repository where she plans to write down ideas about the story for personal purposes. She does not want git to track this file or share it with her team mates.
>
>It is good that the file is untracked. But it is still under GIT's radar. If you run the git add . command, accidentally git will start to track this file.
>
>
>Let's configure git to ignore this file permanently.
>
>Use below credentials to SSH into the storage server and to complete this task.
>
>Username: sarah
>Password: 


# Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. Connect to storage server, login details found in the 'company' wiki. (In a real world this would be in a vault,or you be accessing via your own assigned identity, not a shared identity.)

    ssh sarah@ststor01

2. navigate to correct directory

    cd /home/sarah/story-blog-t1q9/

3. (optional) check in correct directory

    pwd

4. check git status

    git status

5. make git ignore file

    touch .gitignore

6. Modify git ignore file

    vi .gitignore

7. Add line in file for file to ignore

8. check file is now ignored by git

    git status


# My Comments
NA