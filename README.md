# Learn Git and GitHub!

A tutorial to help you learn Git! Follow the instructions below to learn how to
use git and submit your first code change!

![](/assets/images/Git-Logo-2Color.png)

:bulb: **Notes**
* This tutorial gives instructions on how to configure and use Git with both
Linux-based machines and Windows machines. Mac users can typically follow the
Linux instructions.
* A `$` in this tutorial indicates a command you should enter in a terminal/command line.
* Is Git already on my system?
  * Git is included with virtually all Linux distributions.
  * Git is included with MacOS, but you may need to install/enable command line tools.
    * Enter the command `$ xcode-select --install` in the terminal to do this.
  * Git is not included with Windows - but there are several ways to easily install it.

## Contents
0. [Configure GitHub and Git](#github-and-git-configuration)
1. [Copy this Repository to your Local Machine](#check-out-this-repo)
2. [Create a Branch](#create-a-new-branch)
3. [Sign the signatures.md document](#sign-the-readme-document)
4. [Commit your Changes](#commit-your-changes)
5. [Push Changes to GitHub](#push-your-changes-to-github)
6. [Submit a Pull Request to Publish your Changes](#submit-a-pull-request)
7. [Clean Up Local Git Repository](#clean-up-local-git-repository)
8. [Additional Resources](#additional-resources)

## GitHub and Git Configuration

Before you begin, you'll want to make sure your GitHub Account is set up
and configure Git (the software) on your local machine.

:warning: **GitHub =/= Git** :warning:
* **Git** is version control software. It's open-source and competely free.
* **GitHub** is a private company that provides both *remote* git repository hosting
and a community focused on development and open-source technologies. GitHub is
just one of several popular options for hosting remote git repositories.

### Set up your Account on GitHub

* UW Health has an Enterprise GitHub instance running at https://github.uwhealth.wisc.edu
  * Sign in with your regular AD account.

### Install and Configure Git Locally

#### Linux

* Git in included in most Linux distributions by default. Enter the command
`$ which git` to find out if and where you have the binary installed.
* You'll need to configure your name and email.
  * `$ git config --global user.name "John Doe"`
  * `$ git config --global user.email johndoe@example.com`

#### Windows

### Add SSH Key to GitHub.
* There are two ways to use git with a remote repository host - git-over-ssh
and git-over-http(s). When you clone a repo from GitHub, you can normally choose
either method.
  * Git-over-http(s) is disabled for the UW Health Enterprise GitHub Service.
  You *must* use git-over-SSH.
  * To do this, you'll have to generate a **SSH Key** and add the public key to
  your account.
  * By using SSH-keys, you won't have to enter your login credentials every time
  you push/pull something to/from GitHub.

#### Linux/Mac

* Follow the instructions [here](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
to generate a SSH key using `ssh-keygen`.

* Follow the instructions [here](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)
to add the SSH **public** key (id_rsa.pub) to your GitHub account.

#### Windows

**TODO**

### Desktop/GUI Applications

GitHub provides [a desktop app](https://desktop.github.com/) for Windows and Mac systems.
It is pretty good for working with repositories hosted on GitHub, but it is not the only desktop app available for working with Git.

[Here's an extensive but non-exhaustive list](https://git-scm.com/download/guis) of desktop apps for working with Git.

* This guide will include instructions for working with both the command line and with the GitHub desktop app.

## Clone This Repo

### Command Line

* Change into the directory where you want to keep your repositories.
`$ cd ~/Development`
* Clone this repository.
` ~/Development $ git clone git@github.uwhealth.wisc.edu:serveradmins/learn-git.git`
* You should see Git download the repo and a subdirectory should be created.
```
~/Development $ ls
learn-git
```
* Change to that directory.
`~/Development $ cd learn-git`
* That directory should contain the contents of this repo.
```
~/Development/learn-git $ ls -a
assets/ .gitignore README.md signatures.md
```

### Desktop App

* Open the GitHub Desktop App and go to File --> Clone Repository (CTRL + SHIFT + O)
![](/assets/images/gh_desktop_clone_repo.png)
* Click on the "Enterprise" tab and navigate to the `learn-git` repo.
  * Enter the path on your local machine where you want the project saved. I would recommend not saving it on the hard drive itself and not on a network drive - you want to be able to use this offline!
![](/assets/images/gh_desktop_clone_repo2.png)
* You should see this as it clones the repo from GitHub to your local project directory.
![](/assets/images/gh_desktop_clone_repo3.png)


## Create a New Branch

:question: Why create a new branch? After you clone the repo, you are probably on the default `master` branch. It's bad practice to commit changes directly to the`master` branch in a shared repository. It's better to create a `feature-branch` and safely make your changes there.

### Command Line
* You can create a new branch with the `$ git branch <branch-name>` command and then switch to that branch with `$ git checkout <branch-name>`,
or you can use this shortcut: `$ git checkout -b <branch-name>`
  * Enter the command: `$ git checkout -b add-YOURFULLNAME-signature`
    * Replace YOURFULLNAME with your first and last name. Mine would be "dakotachambers"
    * For me the new branch name is now `add-dakotachambers-signature`
* Use `$ git status` to confirm you're on the correct branch.
```
~/Development/learn-git $ git checkout -b add-dakotachambers-signature
Switched to a new branch 'add-dakotachambers-signature'
~/Development/learn-git $ git status
On branch add-dakotachambers-signature
nothing to commit, working directory clean
```

* :bulb: At this point, your branch lives **only on your local machine**. You need to push it to the remote repository on GitHub:
```
$ git push -u origin add-dakotachambers-signature
...
To git@github.uwhealth.wisc.edu:serveradmins/learn-git.git
 * [new branch]      add-dakotachambers-signature -> add-dakotachambers-signature
Branch add-dakotachambers-signature set up to track remote branch add-dakotachambers-signature from origin.
```
* You should now see the branch listed on GitHub:
![](/assets/images/github_branch_example.png)

### Desktop App

* Click on the tab that says "Current Branch: Master":
![](/assets/images/gh_desktop_branch1.png)
* Click on "New Branch" and enter your branch name "add-YOURNAME-signature", then click "Create Branch."
![](/assets/images/gh_desktop_branch2.png)
* Right now, this branch only exists on your computer. Click "Publish Branch" to push it to GitHub.
![](/assets/images/gh_desktop_branch3.png)
* On the GitHub website, you should see your branch from the drop-down menu:
![](/assets/images/github_branch_example.png)

## Sign the signatures.md Document

* Add your signature to the bottom of the `signatures.md` document.
* Nothing tricky about this step. A file that ends in `.md` is a *markdown* file - it's a plain text document that can do some fancy rendering (into HTML, PDF, e tc). Open and edit the file in your favorite text editor.
  * Some suggestions:
    * [Vim](https://www.vim.org/)
    * [Atom](https://www.vim.org/)
    * Notepad (Ships with Windows)
    * [VS Code](https://code.visualstudio.com/)
    * [Notepad++](https://notepad-plus-plus.org/)

  ![](/assets/images/edit_signature_file.png)
  * You do *not* want to open this in software like Office. You need to preserve the plain-text format.
* From the command line, you can simply enter this command to add your name to the bottom:
  * `$ echo "* john doe" >> signatures.md`

## Commit your Changes

### Command Line

* Add your updated file to be tracked by Git:
  * `~/Development/learn-git $ git add .`
    * By specifying `add .` - you are recursively adding any new, deleted, or altered file at the current directory and all subdirectories, minus what the `.gitignore` file tells Git to ignore. You could also use `git add signatures.md` to be more verbose.
  * This **stages** the file and prepares it for commiting. It tells git you want to include the changes.
* Use the `commit` command to formally record the changes in the git repository.
  * `~/Development/learn-git $ git commit`
    * If you enter just this command, it will open a text editor (Your default editor, set by `$EDITOR` environment variable. For most people it will be Vim or Nano.
    * You now have to enter a **commit message.**
    * Using the editor that opened, enter a message about what you changed, eg: `Added my name to the signatures.md file` There is no need to delete the lines commented out with `#` - Git will ignore them. Save and close the file.
  * You can shorthand this with: `$ git commit -m "Added my name to signatures.md"`

Congratulations! Git has now recorded this change to the file(s). These changes still only exist on your local machine. Next step is pushing them to the remote repository (GitHub) so that other people can see your changes!

### Desktop App

* After you've saved your changes, switch back to the GitHub Desktop app. It should tell you there has been 1 file changed.
![](/assets/images/gh_desktop_changed_file.png)
* Make sure the file is checked :heavy_check_mark: in the project tree in the left pane. Add a *commit message* below.
  * The small box is for a brief summary of your commit. Keep it to 50 characters max.
  * The larger box is for a full commit message. You can use complete sentences and even style it in markdown.
  * For simple commits, just a summary might be fine. For larger commits, you'll want to take the time to explain what you did.
![](/assets/images/gh_desktop_commit_message.png)

## Push your Changes to GitHub

* Your changes are now tracked in Git on your local machine. Next step is pushing your changes to GitHub.

### Command Line

* Enter the command: ` $ git push origin <your-branch>`
  * `<your-branch>` is the branch you created in Step 2.

### Desktop App

* The desktop app should recognize your local commit and ask you if you want to push it to a remote repository. In this case, and in most standard cases, the default remote repository is named `origin`. Press the "Push Origin" button.
![](/assets/images/gh_desktop_commited_push_changes.png)

## Submit a Pull Request

Congratulations! You should see your change live on GitHub on the branch you created. Almost done! The next step is to create a `pull request` to merge your changes into the `master` branch.

**TODO - add images from GitHub**

* Go to the [GitHub Repository on the website](https://github.uwhealth.wisc.edu/serveradmins/learn-git) and click on the **Pull Requests** tab, or click on the "Compare & Pull Request" button.
![](/assets/images/gh_desktop_changes_pushed_to_remote.png)
  * Select **New Pull Request**
* Set the **base** branch as `master` - this is the branch that you are merging your changes *into*.
* Set the **compare** branch as `<your-branch>` - this is the branch that already has changes in it you want to merge into the `master` branch.
![](/assets/images/gh_desktop_pull_request.png)
* Select **Create Pull Request**

And you're done! At this point, the repository **maintainer** (For this repo, [Dakota](https://github.uwhealth.wisc.edu/dcc341)) will review your changes and **merge** your branch into the protected `master` branch.

![](/assets/images/gh_desktop_merge_pr.png)

## Clean Up Local Git Repository

* Whenever you're ready (after your changes are approved and merged) you can clean up your local Git repository.

### Command Line
* Check out the `master` branch: `$ git checkout master`
* Pull the latest changes from GitHub: `$ git pull`
* Delete the feature branch you created: `$git branch -d <your-branch>`
  * This is optional, but recommended if you want to keep your Git repo "neat". Git won't lose track of that branch or what you did.

### Desktop App

* While you have the branch you want to delete checked out, go to the "Branch" dropdown menu and select "Delete Branch." Or just press CTRL+SHIFT+D.

---

:sparkler: **Congratulations!** :sparkler: You've passed the Git 101 tutorial! You're well on your way to becoming a Git superstar.

## Additional Resources

* [Git Documentation - git-scm.com](https://git-scm.com/doc) - The official Git documentation is
  *really* good. Full of examples and verbose/technical without being over-bearing.
* [GitHub Help - github.com](https://help.github.com/) - The official help page from GitHub.
* [Git 101 - Chambers.io](http://chambers.io/2018/04/07/git-week.html) - Shameless
  self plug. I wrote some stuff about how to use Git and how it works under the hood.
* [Git Flight Rules](https://github.com/k88hudson/git-flight-rules) - A list of Git "Flight Rules" to follow in any situation.
