# The Git Tutorial Reading Notes
Version control is an archive sort of, it lets you revisit previous file versions and even revert a file back to it's previous version. Making mistakes not so final and making a stressful undertaking not so stressful.
### The Variants and History of VC
#### Local Version Control

Back in the day, a VCS could only be kept locally and it was one database that stored file history and information. It was called Local Version Control (LVCS)

#### Centralized Version Control
With growing developer teams, collaborative coding became more popular and demanded the need for a Centralized Version Control or (CVCS) one server stores all the file changes and versions and it can be accessed by multiple people, it made collaborative coding a lot easier and more efficient.

#### Distributed Version Control
This adaptation of Version Control changed the single server weakness of it's previous iteration, making it a lot less probable to potentially lose all your files.

## What Is Git
Git is essentially a DVCS that saves your work in snapshots, each time you 'commit' or save your work, Git saves the snapshot of what you had.

Git uses a local disk to make getting a file's information quicker and more efficient.

Git is also optimized to prevent or minimize the loss of data and information, when you commit to a change in Git, rarely will that information be lost.

## Git's Gui and Repositories
While Git does utilize a GUI, it allows the freedom to use a third party if need be.

Cloning a file copies all of it's version, and brings forth the most recent iteration 

Repositories have three parts
1. Working Directory- This is where all your files are.
2. Index- The area used for staging, the step before committing 
3. Head: Points to the most recent commit, in  other words the most recent version of a file

## Other Information
You can stash a commit by using the command 'git stash' you can use it for when you aren't ready to make your changes yet. You can then use 'git stash apply' when you are ready to apply your changes.

You can use remote repositories for collaborative projects, you can allocate read and write or read-only privileges.

You can run the 'git remote' command it lets you see short names for remote handles.

To see the whole url for remotes you can use the command 'git remote -v' and see the whole name for a remote.


