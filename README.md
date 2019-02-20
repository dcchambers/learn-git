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


**TODO** [@dcc341](https://github.uwhealth.wisc.edu/dcc341) to expand this guide...

## Contents
0. [Configure GitHub and Git](#github-and-git-configuration)
1. [Copy this Repository to your Local Machine](#check-out-this-repo)
2. [Create a Branch](#create-a-new-branch)
3. [Sign the README](#sign-the-readme-document)
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
 
### Desktop App

## Create a New Branch

### Command Line

### Desktop App

## Sign the README Document

### Command Line

### Desktop App

## Commit your Changes

### Command Line

### Desktop App

## Push your Changes to GitHub

### Command Line

### Desktop App

## Submit a Pull Request

### Command Line

### Desktop App

## Clean Up Local Git Repository

### Command Line

### Desktop App

## Additional Resources

* [Git Documentation - git-scm.com](https://git-scm.com/doc) - The official Git documentation is
  *really* good. Full of examples and verbose/technical without being over-bearing.
* [GitHub Help - github.com](https://help.github.com/) - The official help page from GitHub.
* [Git 101 - Chambers.io](http://chambers.io/2018/04/07/git-week.html) - Shameless
  self plug. I wrote some stuff about how to use Git and how it works under the hood.
