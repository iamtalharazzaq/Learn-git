# __Overview of Git and GitHub__
Git is a distributed version control system designed to track changes in source code during software development. It enables multiple developers to work on the same project simultaneously by using branches and merging changes. Git maintains a complete history of all changes made to a project, allowing developers to revert to previous versions, compare changes, and collaborate without conflicts.

GitHub is a cloud-based platform built on top of Git that provides a web interface for hosting and managing Git repositories. It enhances Git’s capabilities with additional features such as pull requests for code review, issues for tracking tasks and bugs, and project boards for project management. GitHub also supports continuous integration and deployment with GitHub Actions, and it fosters a vibrant community where developers can share, contribute to, and collaborate on projects.

### Key Differences Between Git and GitHub
* __Functionality:__
    * __Git:__ A tool for version control, allowing local and distributed management of code changes.
    * __GitHub:__ A platform for hosting Git repositories with additional collaboration features and a user-friendly web interface.
* __Usage:__
    * __Git:__ Used locally on your computer to manage project history and coordinate work between multiple developers.
    * __GitHub:__ Used online to share repositories, collaborate on projects, and utilize enhanced features for project management and workflow automation.

## __Version Control System (VCS)__
A Version Control System (VCS) is a software tool that helps developers manage changes to source code over time. It keeps track of every modification to the code in a special database. If a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the mistake while minimizing disruption to all team members. 

* __Functionalities of a Version Control System (VCS)__
    - __Tracking Changes:__ Records every modification to files, documenting who made changes and why.
    - __Collaboration:__ Allows multiple developers to work simultaneously on the same project without overwriting each other’s work.
    - __Branching and Merging:__ Enables the creation of branches to work on new features or fixes independently, and later merging them into the main codebase.
    - __Reversion:__ Provides the ability to revert files or projects back to a previous state to undo mistakes.
    - __History and Audit:__ Maintains a comprehensive history of changes, facilitating debugging and accountability.
    - __Backup and Restore:__ Acts as a backup system by recording all changes, allowing restoration of the project to any previous state.

 * __Benefits of Using a Version Control System__
    * __Enhanced Collaboration:__ Facilitates teamwork and coordination among multiple developers.
    * __Improved Code Quality:__ Supports code review processes and the integration of changes, leading to higher quality code.
    * __Time Efficiency:__ Saves time by enabling quick identification and reversion of problematic changes.
    * __Project Management:__ Helps manage large projects by keeping track of all changes and ensuring everyone works on the latest version.
    * __Risk Mitigation:__ Reduces the risk of data loss and makes it easier to recover from mistakes or failures.
    * __Audit Trail:__ Provides a clear record of changes, which is useful for compliance and accountability purposes.

 ## Installing Git
 To install Git, download the installer for your OS from the Git website or use package managers like apt-get for Linux. Follow on-screen instructions to complete installation. Git will be ready to use from the command line for version control in your projects. Below are the installation steps for Git on Windows, macOS, and Linux, each with their respective links:
   * __Windows__: [Download Git for Windows](https://git-scm.com/download/win) and follow the installation instructions.
   * __macOS__: [Install Git on macOS](https://git-scm.com/download/mac) using the installer package provided.
   * __Linux__: Install Git on Linux via your distribution's package manager or [download directly from Git](https://git-scm.com/download/linux) and compile it from source.

 ## Connecting Git to GitHub on your local machine
Here are a few steps for connecting to Github after installing Git on your machine locally:
1. Get a GitHub account.
    * Sign up for a free GitHub account if you don't already have one.
2. Set up Git with your user name and email:
    * Configure Git with your name and email to associate commits with you.
        ````
        git config --global user.name "Your name here"
        git config --global user.email "your_email@example.com"
        ````
3. Set up SSH on your computer:
    * Generate SSH keys if they do not exist to enable secure communication with GitHub.
        ````
        ssh-keygen -t rsa -C "your_email@example.com"
        ````
4. Copy your public key into your clipboard:
    * Copy the SSH public key to your clipboard for later use.
        ````
        pbcopy < ~/.ssh/id_rsa.pub
        ````
5. Paste your SSH public key into your GitHub account settings:
    * Add the copied SSH key to your GitHub account under SSH keys.
    * Go to GitHub Account Settings > SSH Keys > Add SSH Key.
6. Test your SSH connection:
    * Verify that your SSH key is properly set up by testing the connection to GitHub.
        ````
        ssh -T git@github.com
        ````
    * If it says, "Hi username! You've successfully authenticated, but GitHub does not provide shell access," it worked.

# __Git Terminologies__
Git users have their own terminology. They use __repository__ instead of __folder__ and __branch__ instead of __timeline__. However, I think __timeline__ better captures the concept.
## Checking the Installed Git Version:
* To verify the version of Git installed on your system, follow these steps:
    1. Open a Terminal Window:
        * On macOS or Linux, you can use the built-in Terminal application.
        * On Windows, you can use Command Prompt, PowerShell, or Git Bash.
    2. Run the Command:
        ````
        git --version
        ````
This command will display the version of Git currently installed on your system. Git is a stable and reliable software, with breaking changes exceptionally rare.

## Repository
In Git, a repository (often abbreviated as "repo") is a storage space where your project lives. It can be a local repository on your computer or a remote repository hosted on a service like GitHub, GitLab, or Bitbucket. The repository is where Git tracks changes to your files and directories, maintains the history of those changes, and facilitates collaboration with other developers.

### 1. Initialization
* __git init:__ This command creates a new Git repository. It sets up all the necessary files and directories inside a .git folder.
* __git clone <repository>:__ This command copies an existing repository (from a remote source, like GitHub) to your local machine, creating a complete copy of the project including its history.

### 2. Repository Structure
* __.git Directory__: Contains all the metadata and objects for the repository. Key components include:
    * __objects/:__ Stores all the content for your repository (files, commits, trees, etc.) in a compressed format.
    * __refs/:__ Contains pointers to commit objects, including branches (refs/heads/) and tags (refs/tags/).
    * __HEAD:__ A pointer to the current branch reference, indicating the current commit.
    * __config:__ Contains configuration settings for the repository.

### 3. Remote Repositories
* __Adding Remotes:__ Connects your local repository to a remote server.
    * `git remote add <name> <url>` : Adds a remote repository.
* __Fetching:__ Downloads objects and refs from another repository.
    * `git fetch <remote>`: Fetches branches and commits from the remote repository.
* __Pulling:__ Fetches and integrates changes.
    * `git pull <remote>`: Fetches and merges changes from the remote repository.
* __Pushing:__ Uploads local changes to a remote repository.
    * `git push <remote>`: Pushes commits from your local branch to a remote repository.


