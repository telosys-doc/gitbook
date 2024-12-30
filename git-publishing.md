# Git publishing

Once you've created (or customized) a **model** or a **bundle**, you might want to publish it as a **Git repository** so that you can share it and reuse it later from anywhere.

Here's the procedure to follow...

### 1) Prepare the local Git repository&#x20;

Each model or bundle is a directory, so you can use it as Git repository.

In the model/bundle directory:&#x20;

* Initialize the Git repository with initial branch (for example “master”)\
  `$`**`git init -b master`**
* You can also define your user name and email for the current repository (optional)\
  `$`**`git config user.name "Your Name"`** \
  `$`**`git config user.email your@email.com`**
* Add all the files to be committed (usually all files)\
  `$`**`git add .`**
* Commit the files \
  `$`**`git commit -m "Initial commit"`**

### 2) Prepare the remote repository&#x20;

On the "remote side" (Git server)

Create a Git repository on a server to host the repository you wish to publish.\
You can do that on GitHub, GitLab, your own server, etc...

Copy the remote-repository URL. \
For example:\
&#x20; `https://github.com/xxx/yyy/repo-name.git`   \
&#x20; `https://gitlab.com/xxx/yyy/repo-name.git`&#x20;

### 3) Publish the repository&#x20;

On your workstation, in the **local** directory:

* Add the remote repository as a new remote (for example with name “origin”)\
  `$`**`git remote add origin https://xxx/yyy/repo-name.git`** \
  (use the previously copied URL)
* Check Git remote\
  `$`**`git remote -v`**\
  `origin  https://xxx/yyy/repo-name.git (fetch)`\
  `origin  https://xxx/yyy/repo-name.git (push)`
* Push to “origin” (remote-side) a branch of your repository (for example “master”)\
  `$`**`git push origin master`**\
  (if not authenticated Git ask for user & password)



And that's all. \
The remote Git repository contains now all the model/bundle files. \
The momdel/bundle is now installable by Telosys on any workstation.

See also:\
[Adding an existing project to GitHub using the command line](https://docs.github.com/en/github/importing-your-projects-to-github/importing-source-code-to-github/adding-an-existing-project-to-github-using-the-command-line)
