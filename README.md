# Git
 

## 1. What is Git

It is a free and open-source version control system used to handle small to very large projects efficiently. 

Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.


#### A short history of Git ####

The Linux kernel is an open source software project of fairly large scope.  During the early years of the Linux kernel 

maintenance (1991–2002), changes to the software were passed around as patches and archived files. In 2002, the Linux kernel 

project began using a proprietary DVCS called **BitKeeper**. In 2005, the relationship between the community that developed 

the Linux kernel and the commercial company that developed BitKeeper broke down, and the tool’s free-of-charge status was revoked. 

This prompted the Linux development community (and in particular Linus Torvalds, the creator of Linux) to develop their own tool 

based on some of the lessons they learned while using BitKeeper. In 2005, the Linux kernel community began using Git as their 

version control system, and other open-source projects soon followed.


## 2. A short history of Version Control Systems  ##

- **SCCS** (Source Code Control System) - 1972.
  Version control system designed to track changes in source code and other text files during the development of a piece of software.
  It was originally developed at Bell Labs beginning in late 1972 by Marc Rochkind for an IBM System/370 computer running OS/360.
  Only single user can work simultaneously on SCCS.
  **Only for Unix**

- **RCS** (Revision Control System) - 1982.
  Is an early implementation of a version control system (VCS)  
  It is a set of UNIX commands that allow multiple users to develop and maintain program code or documents. 
  With RCS, users can make their own revisions of a document, commit changes, and merge them. 
  RCS was originally developed for programs but is also useful for text documents or configuration files that are frequently revised.

- **CVS** (Concurrent Versioning System) - 1986.
  Is a version control system originally developed by Dick Grune in July 1986. 
  CVS operates as a front end to Revision Control System (RCS), an earlier system which operates on single files. 
  It expands upon RCS by adding support for repository-level change tracking, and a client-server model.
  Several users can work simultaneously on CVS.

- **SVN** (Apache Subversion) - 2000.
  Software developers use Subversion to maintain current and historical versions of files such as source code, 
  web pages, and documentation. Its goal is to be a mostly compatible successor to the widely used Concurrent Versions System (CVS). 

  Features:
	- Native support for binary files, with space-efficient binary-diff storage
	
	- The system maintains versioning for directories
	
	- Branching is implemented by a copy of a directory, thus it is a cheap operation, independent of file size

- **Git** - 2005.

  Features:
	- **Distributed** version control system

	- Reliable: providing a central repository that is being cloned each time a User performs the Pull operation, 
	  the data of the central repository is always being backed up in every collaborator’s local repository

	- Git is compatible with all the Operating Systems that are being used these days

	- Non-linear Development: allows users from all over the world to perform operations on a project remotely

	- Speed

	- Open-Source
 
  Contra:
    - Not good with big binary file

	- Movies, images...


## 3. What is the difference between Centralised and distributed version control

A distributed version control system enables every user to have a local copy of the running history on their 
machine, so if there's an outage, every local copy becomes a backup copy and team members can continue to development offline. 
There is **no main repository.**


## 4. Git  and GitHub are the same?
Git is a version control system,  GutHub is a service for hosting of the Git repositories.       


## 5. Git config  ##

#### git config levels and files ####

  **--local:** For writing options: write to the current repository .git/config file. This is the default behavior.

  **--global:** Global level configuration is user-specific, meaning it is applied to an operating system user.

  **--system:** System-level configuration is applied across an entire machine. This covers all users on an operating system and all repos. 

  One of the first things you did was set up your name and email address:

	```
	$ git config [--global | --local | --system] user.name "John Doe"
	$ git config [--global | --local | --system] user.email johndoe@example.com
	```
 
  other useful setting is text editor to prompt for further input. For VS Code use:

    ```
    git config [--global | --local | --system] core.editor "code -"
	```

  You can edit .git/config file manually with any text editor:

    ```
	[core]
		repositoryformatversion = 0
		filemode = false
		bare = false
		logallrefupdates = true
		symlinks = false
    ```

  Get all config file entries:  ``` git config --list [--global | --local | --system] ```


## 5.1 What is a “.gitignore” file

Introduce file or folders to exclude from a project. 
These files will not be affected by Git commands bit will be exist in working directory.


