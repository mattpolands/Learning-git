# Learning-git

My goal is to record my notes and learning process as I familiarize myself with git and it's associated parts.

Once again I have to thank Pierian Training for its excellent tutorials. I cannot recommend them enough. Cost effective, clear, and concise and where I believe that they truly thrive is at the level of detail they offer (perfect for beginners like myself).

What is Github?
GitHub is a web-based platform for version control and collaboration that allows developers to host and manage their software projects. It provides a range of features and tools designed to facilitate project management, code sharing, collaboration, and version control.

Key features of GitHub include:

1. Version Control: GitHub utilizes Git, a distributed version control system, to track changes to source code files over time. Developers can create repositories to store their code and easily manage different versions or branches of their projects.

2. Collaboration: GitHub enables developers to work together on projects effectively. It offers features like pull requests, which allow developers to propose changes, review code, and merge changes into the main codebase. It also provides issue tracking, project boards, and wikis to facilitate communication and collaboration among team members.

3. Code Hosting: GitHub serves as a hosting platform for Git repositories. Developers can push their local repositories to GitHub, making them accessible to others. This makes it easier to share code with collaborators and provides a central, cloud-based location for code storage.

4. Social Features: GitHub has a strong social aspect, allowing developers to follow projects, star repositories they find interesting, and discover open-source projects. It fosters a community-driven environment, promoting collaboration and knowledge sharing among developers.

5. Integrations and Automation: GitHub integrates with a wide range of tools and services, such as continuous integration and deployment (CI/CD) systems, project management tools, code quality analyzers, and more. This allows developers to streamline their development workflow and automate various processes.

GitHub has become a popular platform for both individual developers and organizations, serving as a hub for open-source projects, private repositories, and collaborative development. It provides an accessible and user-friendly interface, making it easier for developers to manage their code, collaborate with others, and contribute to the larger developer community.

Repository Basics
- Source code management
- Understanding code repositories
- Cloning repositories

Updating code in Repositiory
- git status
- git add 
- git commit
- git diff 
- git push 
- git pull

The purpose of git is to be able to fluently work with others. Git does this by using branches that allow you to split off code development to others and then later bring back and merge that code into the main branch.

Undoing changes (rolling back code bases to a previous commit)
- git log
- git amend

Version Control Overview
- software used to manage and track changes in digital files
- version control system (VCS) allows us to track changes, undo changes, compare versions, and work with others
- GitHub (owned by Microsoft) integrates easily with git and allows you to have versions of your code “live” on the internet for you and others to access, update, and change from any machine
- git is an open source VCS software
- GitHub is a company that operates a service for hosting files on the internet that are managed using git
- git allows you to add save points to your work, create changes, update existing coded, undo changes, create branches for others to work on, and merge work together

MacOS Command Line Basics
- using command line at the terminal:
    - change directories (cd) then name of one of the listed directories
    - print current directory (pwd)
    - list files in current directory (ls)
    - clear terminal (clear)
    - to go back up a directory (cd ..)

Quick note, capital G Git typically refers to the entire project
While git is the actual program used

git was created by the creator of Linux, Linus Torvalds in 2005.
git doesn’t really have a true meaning 
GitHub was started in 2007
GitHub was acquired by Microsoft in 2018 for $7.5 billion

from terminal to confirm version git —version
https://git-scm.com/downloads or to update to most recent version
in terminal git clone https://github.com/git/git

Preferred text editor VS Code
https://code.visualstudio.com/

github.com

Check current configuration in terminal
git config user.name >>> mine is mattpolands
git config user.email >>> matthewpoland@icloud.com

Can set the configuration or change 
git config —global user.name “user”
git config —global user.email “email”

A repository (also called repo) is the main place we track changes and manage our files that are using Git

Example of a public repository https://github.com/tensorflow/tensorflow

.md = markdown file - allows you to stylize text
Good practice is to label file that explains the project and talks about the repository as README.md
This is also a good place to rules for contributions and additional resources (ex Tensorflow has links to classes)

How to create a Git Repository
in terminal type git init
- this command initializes a Git Repository on your local machine
- you only need to run this command once per project
- creates a hidden folder .gitdirectory which holds all the information about the VCS

command git status
- will report back the status of you Git repository
- a good command to let you know if you are actually in a directory that is acting as a Git Repository

