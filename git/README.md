### COMMONLY USED GIT COMMANDS

##### Add all file to staging area

    git add .

##### Add files to staging area

    git add <filePath1> <filePath2>

##### Commit files in staging area to local repo

    git commit -m <COMMIT_MSG>

##### View log with short commit hash

    git log --oneline

##### Squash commits to previous commit

    git rebase -i <PREVIOUS_COMMIT_HASH>

Lets say you have four commits

Fourth commit 09dc00e   
Third commit 875bebb    
Second commit 239e756   
First commit bb0829b

And you want to merge last two commits to second commit then PREVIOUS_COMMIT_HASH will be the hash of First commit

Once you do that you will see something like below in an editor.

Pick Fourth commit 09dc00e   
Pick Third commit 875bebb    
Pick Second commit 239e756   

Change Pick to Squash or S for the commits you want to squash. Last commit should be Pick.
(To edit press i (INSERT))

S Fourth commit 09dc00e   
S Third commit 875bebb    
Pick Second commit 239e756   

after edit press esc

then :x or :wq