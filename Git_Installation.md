#### **GIT Installation**

In order to use GIT, you have to make it available on your computer.  In case if it’s already installed, it’s probably a good idea to update to the latest version. 

We cans Install GIT as

- a package or 
- via another installer, or 
- download the source code and compile it.

```shell
MyGitMachine $ uname
Linux

MyGitMachine $ apt-get update
Hit:1 http://azure.archive.ubuntu.com/ubuntu focal InRelease
Get:2 http://azure.archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
---
--- ********  It will take few minutes *********
---
MyGitMachine $ apt-get install git-all
Reading package lists... Done
Building dependency tree
--
--
--
After this operation, 902 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
---
--- ********  It will take few minutes *********
---

MyGitMachine $ git --version
git version 2.25.1
MyGitMachine $
```

#### **GIT Setup**

Now we have install Git on our system, the second step is to customize your Git environment. You should have to do these thing only once on any given computer. Using   **<u>git config</u>**  we will set configuration variables that control all aspects of how Git looks and operates:



```shell
git config --global user.name "Your_Name"
git config --global user.email "Your_Email"
git config --global core.editor "Path_of_Editor_SW"
git config --list

```

#### **GIT Help**

Just like Linux man pages, you may need help while using Git, there are three ways we can get help from  manual page (manpage) :

```shell
$ git help <verb>
$ git <verb> --help
$ man git-<verb>

MyGitMachine $ git help add
MyGitMachine $ git help config
MyGitMachine $
MyGitMachine $ git add -h
usage: git add [<options>] [--] <pathspec>...

    -n, --dry-run         dry run
    -v, --verbose         be verbose

    -i, --interactive     interactive picking
    
```