## 6. Git init  ##

  **git init** create an empty Git repository or reinitialize an existing one.
  It can be used to convert an existing, unversioned project to a Git repository or initialize a new, empty repository. 
  Most other Git commands are not available outside of an initialized repository, so this is usually the first command 
  you'll run in a new project.

  Executing git init creates a **.git subdirectory** in the current working directory, which contains all of the necessary 
  Git metadata for the new repository. This metadata includes subdirectories for objects, refs, and template files. 
  A HEAD file is also created which points to the currently checked out commit.


## 7. Bare repositories ##
  
   ```--- git init --bare ```	Initialize an empty Git repository, but omit the working directory. 
   
   Shared repositories should always be created with the --bare flag. The --bare flag creates a repository that doesn’t have a working directory, 
   making it impossible to edit files and commit changes in that repository. You would create a bare repository to git push and git pull from, 
   but never directly commit to it. 


## 8. Git concepts and architecture

Git however uses a three-tree architecture:

 - Repository (being tracked by Git)

 - Staging index (containing changes that are about to be committed into the repository)
 
 - The Working Tree (containing changes that may not be tracked by Git)

We added, then we committed, it was a two-step process. When we made our first commit, we didn’t just perform a commit. 
First, we used the add command. We added, then we committed. 
It was a two-step process (added our files to the staging index, and then from there we committed to the repository).


## 9. Saving changes (Git add)

The commands: git add, git status, and git commit are all used in combination to save a snapshot of a Git project's current state:
There are simple three steps for the main flow:

**Make changes => Add the changes => Commit changes to the repository with a message**


## 10. Git commit hash value

Commit is the way to save changes to a branch. The snapshot of the current state is created. 
The commit object contains a tree of blob objects and other objects which represent the commit (snapshot). 
The snapshot can be used to revert branch to that state.  
In Git, every commit you make is assigned a unique SHA-1 hash value. This hash value is like a fingerprint for each commit.
It helps Git keep track of every change made in the repository. Git uses a specific type of hash value known as SHA-1.
Every time you commit changes, Git generates a unique hash value. 
This value is a SHA-1 hash of the commit’s contents, including its code changes and metadata(author, date, commit message...)
Think of these hash values as unique IDs. They allow Git to track each commit individually. 
This tracking is what enables Git’s powerful version control capabilities.

**Summarize:**

 - Gite generates a checksum for each change set. Checksum algorithms convert data into a simple number.
   The sama data always equals same checksum 

 - Data integrity is fundamental. Changing data will change checksum.

 - Git uses SHA-1 hash algorithm to create checksums: 40-character hex string. 


## 10.1 How to create an empty commit

``` git commit –allow-empty  -m “message” ```


## 11. HEAD

HEAD can be termed as a special ref that points to the current commit. 
However, HEAD can change depending on the latest commit that we have checked out in our git directory. 

``` git show HEAD ``` - To verify the HEAD status use this command and it will also show the HEAD location.

We can check out our HEAD in the .git/HEAD file. It will contain, for ex:

``` ref: refs/heads/main ```

#### Detached HEAD ####

In rare cases, the HEAD file does NOT contain a branch reference, but a SHA-1 value of a specific revision. 
This happens when you checkout a specific commit, tag, or remote branch. 
Your repository is then in a state called **Detached HEAD**

#### How to fix a *detached head*

Create a new branch from the detached HEAD state.


## 12. Git log

Show commit logs. The output is given in reverse chronological order by default.

#### Commit Limiting ####

  -n <number>: Limit the number of commits to output

  --since=<date> --after=<date>: Show commits more recent than a specific date

  --until=<date> --before=<date>:  Show commits older than a specific date

  --author=<pattern> --committer=<pattern>:  Limit the commits output to ones with author/committer

  --grep=<pattern>: Limit the commits output to ones with a log message that matches the regular expression 

  --graph: Displays the commits history in graphical view

  ... many others...

#### Commit Formatting ####

 --oneline: This is a shorthand for "--pretty=oneline --abbrev-commit" used together

 ... many others...


## 12.1 What is git reflog

Manage reflog information.

Reference logs, or "reflogs", record when the tips of branches and other references were updated in the local repository. 

Reflogs are useful in various Git commands, to specify the old value of a reference. 

``` git reflog --all ``` : Show of all changes made to repo.        


## 13. Git status

 The **git status** command displays the state of the working directory and the staging area. 
 It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git. 
 Status output does not show you any information regarding the committed project history.

 --short: Give the output in the short-format.


## 14. Git diff
Diffing is a function that takes two input data sets and outputs the changes between them. 
git diff is a multi-use Git command that when executed runs a diff function on Git data sources. 
These data sources can be commits, branches, files and more.

