### **What is Git**?

Git is a Version Control System. Ok, What is Version Control System? Before directly jumping to the question of  What is “version control”, and why should you care?. Let's take a step back and discuss the scenario.

 



### Problems

- Problem#1 System Failure

- Problem#2 Access Control: Collaboration between the team members

- Problem# 3 Code Duplication: Difficult to track the the changes and revert back to the previous Version

### Solution

- Solution#1 Store the file some where in Cloud, where there is very minimal chance of system failures.

- Solution#2 If we can resolve the conflict of the changes made by multiple people at the same time, with the help of the tool.

- Solution# 3 If by somehow we maintain the history of all the changes and revert back to the previous state of the code.
  

**Can we achieve this with Normal File system**

### Normal Fil System

- The tools provided by the Normal file systems are blunt, like granting or denying the write access to specific file system. Also we need some solution, which are much more convenient to use and automatic. 



#### **What is the Solution**

###  VCS

- In VCS your code is store in some remote machine, which is much more stable then your local system. You can always sync it up.
- VCS offers you merge tool, where multiple people work on same code at same time. The GOLDEN copy is maintained on the cloud. Code merge happens using merge tool. It's really very beautiful, how VCS solves these kind of conflict issue with merging tool.
- VCS maintains the history, you can reverts to any of the previous state of your code. It track the each and every changes also by whom. 

**So, Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later.**

#### **Types of VCS**

- **Local Version Control Systems**
  It is one of the simplest forms and has a database that kept all the changes to files under revision control.

  

  

  <img src="https://cdn-images-1.medium.com/max/800/1*VsALkIdnjT3DVO7VKnIJYA.png" alt="img" style="zoom:50%;" />

- **Centralized Version Control Systems**

  Centralized version control systems contain just one repository globally and every user need to commit for reflecting one’s changes in the repository. It is possible for others to see your changes by updating. 

  Two things are required to make your changes visible to others which are: 

  - You commit
  - They update



<img src="https://cdn-images-1.medium.com/max/800/1*V3fXBDudcdXeGGMUomvb0Q.png" alt="img" style="zoom:50%;" />

-  Everyone knows to a certain degree what everyone else on the project is doing (advantages over local VCSs) .

- Administrators have fine-grained control over who can do what, and it’s far easier to administer a CVCS than it is to deal with local databases on every client.

- Disadvantages: Single point of failure that the centralized server represents.

  

  

- **Distributed Version Control Systems**

Distributed version control systems contain multiple repositories. Each user has their own repository and working copy. Just committing your changes will not give others access to your changes.

<img src="https://cdn-images-1.medium.com/max/800/1*XXbzvIsJcidKQ9-B6t8VYQ.png" alt="img" style="zoom:50%;" />

 This is because commit will reflect those changes in your local repository and you need to push them in order to make them visible on the central repository. Similarly, When you update, you do not get others’ changes unless you have first pulled those changes into your repository. 



### Tools

There are different VCS tools available like Git, Subversion and Mercurial, here we are going to discuss about Git The reason is very Simple, Git is by far the Best VCS system 

- It is Open Source and Distributed Version Control System
- It is mature, tried and tested product.
- fast and efficient
- very popular most widely used VCS system in the world, so giving you a huge community support.. 