## Module 3 - Revisions
[Main Page](README.md)

### Version Control Systems (VCS)

Records changes, person who modifed files and compares changes between original and changed file. 
- Local is stored on the hard drive on your computer. 
- Centralized is a single server that can be accessed by many clients to collobaborate without having a million local copies of a file. 
- Distributed was created to mitigate against single server failures. Mirrors repositories to back up data and prevent loss. 

### Git

- Git is a distributed VCS that stores snapshots (commits) of the file.

- View, apply or remove files.

- Keeps all your project files in one repository.

- Local Operations **Need to get this explained better in review**

- All changes are tracked by Git and corrupted files are detected in transit.

-  Minimizes file loss and file damage.

- States of Files in Git
  - committed data is stored in local db
  - modified data but not committed
  - staged files wait to be committed in the next snapshot. Think similar VMWare.

- Can be installed on Mac, Windows and Linux.
- Can have a GUI

- Competitors
  - SVN
  - Perforce

### Using Git

- Import a repository 
  - Change to target project's directory.
    ```cd test```
  - Initialize Git to create a new subdirectory .git and tracking has not started yet.
    ```git init```
  - Starts tracking with an intial commit that has a label that points to it. You can write a message in your commit to describe changes.
    ```git add *.c```
    ```git add LICENSE```
    ```git commit -m "insert a message here"```

- Clone an existing repository
  - clones all versions of files, creates a directory called first, initializes a .git directory, retrieves a working copy of the latest version of the project.
    ```git clone https://github.com/first```
  - this makes a copy of the target repsository to a new directory
    ```git clone https://github.com/first newdirectory```
    
- HEAD means you are here. Or the latest shanpshot.

### GitHub

- Your code, in the cloud. Where open source lives. Online code storage.

- Remote repository.

- Uses Git to track versions, review changes and keep changes separate until they are vetted for addition to official repository.

- Many Team members can work on same document.

- Competitors
  - BitBucket
  - Atlassian
  - AWS Code Commit
  - GitLab

### Workflow
- Local Repository on your local machine
  - Working Directory is where files live after you have checked out the version of the Repository.
  - Index is the area where they stage. Changes sit here until commits.
  - Head shows the most recent commit and checks back in to Repository as a new version.

- Saving Changes
  - Untracked files are not included in the last snapshots.
  - Tracked files can be modified, unmodified and staged. They are included in snapshot.

- Life Cycle of File Status
  - Git flags an edited file as modified during commit.
  - Stage modified files.
  - Commit staged changes.

- Check File Status of local repository
  - Determines state of files and tells you what files have changed since your last commit.
    ```git status```

- Tracking and Staging a File for Commit - adds files from working directory to staging area
  - Single file
    ```git add filename```
  - All Files
    ```git add *```

- Committing a File takes a snapshot - small frequent commits
  - After files are staged, commit changes and record what you did in the commit message.    
    ```git commit -m "made change x, y,z"```

- Committing All Changes
  - This commits all files in the working directory
    ```git commit -a```

- Pushing Changes
  - Changes pushed to remote repository. 
  - This pushes changes from the local master branch to the remote repository named origin.
    ```git push origin master```

- Stashing Changes
  - To save changes that you don' twant to commit yet, use command below. It temporarily removes changes and hides them. When ready to work
use second command.
    ```git stash```
    ```git stash apply```
    
### ACP GitFlow

- Add
- Commit
- Push

### Vocabulary
- VCS
- Git vs. Github
- local vs remote
- clone
- commit
- ACP
- deployment
