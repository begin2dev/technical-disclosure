# Git

-   [What is Git?](#what-is-git)
-   [About Git](#about-git)
-   [Git Installation](#git-installation)
    -   [Install Git on Linux](#install-git-on-linux)
    -   [Install Git on Mac OS](#install-git-on-mac-os)
    -   [Install Git on Windows](#install-git-on-windows)
-   [Git Reference](#git-reference)
    -   [Setup and Config](#setup-and-config)
    -   [Getting and Creating Projects](#getting-and-creating-projects)
    -   [Basic Snapshotting](#basic-snapshotting)
    -   [Branching and Merging](#branching-and-merging)
    -   [Sharing and Updating Projects](#sharing-and-updating-projects)
    -   [Inspection and Comparison](#inspection-and-comparison)

-   [Git Flow](#git-flow)
    -   [Basic Tips](#basic-tips)
    -   [Setup](#setup)
    -   [Getting Started](#getting-started)
    -   [Features](#features)
    -   [Make a release](#make-a-release)
    -   [Hotfixes](#hotfixes)

# What is Git?

Git is a **free and open source** distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

Git is easy to to learn and has a **tiny footprint with lightning fast performance**. It outclasses SCM tools like Subversion, CVS, Perforce, and ClearCase with features like **cheap local branching**, conveninent **staging areas**, and **multiple workflows**.

Git also works as a **remote repository hosted on a server, with local replicas on which users work**. By this way, you always have local replicas in different local locations, which makes it very convenient in case something goes wrong and the remote repository is lost.

There are multiple web services where you can host your git repositories as public or private projects. This are some of the most used:

-   [BitBucket](https://bitbucket.org/product/) (_external link_)
-   [GitLab](https://about.gitlab.com/) (_external link_)
-   [GitHub](https://github.com) (_external link_)

You can also use tools like [SourceTree](https://www.sourcetreeapp.com/) (_external link_) that allows to show and manage git branches through a visual interface.

**Sources**:
-   [**What is Git?** | Git SCM](https://git-scm.com/) (_external link_)


# About Git

There are some features that makes git a different SCM tool:

-   **Branching and Merging**: Git allows and encourages you to have multiple local branches that can be entirely independent of each other. The creation, merging, and deletion of those lines of development takes seconds.

-   **Small and fast**: Git is fast. With Git, nearly all operations are performed locally, giving it a huge speed advantage on centralized systems that constantly have to communicate with a server somewhere.

-   **Distributed**: One of the nicest features of any Distributed SCM, Git included, is that it's distributed. This means that instead of doing a "checkout" of the current tip of the source code, you do a "clone" of the entire repository.

-   **Data Assurance**: The data model that Git uses ensures the cryptographic integrity of every bit of your project. Every file and commit is checksummed and retrieved by its checksum when checked back out. It's impossible to get anything out of Git other than the **exact bits you put in**.

-   **Staging Area**: Git has something called the "staging area" or "index". This is an intermediate area where commits can be formatted and reviewed before completing the commit.

-   **Free and Open Source**: Git is released under the **GNU General Public License version 2.0**, which is an **open source license**. The Git project chose to use GPLv2 to guarantee your freedom to share and change free software - to make sure the software is free for all its users.

**Sources**:
-   [**About Git** | Git SCM](https://git-scm.com/about) (_external link_)
-   [**Documentation** | Git SCM](https://git-scm.com/doc) (_external link_)


# Git Installation

To know if Git is already installed, just run the following command:
```
git --version
```

If Git is installed, the above command will show you something like this:
```
git version 2.21.1
```

**Sources**:
-   [**Installation** | Git SCM](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) (_external link_)
-   [**Downloads** | Git SCM](https://git-scm.com/downloads) (_external link_)


## Install Git on Linux

To **install git on linux** via binary installer, just use the distribution applications installer:

**Using `dnf`** (Fedora):
```
sudo dnf install git-all
```

**Using `apt`** (Debian or Ubuntu):
```
sudo apt install git-all
```

## Install Git on Mac OS

To **install git on a Mac**, the easiest way to do it is installing the **Xcode Command Line Tools**.
On Mavericks (10.9) or above you can simply try to run the `git` command from the Terminal:
```
git --version
```

If you do not have it installed already, it will prompt you to install it.

You can also install it via binary installer, you can get it from the download section at the Git website:

https://git-scm.com/download/mac

## Install Git on Windows

To **install git on Windows**, you can download the official build from Git webpage:

https://git-scm.com/download/win


# Git Reference

To know more about the **git commands**, you should visit the page:

https://git-scm.com/docs

You can also visit:

-   **GitHub Cheat Sheet** - https://training.github.com/downloads/github-git-cheat-sheet.pdf (PDF - _external link_)
-   **Bitbucket Cheat Sheet** - https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet (_external link_)
-   **Visual Git Cheat Sheet** - https://ndpsoftware.com/git-cheatsheet.html (_external link_)

All git information is available on:

https://git-scm.com/book/en/v2

## Setup and Config

### git
The stupid content tracker.

**Examples**
```
git --version
git --help
```

### git-config
Get and set repository or global options.

**Description**

To set **global configuration** options:
```
git config --global ...
```

Configuration options are written to the `~/.gitconfig` file.

To set **repository configuration** options:
```
git config --local ...
```

Configuration options are written to the repository `.git/config` file.

**Examples**
```
git config --local user.name "Your Name"
git config --local user.email "your@email.com"
```

### git-help
Display help information about Git.

**Examples**
```
git help
git help init
```

## Getting and Creating Projects

### git-init
Create an empty Git repository or reinitialize an existing one.

**Description**

This command creates an empty Git repository.

**Examples**
```
git init
```

### git-clone
Clone a repository into a new directory.

**Description**

Clones a repository into a newly created directory, creates remote-tracking branches for each branch in the cloned 
repository (visible using git branch --remotes), and creates and checks out an initial branch that is forked from the 
cloned repository’s currently active branch.

**Examples**
```
git clone https://<username>@bitbucket.org/<team_name>/<repository_name>.git <destination_dir>
```

## Basic Snapshotting

### git-add
Add file contents to the index.

**Description**

This command updates the index using the current content found in the working tree, to prepare the content staged for
the next commit.

**Examples**
```
git add .
```

### git-status
Show the working tree status.

**Description**

Displays paths that have differences between the index file and the current HEAD commit, paths that have differences 
between the working tree and the index file, and paths in the working tree that are not tracked by Git (and are not 
ignored by **gitignore**).

**Examples**
```
git status
```

### git-commit
Record changes to the repository.

**Description**

Create a new commit containing the current contents of the index and the given log message describing the changes.

**Examples**
```
git commit -m "This is my first commit"
```

### git-rm
Remove files from the working tree and from the index.

**Description**

Removes files from the index, or from the working tree and the index.

**Examples**
```
git rm file.name
```

## Branching and Merging

### git-branch
List, creat, or delete branches.

**Examples**
```
git branch --list
git branch -d develop
```

### git-checkout
Switch branches or restore working tree files

**Description**

Updates files in the working tree to match the version in the index or the specified tree.

**Examples**
```
git checkout branchname
git checkout -b newbranch
```

### git-merge
Join two or more development histories together.

**Description**

Incorporates changes from the named commits (since the time their histories diverged from the current branch) into the 
current branch.

**Examples**
```
git merge branchname
```

### git-stash
Stash the changes in a dirty working directory away.

**Description**

Use this command when you want to record the current state of the working directory and the index, but want to go back 
to a clean working directory.

### git-tag
Create, list, delete or verify a tag object signed with GPG.

**Examples**
```
git tag -a "tag name"
git tag -l
```

## Sharing and Updating Projects

### git-fetch
Download objects and refs from another repository.

**Description**

Fetch branches and/or tags("refs") from one or more other repositories, along with the objects necessary to complete 
their histories.

**Examples**
```
git fetch --all --prune --tags
```

### git-pull
Fetch from and integrate with another repository or a local branch.

**Description**
Incorporates changes from a remote repository into the current branch.

**Examples**
```
git pull origin master
```

### git-push
Update remote refs along with associated objects.

**Description**

Updates remote refs using local refs, while sending objects necessary to complete the given refs.

## Inspection and Comparison

### git-show
Show various types of objects

**Description**

Shows one or more objects (blobs, trees, tags and commits).

**Examples**
```
git show v1.0.0
```

### git-log
Show commit logs.

**Examples**
```
git log
```

### git-diff
Show changes between commits, commit and working tree, etc.

**Description**

Show changes between the working tree and the index or a tree, changes between the index and a tree, changes between two
trees, changes between two blob objects, or changes between two files on disk.

**Examples**
```
git diff
git diff file.name
```


# Git Flow

**Git Flow** is a workflow designed by Vincent Driessen and published at nvie.com:

https://nvie.com/posts/a-successful-git-branching-model/

The git flow workflow defines a strict branching model designed around the project release. Provides a robust framework 
for managing projects.

Git flow is suited for projects that have scheduled release cycle.

**Documentation**

-   **Git Flow Cheat Sheet** - https://danielkummer.github.io/git-flow-cheatsheet/index.html Available in multiple languages (_external link_)
-   **Bitbucket Gitflow Workflow** - https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow (_external link_)

## Basic tips

-   Git flow provides excellent command line help and output.
-   The macOS/Windows Client **SourceTree** is an excellent git gui and provides git-flow support.
-   Git-flow is a merge based solution. It doesn't rebase feature branches.

## Setup

-   You need a working git installation as prerequisite.
-   Git flow works on macOS, Linux and Windows.

**macOS**

Homebrew:
```
brew install git-flow-avh
```

Macports:
```
port install git-flow-avh
```

**Linux**
```
apt-get install git-flow
```

**Windows (Cygwin)**
```
wget -q -O - --no-check-certificate https://raw.github.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh install stable | bash
```
You need wget and util-linux to install git-flow.

## Getting started

Git flow needs to be initialized in order to customize your project setup.

**Initialize**

Start using git-flow by initializing it inside an existing git repository:
```
git flow init
```

## Features

Development of new features starting from the 'develop' branch.

**Start a new feature**

Start developing a new feature with:
```
git flow feature start MYFEATURE
```

**Finish up a feature**

Finish the development of a feature. This action performs the following:
-   Mergest MYFEATURE into 'develop'
-   Removes the feature branch
-   Switches back to 'develop' branch
```
git flow feature finish MYFEATURE
```

**Publish a feature**

Are you developing a feature in collaboration?

Publish a feature to the remote server so it can be used by other users.
```
git flow feature publish MYFEATURE
```

**Getting a published feature

Get a feature published by another user.
```
git flow feature pull origin MYFEATURE
```

You can track a feature on origin by using:
```
git flow feature track MYFEATURE
```

## Make a release

-   Support preparation of a new production release.
-   Allow for minor bug fixes and preparing meta-data for a release.

**Start a release**

To start a release, use the git flow release command. It creates a release branch created from the 'develop' branch.
```
git flow release start RELEASE [BASE]
```

It's wise to publish the release branch after creating it to allow release commits by other developers. Do it similar to feature publishing with the command:
```
git flow release publish RELEASE
```

**Finish up a release**

Finishing a release is one of the big steps in git branching. It performs several actions:

-   Merges the release branch back into 'master'
-   Tags the release with its name
-   Back-merges the release into 'develop'
-   Removes the release branch
```
git flow release finish RELEASE
```
Don't forget to push your tags with `git push origin --tags`

## Hotfixes

-   Hotfixes arise from the necessity to act immediately upon an undesired state of a live production version
-   May be branched off from the corresponding tag on the master branch that marks the production version.

**git flow hotfix start**

Like the other git flow commands, a hotfix is started with:
```
git flow hotfix start VERSION [BASENAME]
```

**Finish a hotfix**

By finishing a hotfix it gets merged back into develop and master. Additionally the master merge is tagged with the hotfix version.
```
git flow hotfix finish VERSION
```
