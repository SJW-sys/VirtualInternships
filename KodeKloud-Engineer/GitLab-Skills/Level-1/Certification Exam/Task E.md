# Task
**Important -** Please note that these task can have slight variation such as usernames, filepaths, files, etc

>The Nautilus application development team was working on a git repository /usr/src/kodekloudrepos/news-t2q4 present on Storage server in Stratos DC. One of the developers mistakenly created a couple of files under this repository, but now they want to clean this repository without adding/pushing any new files. Find below more details:
>
>
>Clean the /usr/src/kodekloudrepos/news-t2q4 git repository without adding/pushing any new files, make sure git status is clean.
>
>Use below credentials to SSH into the storage server and to complete this task.
>
>Username: sarah
>Password: 


# Solution
**Important -** While there are more exact commands to make this as quick as possible, I will be as expressive as possible to show a step by step guide with optional verification steps.

1. ensure still on storage server

2. navigate to correct directory

    cd /usr/src/kodekloudrepos/news-t2q4

3. check branches

4. check status

5. clean files dry run
    git clean -n

6. clean files not currently tracked (the ones the developer added)

    git clean -f 

(You could also run 'git clean -i' to manually validate each file you are removing, which I would recommend considering in a PROD environment)

7. check git status

    git status


# My Comments
NA

