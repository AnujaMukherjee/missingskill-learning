## Introduction of Git 

### Git -> Version Control System 
<p> * Git Is a version control .It is a software use to track the local file.  </p>
<p>*  Gitlab and Github are Remote code repository where all other developer push there git initiallized local repo . And with the help of github and git lab developers can work collaboratively. </p>
 </p> * git basically work on 3 stages first step is working stage where we can locally modified our codes, after that we use "git add" so our code goes from working area to stagging area . From stagging area we do final commit, which is the last step and it puts a snapshot of whatever was there in the staging area as a permanent commit/version. Hence the name Version Control. Then obviously we can do "git push origin master to push all our commits into the remote repo present in GitHub or GitLab. </p>
<p> * if we wants to gets any update or if our team menbers  change something on there local repository and push it to remote repository now next dayt if I am working on the same project first thing I have to do that is git clone so that all the latest commit and updates  are fetch to my local repo </p>
<p> * Git is a <b>Distributed Version Control System </b>
which basically helps us to restore our mistakes by allowing us to checkout to any of previous commits, anytime we want.</p>
 <p> * Furthermore, git helps us to work with multiple people, on the same file on the same time, which is a superpower when it comes to developing something. </p>
        


### Difference  between Centralized Version Control and Distributed Version Control

|Centralized Version Control|Distributed Version Control|
|---|---|
| In CVS, all the projects , files and directories, are in remote server so in the time of cloning we can clone only that files  which we want to work upon instead of cloning the entire project. So, none of the developer working on that remote repo actually has the entire project(with all its versions) in their local machine. | In DVS, entire project(with all its versions) will be cloned into the local machine of each  of the developers working in that remote repo regardless of whether or not a given developer will ever need to open the files he is not working with. So the benefit is that, each developer gets the full copy of the project.|
| Suppose in remote repo  there is a flipkart project  inside that we have thousands of js files , html files among this "A" is working on login.js file so that time of cloning if it is CVS then  in local repo login.js will clone | suppose  in remote repo  there is a flipkart project  inside that we have thousand js files , html files among this "A" is working on login.js file so that time of cloning if it is DVS then  in local repo entire flipkart project will clsone "A" user gets the other js like  tanscation.js , product.js etc|
| In CVS if developer "A" and developer "B" both are working on same js file , both are working on "product.js" "A" and "B" both makes some changes  and push them into remote repo. Now, the problem which arises is, that it will show the changes of the last person who pushed in remote repo. If "B" pushed last, then B's changes will overwrite the changes pushed by "A" on the same file, thus we lose on the modifications done by "A", becasue of the RACE CONDITION.| In DVS, if developer "A" and developer "B" both are working on same js file let's say, "product.js" and "A" and "B" both makes their own  contribution to the same "product.js" file and when both A and B try to push their own version of the product.js file to the remote repo, then the beauty of DVS is such that, it does not allow that to happen. How? => Let's say first A pushed, then if B tries to push, B will get an error saying "Cant Push, because remote is ahead by one commit, so you need to take pull first". And when B takes pull, then he gets A's code in his local machine. Now he can then solve the merge conflits to finally end with a code which has the best parts of both A and B. 
- <b>git branch :- </b> <p> * git branch commands is used to create a branching .</p>
  <p> * It will show us that which branch  currently we are . basically it will shows us default branch name which is 'master' branch where last commit is done .</p> 
  <p> * branch pointer pints to latest commit 
  <p> * now if we want to create a new branch from Master branch .</p>
  <p> * now if we want to create a new branch from master branch .</p>
  <p> * git branch feature [branch name] </p>

- <b> git checkout:- </b>  if we want to move our pointer from master branch to feature branch then we used this command .Switch the branch to given branch 
 
   - <p>git checkout feature </p>
          <p>master </p>
          * feature

        
- <b>git fetch :- </b> latest difications in remote Repository are informed to local  repository. get the changes  from origin server. 
- <b> git pull ;- </b>  local repository picks up the changes from remote repository and integrates it. get the changes  from origin server and merge into current server    
     * git pull origin master  // all chsnges from remote repository are pulled and intigrate to local repository 
 - <b> git log:- </b> it shows  where the head pointer is now pointing 
 - <b> git diff :- </b> After commit if any updation done on local or Remote Repo  "<i> gitt diff </i> "commands show that diff that how many line uploads or delete 
 
 - <b> git reset :- </b> undo the changes .
         
    -  <p>$ touch newfile1</p>
          <p>$ git add newfile1 </p>
          <p> $ git status -> newfile is indicated as file yet to be committed </p>
          <p> $ git reset</p>
          <p> $ git status -> newfile1 is indicated as untracked file yet to be added to staging area .
- <b>git clone :- </b> Create a local working copy of remote repo 
- <b> git  stash :- </b> Save the current change in local repo managed internally by git 

  - git stash
  - git stash pop 
  - git stash list 

- <b>git show :- </b>  show the changes of latest commit 

    - git show <commit-id> => show the changes of that commit 

- <b> git config :- </b>  set the user config in global  config and local config .
 - <b> git push :- </b> push the commit history to remote origin server 
      
      - git push origin <master(branchname)>
## CVS
<img src="cvs.jpg" >

## DVS
<img src="dvs.jpg" >  
