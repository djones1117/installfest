<img src="https://i.imgur.com/pF2sUV5.jpg">

# SEI Installfest Guide

Let's install and configure the software we will be using throughout the program!

## Preparation

### Notes About Running Commands in Terminal

Most of the commands we run will be run in Terminal.

To open Terminal:
- Open Spotlight Search (`command + spacebar`)
- Start typing "terminal" until the **Terminal** app is highlighted
- Press `[return]` to launch Terminal

It's important to know that many of the commands we run in terminal simply do not provide a response - this is a case of "no news is good news"!

You should only be concerned if you receive error/warning messages after running a command.

### Using `sudo`

If you receive a "permissions" related error when running a command in Terminal, try running it again as an admin by prefacing the command with `sudo`.

You may be prompted for your computer username/password.

> Note:  When prompted to enter a password in Terminal, usually **nothing** will be displayed as you type your password.

### Credentials

Before beginning, you'll need to have the your **username** and **password** for your computer.

Note that the user must have administrative access to the computer. You can verify this by using Spotlight to launch **Users & Groups** and checking for the word **Admin** under the username:

<img src="https://i.imgur.com/yYQiKsr.png">

### Support

If you have any questions or need assistance while following along, please reach out to your cohort's "support" channel in Slack.

## What We'll Be Installing/Configuring

We'll be installing and configuring the following software and tools:

1. Terminal's Shell
2. Create a `~/code` Folder
3. Spectacle (window management)
4. Homebrew
5. Node.js
6. Visual Studio Code
7. GitHub Accounts
8. Git
9. Python 3
10. PostgreSQL
11. MongoDB
12. Update Z Shell to Show Repo Info (optional)
13. Imgur (optional)

## 1. Terminal's Shell

A Shell is the program that allows us to run commands in Terminal.

For a long time, Bash (Bourne Again Shell) was the default shell for macOS.  However, since Catalina, Apple now uses Zsh (Z Shell) instead.

If your Mac at one time ran a version of macOS previous to Catalina and have since upgraded to Catalina or later, you will want to update Terminal to use Zsh.

### How can I tell if Terminal is using Bash or Zsh?

Bash displays a `$` as its command prompt, while Zsh uses `%`.

You can also check the name of the active shell program by running in Terminal:

```
echo $0
```

`-bash` will be displayed if running Bash or `-zsh` will displayed if running Zsh.

### Setting Zsh as the Default Shell

It is highly recommended to switch to Zsh from Bash because:
- Bash is no longer supported by Apple
- Zsh is considered to be more interactive and customizable

Run the following command to switch to Zsh:

```
chsh -s /bin/zsh
```

Enter your computer password if prompted.

Quit Terminal (`command + Q`), then relaunch Terminal. 

Welcome to Zsh!

## 2. Create a `~/code` Folder

We need a place to store our work, projects, etc. that we create during the course.

Let's create a folder named `code` inside of our _home_ folder (represented by `~`) by running this command:

```
mkdir ~/code
```

> Note:  Future lessons will assume that you have a `~/code` folder created.

## 3. Spectacle (window management)

Productive developers often use keyboard commands vs. the mouse to perform certain tasks.

"Snapping" open application windows to be full-screen, to the left, right, etc. using the keyboard is one such task.

Spectacle is a free tool that uses the keyboard to size application windows saving valuable time vs. using the mouse.

