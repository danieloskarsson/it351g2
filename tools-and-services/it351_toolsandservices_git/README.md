---
description: description
---

# Git

Git is a distributed version control system \(VCS\). The purpose of VCS:es is to keep track of file changes so that you can see exactly what has been changed and revert or commit to the changes. Before Git and similar distributed VCS:es the norm was for these type of tools to be centralized, i.e. there was a server that had to be online and accessible at all times. With distributed or de-centralized VCS:es each client has its own complete clone of the source code repository.

 To use git you start by either executing `git clone` to clone an existing repository, or invoking `git init .` ****from within any directory. A directory that is being tracked by git is called a git **repository** and always contain a hidden directory called **.git** where all history is stored. Git keeps track of all files within the directory including those that are stored in sub-directories. Removing the .git directory removes any trace of git ever tracking that the contents of that directory and the git repository returns to be nothing else than a normal directory.

{% hint style="info" %}
Git is useful for other types of content than source code. Git is not made for binary formats but one could example keep track of a set of markdown files with a git repository.
{% endhint %}

There are a couple of core concepts to understand when it comes to git. Two of the most important ones are the **working directory** and the **staging area**. The staging area contains all the file changes that that has been added to the staging area using `git add`. When the staging area contains a set of changes that should be saved for all eternity the `git commit -m "message"` command add those changes to the git history. The complete git history can be viewed using `git log` and contains all commits ever created and for each commit there is a timestamp, message, and a hash that were all added with git commit. The working directory contains all file changes that has _not yet_ beed added to the staging area. If a file is changed, the working directory will show exactly what was added and what was removed. To see what files has been changed the command `git status` is used. The status command actually shows both the files in the staging area \(normally in green\) as well as the files that has been changed in the working directory \(normally in red\). The exact changes of what has been added and what has been removed in the working directory \(compared to the staging area\) can be seen using `git diff`.

{% hint style="info" %}
In Android Studio git commands are available from within the VCS menu item
{% endhint %}

To synchronize changes between a local repository and a remove repository \(such as a Github repository\) there are two commands. The command `git pull` pulls all the updated history from the remote repository to the local repository. The `git push` command does the opposite and pushes all the commits from the local repository to the remote repository. When multiple persons are working in the same repository it is important to synchronize changes between the local repository and remote repository often as changes can be pushed from multiple persons. If multiple persons change the same lines of code with synchronizing their changes in time there will be a merge conflict. However in this course there will be only one person working in the same repository so merges are not discussed in detail.

{% hint style="info" %}
Git and Github are different things. Git is a tool that is installed on a computer and Github is a service that hosts a copy of your repositories in the cloud.
{% endhint %}