Branch1  <=> Branch2 :  ``` git diff <branch>  <branch> ``` 

Commit1 <=> Commit2 :  ``` git diff  sha1  sha2 ``` 

Working tree <=> Staging area :  ``` git diff ``` 

Staging area <=> Repository   :  ``` git diff  --staged | --cached(legacy) ```

	```
	git diff
	diff --git a/diff_test.txt b/diff_test.txt
	index 6b0c6cf..b37e70a 100644
	--- a/diff_test.txt
	+++ b/diff_test.txt
	@@ -1 +1 @@
	-this is a git diff test example
	+this is a diff example
	```


## 15. Delete files

git -rm - Remove files from the working tree and from the staging area. This command is opposite to *add*

rm --cached: removal should happen only on the staging area.	

  -r: Recursively removes folders

  --dry-run: only see an output of the files that Git would remove, but no files are actually deleted.


## 16. Rename files

**git mv** - Move or rename a file, a directory, or a symlink


## 17. Removing the Untracked files: git clean

**git clean:**  Remove untracked files from the working tree

Cleans the working tree by recursively removing files that are not under version control, starting from the current directory.

  -f:  forces the removal of untracked files. Directories and ignored files are left alone

  -d: forces removal of untracked git directories
  
  -x: removes untracked files that map to .gitignore entries.

  -i | --interactive:  Show what would be done and clean files interactively

  -n |--dry-run: Don’t actually remove anything, just show what would be done


## 18. Cancel changes in Working Tree: git restore

**git restore:** Restore working tree files, **--worktree** flag can be added, but it is by default.

```git restore <file> ``` : remove all the changes that are not staged for commit. 

Or you can use old command:  ```git checkout -- <file>```    


## 19. Cancel changes in Staging Area: git restore --staged

**git restore** --staged: Specifying --staged will only restore the staging area.


``` git restore --staged <file>... ```

Note: Specifying --staged AND --worktree: restores both working tree and staging.

Or you can use reset command:  ``` git reset HEAD <file>... ```


## 20. Change last commit in repository: git commit --amend

``` git commit --amend ```  Replace the head of the current branch by creating a new commit.

Previous commit will be deleted, new commit with the new SHA1 will be created.

--no-edit: do not ask to write(change) commit message


## 20.1 How to ignore changes in a tracked file: –assume-unchanged

``` git update-index –assume-unchanged <filename> ```


## 21. Get previous version of the file from repository

Or you can use old command:  ``` git chechout SHA1 <file>... ```


## 22. Revert last changes: git revert

``` git revert``` :  Revert some existing commits.  

This requires your working tree to be clean (no modifications from the HEAD commit).
Note: git revert is used to record some **new commits** to reverse the effect of some earlier commits (often only a faulty one).

If you want to throw away all uncommitted changes in your working directory, you should see **git reset**


## 23. Git reset

 --soft: do not change staging index and working tree. Reset only repository. 
 --mixed(default):  changes staging index to match repository, does not change working directory 
 --hard: changes staging index and repository and working folder


## 24. Git clone

**git clone** Clone a repository into a new directory

Clones a repository into a newly created directory, creates remote-tracking branches for each branch 
in the cloned repository, and creates and checks out an initial branch that is forked from the cloned 
repository’s currently active branch.
Local repositories also can be cloned.

```git clone -b <branch> --single-branch  repository-url  branch``` : clone only songle branch  

``` --depth <depth> ```  : clone only last M commits


## 25. Git stash

**git stash** : Stash the changes in a dirty working directory away

- push: Save your local modifications to a new stash entry and roll them back to HEAD (in the working tree and in the index) 

- pop: **Remove** a single stashed state from the stash list and **apply** it on top of the current working tree state

- apply:  Like pop, but **do not remove** the state from the stash list

- list: List the stash entries that you currently have

- clear: Remove all the stash entries

- u: Add untracked files to the stash also

- a: Add files from .gitignore to the stash also

- drop:  Remove a single stash entry from the list of stash entries

``` git stash save "name" ```  : store stash with the name.

``` git checkout <stash-id> -- <filename> ```  : get from exact stash exact file


## 26. Git Merge vs Rebase

Merge can be **fast-forward** – target branch is updated to the latest commit of the source branch  
or **three-way merge**: branch histories are combined into a new commit.

