pwd = see directory path
ls = see file in path directory
# Editing a file
nano finance.csv
Use nano to:
delete,
add,
or change contents of a file
Save changes: Ctrl + O
Exit the text editor: Ctrl + X
echo —create or edit a file
Create a new file todo.txt
echo "Review for duplicate records" > todo.txt
Add content to existing file todo.txt
echo "Review for duplicate records" >> todo.txt
# Checking Git version
git --version
# Accessing the .git directory
ls
data report.md
ls -a
. .DS_Store data
.. .git report.md
# Modifying a file (">>" means to a specific file")
echo "Mean age is 32 years old, with a standard deviation of 6.72" >> summary_statistics.txt
# nano report.md
# Mental Health in Tech Survey
TODO: write executive summary.
TODO: include link to raw data.
Save using Ctrl + O and Ctrl + X
# Saving a file
Adding a single file
git add report.md
Adding all modified files
git add .
. = all files and directories in current location
Making a commit
git commit -m "Updating TODO list in report.md
Check the status of files
git status
on branch main
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
modified: report.md
git commit -m "New TODO in report.md"
# See Changes
    SummaryCommandFunction
    git show HEAD~1Show what changed in the second most recent commit
    git diff 35f4b4d 186398fShow changes between two commits
    git diff HEAD~1 HEAD~2Show changes between two commitsgit annotate fileShow line-by-line changes and associated metadata
# Identifying branches
    git branch  
# Creating a new branch
    git checkout -b report   
Changes per document by line
    git Annotate report.md
    #INTRODUCTION TO GIT
    #SummaryCommandFunction
    git show HEAD~1 Show what changed in the second most recent commit
    git diff 35f4b4d 186398f Show changes between two commit
    git diff HEAD~1 HEAD~2S how changes between two commitsgit annotate fileShow line-by-line changes and associated metadata
 # INTRODUCTION TO GIT The HEAD shortcut
    git diff -r HEADCompares staged files to the version in the last commit
    Use a tilde ~ to pick a specific commit to compare versionsHEAD~1 = the second most recent commitHEAD~2 = the commit before that
    Must not use spaces before or after the tilde ~
# Unstaging a single file in GitTo unstage a single file:
    git reset HEAD summary_statistics.csvnano summary_statistics.csv
    git add summary_statistics.csv
    git commit -m "Adding age summary statistics"
# Undo changes to an unstaged file
    Suppose we need to undo changes to a file in the repository
    git checkout -- summary_statistics.csv 
    checkout means switching to a different version 
    This means losing all changes made to the unstaged file forever
 # Undo changes to all unstaged files
    git checkout .
    
# Customizing the log output
   We can restrict the number of commits displayed using -:
    git log -3 To only look at the commit history of one file:
    git log -3 report.md
# Customizing the log output
    Restrict git log by date:
    git log --since='Month Day Year'Commits since 2nd April 2022:
    git log --since='Apr 2 2022'Commits between 2nd and 11th April:
    git log --since='Apr 2 2022' --until='Apr 11 2022'
  
 # Restoring an old version of a file
    git checkout -- filename To revert to a version from a specific commit:
    git checkout dc9d8fac mental_health_survey.csv This was the second to last commit, so another approach is:
    git checkout HEAD~1 mental_health_survey.csv
 # Restoring a repo to a previous state 
    git checkout dc9d8facAlternatively:git checkout HEAD~1
# Levels of settings
    git config --list
    Git has three levels of settings:
    1. --local: settings for one specific project
    2. --global: settings for all of our projects
    3. --system: settings for every users on this computer
# Changing our settings
    git config --global setting value
    Change email address to johnsmith@datacamp.com:
    git config --global user.email johnsmith@datacamp.com
    Change username to John Smith:
    git config --global user.name 'John Smith'
    If we don't use '' and our user.name has a space:Git would save user.name as John
# Using an alias
    Set up an alias through global settings
    Typically used to shorten a commandTo create an alias for committing files by executing ci:
    git config --global alias.ci 'commit -m'
    Again, we use '' so Git processes characters after the space
    We can now commit files by executing:git ci
# Creating a custom alias
    We can create an alias for any commandIf we often unstage files:
    git config --global alias.unstage 'reset HEAD'
    Be careful not to overwrite existing commands!
# Tracking aliases.
    git
    config file
    git config --global --list
    Output format: 
    alias.aliasname=command
    alias.ci=commit -malias.unstage=reset HEAD
 # Ignoring specific files
    nano .gitignore
