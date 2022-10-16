#### **Git Internals :**

- how Git works
- how it performs its operations
- Discuss some low-level commands like 
  -- git-mktree, 
  -- git-hash-object and 
  -- git-cat-file. 

#### **I'll also explain how Git stores the information:**

- Git objects types
  -- Blobs
  -- Tress
  -- Commits
  -- Annotated Tags

- Git repository

#### **Ok, let's start** 

- The first step is to initialize a repository, using **git init** command.
- The **git init** command, will actually create new empty Git repository.
- Once the new Git repository created , you will be able to add new files to it.

```shell
MyGitMachine $ mkdir /myproject
MyGitMachine $ cd /myproject/
MyGitMachine $ pwd
/myproject
MyGitMachine $
MyGitMachine $ la -lart
total 8
drwxr-xr-x 20 root root 4096 Oct 16 07:02 ..
drwxr-xr-x  2 root root 4096 Oct 16 07:02 .
MyGitMachine $
MyGitMachine $ git init
Initialized empty Git repository in /myproject/.git/
MyGitMachine $
MyGitMachine $ ls -lart
total 12
drwxr-xr-x 20 root root 4096 Oct 16 07:02 ..
drwxr-xr-x  3 root root 4096 Oct 16 07:02 .
drwxr-xr-x  7 root root 4096 Oct 16 07:02 .git
MyGitMachine $

MyGitMachine $ cd .git
MyGitMachine $ ls
HEAD  branches  config  description  hooks  info  objects  refs
MyGitMachine $
```



- This hidden '.git' folder, is completely managed by Git, never make any changes in this hidden folder. It must be managed only by Git. 
- You'll see bunch of other folders and several files inside it. We'll dive deep contents of each folder slowly.
- You can see that, for example, branches folder is empty at the moment. objects folder contains two other folders, info and pack, and they are empty as well.

```shell
MyGitMachine $ pwd
/myproject/.git
MyGitMachine $
MyGitMachine $ ls
HEAD  branches  config  description  hooks  info  objects  refs
MyGitMachine $ cd branches/
MyGitMachine $ ls
MyGitMachine $ cd ..
MyGitMachine $  cd objects/
MyGitMachine $ ls
info  pack
MyGitMachine $  cd info/
MyGitMachine $ ls
MyGitMachine $  cd ../pack/
MyGitMachine $ ls
MyGitMachine $

```

The contents of those files, config, description, and HEAD files:

```shell
MyGitMachine $ ls
HEAD  branches  config  description  hooks  info  objects  refs
MyGitMachine $ cat config
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
MyGitMachine $
MyGitMachine $ cat description
Unnamed repository; edit this file 'description' to name the repository.
MyGitMachine $ cat HEAD
ref: refs/heads/master
MyGitMachine $

```

The contents of those files, config, description, and HEAD files:

- **config file**:  It is a configuration of your Git repository, and here you'll see, some default settings. 

- **description file**: You'll see the description of your repository; Unnamed repository; edit this file 'description' to name the repository.

- **HEAD** **file**: You'll see only single line of text. ref: refs/heads/master. 

```shell
MyGitMachine $ ls
HEAD  branches  config  description  hooks  info  objects  refs
MyGitMachine $ cat config
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
MyGitMachine $
MyGitMachine $ cat description
Unnamed repository; edit this file 'description' to name the repository.
MyGitMachine $ cat HEAD
ref: refs/heads/master
MyGitMachine $

```

**Okay, from here we can see that Git has own filesystem, so let's start understanding the concept keeping the File System structure in mind.**

**Git filesystem**:

- Git stores objects
- Objects are stored in the folder, objects 
- There are **several types of objects** that Git can store, 

There are four object types in Git:

- Blob, 
- Tree, 
- Commit, and 
- Annotated Tag



<img src="https://cdn-images-1.medium.com/max/800/1*FCHhbIo1ZnZ2Xc9KeyrEpQ.png" alt="img" style="zoom:50%;" />

**Blob** 

- Git stores files, any files with any extensions, either video files or pictures or text files
- Blob represents single file in a Git filesystem
- So, any files of any types are stored as Blobs. 

**Tree**

- Tree represents directory or folder, and for management of Blobs and Trees
- In tree object type, Git stores information about directories
- Just like as in any other or filesystem, directory may be empty or contain files or contain other directories or have mix of files and directories. 

**Commit**

- Commit object stores versions of our project.

**Annotated Tag**

- Is use persistent text pointer to specific Commit. 



We can use low-level Git commands, like **git hash-object** and **git cat-file** to work with these objects types directly.

- **git hash-object** command, we will be able to create new object in Git structure. With help of 
- g**it cat-file** command, we will be able to read Git objects.