- Merge: creates a new “merge commit” in the feature branch that ties together the histories of both branches.
        
      Pro: Merging is nice because it’s a non-destructive operation. 
           The existing branches are not changed in any way. This avoids all of the potential pitfalls

      Contra: Feature branch will have an extraneous merge commit every time you need to incorporate upstream changes. 
              If main is very active, this can pollute your feature branch’s history quite a bit.


- Rebase: moves the entire feature branch to begin on the tip of the main branch, effectively incorporating all of the new commits in main.

      Pro: you get a much cleaner project history. This makes it easier to navigate your project with commands like git log

      Contra: Rebase makes you resolve conflicts in the order they were created to continue the rebase. 
              Unfortunately, this means more work for you, as you may need to fix the same conflicts repeatedly


## 27. What is a conflict in Git

Occurs when two branches have made changes to the same lines in a file OR one branch deletes a file and another modifies it. 
The developer must manually resolve the conflicts.




## 28. What is branch, create/switch

It is the way to isolate development work on a separate task (new feature or bugfix). 
The changes in branch will not affect to main master branch (or other branches).

	```
	git branch <name>    
	git switch <name>       
	
	```

## 29. How to delete a branch

``` git branch –d <name> ```  :  Delete local branch (not active for now)

``` git branch –D <name> ```  :  Delete local branch which is not fully merged

``` git push –d  origin <name> ```  : Delete remote branch 


## 30. How to rename a branch

``` git -m <newname>  ```  : Rename current branch

``` git -m  <oldname> <newname>  ``` : Rename other branch


## 30. Branches test site
https://learngitbranching.js.org/


## 31. How to list all the remote repositories

``` git remote ```       : List of short names

``` git remote –v  ```   : List of short names + URL (fetch + push)


## 31.1 How to list remote branches    

``` git branch –r ```


## 32. git fetch VS git pull 

git pull:  fetch PLUS integrate changes to current active branch

git fetch:  downloads updates from a remote to your local without integrating them to local branches.


## 33. GitFlow

GitFlow – master branch, develop branch, feature branches, hotfix branches, release branches.


## 34. How to handle huge binary files in Git

Git LFS is a Git extension for working with large files in a separate Git repository. 


## 35. What is git ls-tree

List the content of the given tree object:   ``` git ls-tree –r HEAD ```


## 36. What is git hooks

They are scripts that are executed after a specific event occurs in a Git repository. 

Server/Client hooks:  inside .git/hooks folder.  

For example: hook commit-msg to check commit message on client side.


## 37. What is SubGit

Tool for managing Git repositories with Subversion history. 
It allows you to keep Subversion history while moving to Git. It will help you to migrate from SVN to Git.


## 38. Explain git attributes  (inside file .gitattributes)

gitattributes - Defining attributes per path. A gitattributes file is a simple text file that gives attributes to pathnames.

Use the .gitattributes file to declare changes to file handling and display, for ex:

 - Collapse generated files in diffs

 - Create custom merge drivers.

 - Create exclusive lock files to mark files as read-only.

 - Change syntax highlighting in diffs.

 - Declare binary file handling with Git LFS.

 - Declare languages used in your repository.


## 39. What is ‘git archive’    

Create git archive from current working tree.


## 40. git bisect 

Make binary search in the commits history. Steps: 

 - git bisect start        
 
 - Check HEAD commit and set as *bad*:   git bisect bad   

 - Check commit and set as *good*:  git bisect good <sha1>

 - git starts binary search – somewhere between bad and good, make checkout and you can test this commit.

 -  If it’s still bad – tell git about it: git bisect bad OR git bisect good

 -  After all call git bisect reset


## 41. Git tag

Tag marks an important point in a repository’s history. Git supports two types of tags:

 - **Lightweight** tags point to specific commits, and contain no other information. 
   Also known as soft tags. Create or remove them as needed.  ``` git tag <name>  ```

 - **Annotated** tags contain metadata, can be signed for verification purposes, and can’t be changed.



``` git tag –l``` : list of tags       

``` git show <tagname> ```    

 By default tags will not be pushed to origin, must push with flag –tags:   ``` git push –tags ```


## 42. How to change the URL of remote repository

``` git remote set-url <renotename>  <remoteurl> ```

## 43. What are submodules in Git

Submodules enable of the Git repo within the another as a subdirectory. 
For ex: integrating external project or lib into your project.

``` git submodule update -remote ```  : Fetch  and update your submodules