If your system currently does not have a "window manager", let's install Spectacle from [Spectacle's Website](https://www.spectacleapp.com/).

## 4. Homebrew

[Homebrew](https://brew.sh/) is an open-source application that simplifies the installation of software on macOS and Linux operating systems.

### Check if Homebrew is Already Installed

Running `brew --help` in Terminal will display

```
zsh: command not found: brew
```

if it's not installed.

If you saw a list of commands instead, Homebrew is installed...

#### If Homebrew is Already Installed

If Homebrew is already installed, let's make sure it's up to date by running:

```
brew update
```
> Note: Updating Homebrew might take a minute or more to complete.

After updating Homebrew, you may upgrade previously installed applications by running:

```
brew upgrade
```

> Note: Upgrading outdated applications might take several minutes to complete.

Homebrew may recommend running other commands related to the upgrade and it's usually best to run those recommended commands.

After upgrading existing applications, let's check the status of Homebrew by running:

```
brew doctor
```

Again, Homebrew may recommend running other commands to improve its integrity and it's usually best to run those recommended commands.

#### If Homebrew is NOT Already Installed

If Homebrew is not installed, install it:

1. Browse to [Homebrew's Website](https://brew.sh/)

2. Copy the installation command by clicking the Copy Icon displayed under the **Install Homebrew** heading:
    <img src="https://i.imgur.com/CASoct8.png">

3. Paste the command (`command + V`) into Terminal and pressing `[return]`

During or after installation Homebrew may require or recommend other commands be ran.  It's important to take its advice and run those commands.  For example, a common requirement is to install, update, or configure Xcode. Again, run the commands if prompted to do so.

> Note that installing Xcode can take a significant amount of time - please be patient.

## 5. Node.js

Node provides an environment for executing JavaScript outside of the browser.

We will be learning about Node.js during the course and many tools we use depend on it being installed.

### Check if Node.js is Already Installed

In Terminal run:

```
node -v
```

If a version number is displayed, Node.js is already installed.

#### If Node.js is Already Installed

If Node.js is already installed, let's update it to the current version.

Updating Node.js depends upon how it was installed in the first place.  Typically Node.js was either installed using Homebrew or via Node.js's website.

To check if Node.js was installed via Homebrew, run:

```
brew list
```

If Node.js was installed using Homebrew, `node` and/or `node@<version>` will appear in the display and you're good to go!

Otherwise, if it's not listed in the display, Node.js was not installed using Homebrew and can be updated by following these steps:

1. Browsing to the [Node.js Website](https://nodejs.org/en/)

2. Clicking on the Current version to download and install it.
  <img src="https://i.imgur.com/gIuvVCb.png">

#### If Node.js is NOT Already Installed

Homebrew is a great way to install Node.js - let's do it:

```
brew install node
```

You can verify that Node.js is installed by running:

```
node -v
```

## 6. Visual Studio Code

Text editors are a personal choice, however, the most popular open source text editor these days, for good reason, is Visual Studio Code.

It is important to use VS Code during the course so that you can learn some amazing shortcuts, etc.

### Install VS Code

If you don't already have VS Code installed, download and install it from [Visual Studio Code's Website](https://code.visualstudio.com/).

### Ensure the Ability to Launch VS Code by Typing `code` in Terminal

1. **IMPORTANT** - Be sure that VS Code is in your Mac's `Applications` folder.

2. Launch VS Code using Spotlight (`command + space` - then start typing `vs c` until you see the app, then press the `return` key).

3. Type `shift + command + P` to open VS Code's _command palette_.

4. Start typing `shell command` and when you the<br>`Shell Command: Install 'code' command in PATH` command - click it!

5. Quit VS Code and Terminal (always use `command + Q` to fully quit applications instead of clicking the red circle).

6. Relaunch Terminal using Spotlight

7. Test the command by typing `code .` - the current folder should open in VS Code!

Check [this link](https://code.visualstudio.com/docs/setup/mac) for troubleshooting if you run into issues.

## 7. GitHub Accounts

You'll need both **personal** and **GA Enterprise** GitHub accounts.

### Personal GitHub Account

GitHub is a cloud-based service for hosting Git repositories (more on these in a bit) in the cloud. It enables collaboration on projects and is wildly popular.

If you haven't already opened a personal GitHub account, please browse to [GitHub's Website](https://github.com/) and click the **Sign up** button.

#### Logging in to interact with GitHub _via Terminal_

The credentials you used when signing up on GitHub's site can no longer be used to interact with GitHub in Terminal (command line).

Instead, GitHub requires that we provide a Personal Access Token when asked for our password.

Let's follow the [Creating a personal access token instructions in GitHub's docs](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

When selecting the scopes for the token, be sure to select at least these checkboxes:

- **repo**
- **user**

Also, be sure to select the **No expiration**, unless you want to re-create tokens regularly.

> Note: Be sure to save to save your token in a safe place because it will only be displayed once (after it's created).  Otherwise, it will be necessary to create another one each time.

### GA GitHub Enterprise (GHE) Account

In addition to having a personal account on GitHub, you'll need to have a GA GitHub Enterprise account as well.  You can get one by signing up here:  [http://git-invite.generalassemb.ly/](http://git-invite.generalassemb.ly/)

> Note that you may use the same username for both GH & GHE accounts, however, it's recommended that you distinguish between the two by appending `-ga` to your GH username, i.e., `<your GH usename>-ga`

## 8. Install and Configure Git

GitHub and Git are related, but not the same thing. We install and use Git on our local computer whereas we access GitHub by browsing to it in our browsers.

Git is an open-source version control system used by the vast majority of developers to track changes to their projects, know as repositories.

Git should already be installed on your system.  However, it's probably not up to date and is difficult to update the version that Apple installed.

So let's re-install using Homebrew so that it can easily be updated to new versions in the future:

```
brew install git
```

Not let's configure it...

### Configure Git

It's important that Git be configured as follows...

#### Configuring Git to default to a branch named `main`

GitHub (in the cloud) now defaults newly created remote repos (short for repositories) to use a default branch named `main` instead of `master`.

Let's ensure that Git also uses a `main` branch when you create a local repo (using `git init`) by running the following command:

```
git config --global init.defaultBranch main
```

#### Configuring Git to use VS Code as its Editor

The time will come when Git needs info from you and will automatically open a text editor.

The default editor used by Git is usually Vim - and it's not very user friendly.  The following command will set Git's editor to VS Code:

```
git config --global core.editor "code --wait" 
```

#### Configuring your Preferred `username` & `email`:

Run the following two commands to configure your preferred Git `username` and `email` - it is recommended that you use your **personal GitHub** info, **not your GHE account's**:

```
git config --global user.name "username"
```

then...

```
git config --global user.email "youremail@domain.com"
```

#### Avoiding Having to Create A Git Message Every Time a Git Merge Takes Place

By default, Git asks for a commit message any time new commits are merged into a repo.

To avoid this from happening, we can add a single line to our shell configuration...

Use VS Code to edit `~/.zshrc` (Zsh's configuration file):

```
code ~/.zshrc
```

> Note: VS Code will create the file when saved if it does not exist.

Now let's add the following line anywhere inside of the file:

> Note the following is NOT a Terminal command, please copy/paste it into the file opened in VS Code

```
export GIT_MERGE_AUTOEDIT=no
```

Finally, save the file using `command + S` then close VS Code with `command + Q`.

#### Configuring a Global Git Ignore

> IMPORTANT: **THIS STEP IS CRITICAL**

Certain files and folders should not be committed in a local Git repository so that they are not pushed to GitHub.

For example, a `.env` file is used to store sensitive information such as a _database connection string_ that contains a username and password. 

To prevent sensitive or unnecessary information from being committed we can configure a _global Git ignore_ file so that we don’t have to worry about making the appropriate entries in a project’s local Git ignore.

First, create the file in our user's home folder:

```
touch ~/.gitignore_global
```

Next, configure Git to use the newly created `~/.gitignore_global` file as the default for all repositories:

```
git config --global core.excludesfile ~/.gitignore_global
```

Now lets put some well-known files/folders that should be Git ignored in the newly created file using VS Code...

Open the file in VS Code:

```
code ~/.gitignore_global
```

Copy & paste the following into that file in VS Code:

```
# This is a list of rules for ignoring files in every Git repositories on your computer.
# See https://help.github.com/articles/ignoring-files

# Compiled source #
###################
*.class
*.com
*.dll
*.exe
*.o
*.so

# Packages #
############
# it's better to unpack these files and commit the raw source
# git has its own built in compression methods
*.7z
*.dmg
*.gz
*.iso
*.jar
*.rar
*.tar
*.zip

# Logs and databases #
######################
*.log

# OS generated files #
######################
._*
.DS_Store
.DS_Store?
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Testing #
###########
.rspec
capybara-*.html
coverage
pickle-email-*.html
rerun.txt
spec/reports
spec/tmp
test/tmp
test/version_tmp

# node #
########
node_modules

# Rails #
#########
**.orig
*.rbc
*.sassc
.project
.rvmrc
.sass-cache
/.bundle
/db/*.sqlite3
/log/*
/public/system/*
/tmp/*
/vendor/bundle

# Ruby #
########
*.gem
*.rbc
.bundle
.config
.yardoc
_yardoc
doc/
InstalledFiles
lib/bundler/man
pkg
rdoc
tmp

# for a library or gem, you might want to ignore these files since the code is
# intended to run in multiple environments; otherwise, check them in:
# Gemfile.lock
# .ruby-version
# .ruby-gemset

# CTags #
#########
tags

# Env #
#######
.env

# Python #
#######
*.pyc
__pycache__/

# Misc #
.eslintcache
```

Finally, save the file using `command + S` then close VS Code with `command + Q`.

## 9. Python 3

In addition to JavaScript, we will be learning the Python programming language as well.

Macs have come with Python 2 pre-installed for quite some time.  However, Python 2 is obsolete - we need Python 3!

Python 3 might have been installed by Xcode, let's check by running:

```
python3 --version
```

If you received an error or if a version lower than `Python 3.8.x` is displayed, let's install Python using Homebrew...

### Installing Python 3

Let's have Homebrew install the latest version by running:

```
brew install python
```

You can test the installation by running `python3 --version`.

> Note: Due to time constraints and for simplicity, we will not be using Python "virtual environments" during SEI.  If you are familiar with using virtual environments, you may continue to use them.  If you decide to continue to develop using Python beyond SEI, a good next step would be to learn about using virtual environments.

## 10. PostgreSQL

PostgreSQL is a popular and robust Relational Database Management System (RDBMS).

Check if PostgreSQL is already installed by running this command:

```
psql
```

If you entered PostgreSQL's Interactive Shell, you already have PostgreSQL installed. Enter `\q` to exit the shell.

If you already have PostgreSQL installed, note the version and inform an instructor if it's not at least version 10.

Otherwise, let's use Homebrew once again...

### Install PostgreSQL

Install PostgreSQL using Homebrew with this command:

```
brew install postgresql
```

After Postgres is installed run this command:

```
brew services restart postgresql
```
 
Then run the following command to create a new database named the same as the current system user:
 
```
createdb
```

With our relational/SQL database needs taken care of, let's turn our attention to the realm of NoSQL databases...

## 11. MongoDB

MongoDB is the most popular NoSQL/Document-based database available.

Although we could install MongoDB locally on our computers, ultimately, we need our MongoDB to be running in the cloud.

Therefore, we will get set up with MongoDB's hosting service, Atlas, later in the course.

## 12. Install oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Save the file (`command + S`) then completely quit Terminal.

That's it!

If you would like to highly customize Zsh, a popular tool known as Oh-My-Zsh can be found [here](https://ohmyz.sh/).

## 13. Imgur (optional)

You will need to upload screenshots/images to the cloud during the course.

If you aren't yet already using a cloud-based image hosting service such as Flickr, create a free at [imgur.com](https://imgur.com/).

### Congratulations on finishing Installfest!