Upon creating a Git Repository all the folders/directories inside will also be part of that Repository (ie all the changes are tracked)
**The reason this is key is because you do not want to rerun git init within a .git. This will cause changes to be tracked within a file that is tracking changes (inception). It can get sloppy.

mkdir (make directory)

How to clone (copy/get) public repository to local machine
- can download from GitHub under “Code” button as zip file
- open via GitHub Desktop
- or use HTTPS and get copy of URL

Via HTTPS copy link > go to Terminal **again use git status to ensure that you are not already in a repository > post git status the terminal should say fatal: not a git repository > then type git clone “paste copied url”

How to clone and protect a private repository
- option 1: create Personal Access Tokesn (PAT) on github.com 
    - when using the git clone command, reference the PAT
        - go into settings > develop settings (bottom left) > PAT (classic) > generate new token > name, expiration date, click “repo” > generate > copy PAT > in terminal git clone https://token@github.com/account/repo.git (token is actual PAT)
- option 2: use the GitHub Desktop Tool GUI
    - open the Github Desktop Tool
    - Login with GitHub username and password
    - clone repo via GUI

Code repository is really three parts:
	1. working directory
	2. staging area
	3. repository

Key commands
- git add - changing code in a repository
- git commit - committing these changes
- git push - pushing changes
- git pull - pulling changes
- git log - checking logs
- git diff - checking changes

Review on basic workflow
- create repo on GitHub then git clone to bring copy to our local machine
- or git init to initialize a repo on our local machine

Workflow:
initial project> add code (“commit”)> add more code (ie commit, ie informing git about specific changes)
*commit is like a checkpoint in a video game
a Git commit doesn’t just pertain to saving changes in a single file, it can constitute specific changes across an entire working directory

Example:
Create directory on local machine> we call it “my website” (this is the ‘working directory’ part of the repository)> add several files (examples program.py, index.html, style.css) to our working directory> we want to make this permanent (add officially to our repository)> git add filename (example program.py), key this virtual space is the ‘staging area’ part of the repository> git commit filename, adds it officially to the repository (this is telling git to make these changes to the .git log file)> the git push, pushes it to GitHub

Can label the commit for future reference
- example git commit -m “example message”
- -m stands for message
- this message will be viewable for everyone to see so they understand reason for commit

*Just because something is in your working directory doesn’t mean that it is in your repository
Not until it has been committed to the repository
Once it is committed to the repository then it can be pushed to GitHub

git pull is the reverse process 
- pulling from GitHub to your local machine

In Visual Studio> Code> Preferences> Settings> Search Settings “files exclude”
- in future may want to add **/.git to make these files hidden to make things less messy
- took it out for now while learning

In Visual Studio how to add to the working directory
- create an empty desktop folder
- open VS
- open folder via VS
- open New Terminal under Terminal
- good practice always check git status prior to git init 
    - again it is bad practice to open a working directory within a working directory
- git init (we have now initialized our working directory (our example Learning git)

In VS how to add file
- Click on Learning git in the left hand corner and click new file icon
- name in left column
- add message in text editor

Green colored file names label files that have yet to be committed
Can add multiple files at one time just need to have a space between each file name
git add . (this adds all files that you have been working on that you have yet to commit into the staging area)

git log command will show a list of all the commits made to a repository, including the hash, message, and metadata
- it is the history of a repo

Checking for remote branches:
- git remote -v
- -v (stands for view) 
- running this command on a cloned repo will allow you to view the URL of the remote branch

Adding remote branch:
- git remote add name https://url.git
- this remote branch is called the origin branch
- git remote add origin https://url.git
- you replace the .git URL with the .git URL from the repository you created

To rename origin branch:
- git remote rename <old name> <new name>

To end remote branch
- git remote remove <name of branch>

Once we have connected to our remote branch on GitHub, we can push our code to the remote branch
- we tell git to push to the remote main/master branch called origin with the command:
    - git push -u origin main/master

*GitHub use to call origin branch master branch but have for politically correct reasons changed it to main branch
*git still operates using master so need to change this:
	- git branch -M main

Create new repository in GitHub
Then back to VS 
Then in terminal in VS:

git remote add origin https://“token”@github.com/mattpolands/Learning-git.git
git branch -M main
git push -u origin main

Forks let you make changes to a project without affecting the original repository (also called the “upstream” repository)
You can fetch updates from the upstream repository
You can propose changes to the upstream repository with pull requests


##More to come
