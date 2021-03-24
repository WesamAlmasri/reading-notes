# Introduction to Git

![Git](https://iconape.com/wp-content/png_logo_vector/git-3.png)

The **Git** is a version control is a system that allows you to revisit various versions of a file or set of files by recording changes. It keeps track modifications and modifying individuals, and compare changes, so mistakes with files can easily be rectified.

Each time you save a changed version of your project — called commit — Git creates a ***snapshot*** of the file and stores a reference to it. If the file has not changed, Git only stores a reference to the already-stored identical version of it.

Git mostly relies on local operations because most necessary information can be found in local resources. This allows for process expediency because a project’s history resides on the local disk, eliminating the need to fetch history information from the server, and allowing one to continue work on a project even when not online or on a VPN.

Every single change applied to any file or directory is tracked by Git. And, as the gatekeeper, Git will always detect file corruption or loss of information in transit, so git makes it extremely difficult for a snapshot of your file that is committed to be lost.

Files in Git can reside in three main states: committed, modified and staged.

* **Committed**: Data is securely stored in a local database
* **Modified**: File has been changed but not committed to the database
* **Staged**: Flagged a file’s changed version to be committed in the next snapshot

You can deal with Git using the shell command and here are some of the important command of Git:

## Configration of Git

After installing Git, users should immediately set the user name and email address, which will be used for every Git commit.

```
git config --global user.name "Jane Smith"

git config --global user.email "example@email.com"
```

To confirm that you have the correct settings, enter the following command:

```
git config --global user.name (should return Jane Smith)

git config --global user.email (should return example@email.com)
```

*By using the –global option, these Git settings apply to anything on the system. To use different identity settings for a specific project, change the working directory to the desired local Git repository and repeat the steps above without using –global.*

Without configuration of a default text editor, Git will use the system’s default editor–most likely Vim. To configure a different text editor, such as Emacs, type the following into your Terminal or Command Line:

`$ git config --global core.editor vscode`

To check settings, use the `git config --list` command.

There are three ways to get more information on a particular command, by accessing the manual:

```
git help command

git command --help

man git-command
```

## Setting up a Git Repository

### Import an existing project or directory into Git by these steps:

1. Switch to the target project’s directory `$ cd test (cd = change directory)`
2. Use the git init command  `$ git init`
3. To start tracking these repository files, perform an initial commit by typing the following:

    ```bash
    git add *.c

    git add LICENSE

    git commit -m “any message here”
    ```

You can also create a copy of an existing Git repository from a particular server by using the clone command with a repository’s URL:

`$ git clone https://github.com/test`

By cloning the file, you have copied all versions of all files for a project. This command leads to the creation of a directory called “test,” with an initialized .git directory inside it, which has copies of all versions of all files for the specified project. The command also automatically checks out — or retrieves for editing — a copy of the newest version of the project.

To determine the state of files, utilize the git status command:

`$ git status`

If the output was `nothing to commit, working directory clean`

*This information indicates which branch you’re on (we will cover branches in a later section) and states “working directory clean,” which means that files have tracked or modified status at the moment. Also, no untracked files are present because Git has not listed any.*

## Tracking and Staging a New File

To track one file only by using the following format: `git add filename`
To track all files in a repository by using the following command: `$ git add *`

*After using these commands, files are tracked and staged for committing.*

After staging one or multiple files, you should commit the changes and record what you did within the commit message: `$ git commit -a`

*This command commits a snapshot of all modifications to tracked files in the working directory.*

Next, you would push changes to a remote repositoryusing the command `$ git push origin main`.
