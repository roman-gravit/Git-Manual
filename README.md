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

- **SCCS** (Source Code Control System) - 1972
  Version control system designed to track changes in source code and other text files during the development of a piece of software.
  It was originally developed at Bell Labs beginning in late 1972 by Marc Rochkind for an IBM System/370 computer running OS/360.
  Only single user can work simultaneously on SCCS.
  **Only for Unix**

- **RCS** (Revision Control System) - 1982
  Is an early implementation of a version control system (VCS)  
  It is a set of UNIX commands that allow multiple users to develop and maintain program code or documents. 
  With RCS, users can make their own revisions of a document, commit changes, and merge them. 
  RCS was originally developed for programs but is also useful for text documents or configuration files that are frequently revised.

- **CVS** (Concurrent Versioning System) - 1986
  Is a version control system originally developed by Dick Grune in July 1986. 
  CVS operates as a front end to Revision Control System (RCS), an earlier system which operates on single files. 
  It expands upon RCS by adding support for repository-level change tracking, and a client-server model.
  Several users can work simultaneously on CVS.

- **SVN** (Apache Subversion) - 2000
  Software developers use Subversion to maintain current and historical versions of files such as source code, 
  web pages, and documentation. Its goal is to be a mostly compatible successor to the widely used Concurrent Versions System (CVS). 

  Features:
	- Native support for binary files, with space-efficient binary-diff storage
	
	- The system maintains versioning for directories
	
	- Branching is implemented by a copy of a directory, thus it is a cheap operation, independent of file size

- **Git** - 2005

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