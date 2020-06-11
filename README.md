# learn
Learn Git 


Cloning: Cloning means creating a copy of the remote repo on your local machine. Now you can make changes to the project on your local machine.

git clone <Repo-URL>

Commit: When you commit a change, you save the changes you made to your files in the repo. When working with Git from your local machine, using the commit command will save your files in the local repo. To make those changes in the remote repo, you will use the push command.

git commit -m “<commit message>”

Push: Push command allows you to transfer all the changes on your local repo to the remote repo. Now all the fellow developers will have access to the changes you made and they can update their local repositories.

git push origin <branch>


Pull: If push meant transferring code to the remote repo, the Pull command allows you to transfer all the changes from the remote repo to your local repo. So any changes that your fellow developer pushed to the remote repo, you can transfer them to your local repo using the pull command.

There are a few more terms that you will need to know but they are not required right now. We will cover them in detail in the latter part of this article. For now, let’s create our very first GitHub repository!

git pull <remote-repo>


Step 1: Using cd command in GIT Bash, move to the project folder
Step 2: Using init command, initialise the GIT repo. 
	git init
Step 3: Configure GIT
	git config --global user.name "venky2k11"
	git config --global user.email "venky2k11@gmail.com"
Step 4: Add the file. The should exist in this location. It will get added to the repo. 
	git add "notes.txt"
Step 5: Check the status:
	git status

At this stage: We haven’t added the files to the local repo yet. We have just told Git that some changes were made and we want to save these changes in the next commit/save. As of now, these “added” files are in a place called the Staging area. 

Working Directory -> GIT add -> Staging area -> GIT commit -> Local Repo

Step 6: commit changes to local repository.
	git commit -m "Initial commit"
	
File is added to the local git repo. Check GIT status. Update something to the file and check the GIT status again. It should highlighted in red, the file changed. 
Add the fiel to git local repo and commit the changes. 

If the file is added but not yet commited to git repo, it will highlighted the file in Green. Example: modified:   notes.txt

Once commited, it will display "nothing to commit, working tree clean"

Step 7: Viewing commit logs:
	git log
	
Step 8: Create the repository in GitHub (called as Remote Repo)
Step 9: Add this remote repo
	git remote add origin https://github.com/venky2k11/learn.git
	
The command creates a connection between the local and remote repos. Once we do that, we no longer have to refer to the remote repo by the URL every time. We can just use the name origin to refer to the remote repo.

Step 10: Push changes to remote repo 
	git push -u origin master

This might fail if there are existing changes in remote repo which are not in your local. 
Use git pull origin <branch-name> to syn the changes and then push your changes. 
	git pull origin master --allow-unrelated-histories 
	
Step 11: New changes : For all further changes, following steps could be followed. 
	
	* Before making any changes, do a pull and check if there are any changes. 
	* Make the changes
	* Do a git pull origin master  to see if there are any changes. 
	* git add notes.txt
	* git commit -m "2nd time push"
	* git push -u origin master


Working with Branches: 

Step 1: Create a branch. This should be done staying in the master branch. 
	git branch b1
	
	git branch   -> this will return all the branches under this master. 

Step 2: Switch to the branch. 
	
	git checkout b1 
	
Inorder to move to master branch, use git checkout master  

Step 3: We could use "git status" to see the changes. git pull is used to bring changes from git by other users into my local repo. 

	git pull origin b1
	
Step 4: Make changes 
Step 5: use git add  to add the file to the repo 

	git add notes.txt
	
Step 6: commit the changes 

	git commit -m "message"
	
Step 7: push the changes 

	git push -u origin b1


If there was an error during git push due to file size error, use reset command to reverse the commits and then remove the error file and redo the process to add the file and commit and push. 

git reset --soft HEAD~1



Merge Branch with the Master:  For this we need to be in the master branch and use below commands:

Step 1: git merge b1 -m "message"

https://www.analyticsvidhya.com/blog/2020/05/git-github-essential-guide-beginners/?utm_source=AVLinkedin&utm_medium=post&utm_campaign=20_may_new_article

https://github.com/kunalj101/Data-Science-Hacks?utm_source=blog&utm_medium=git-github-essential-guide-beginners