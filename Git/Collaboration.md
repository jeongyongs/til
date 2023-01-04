# Collaboration
Using git for collaboration

<br>

## Index
1. [VSCode Extension](#1-vscode-extension)
2. [Version Control](#2-version-control)
3. [Collaboration](#3-collaboration)

<br>

## 1. VSCode Extension
Extension for convenient use of Git in VSCode
### 1.1. Git Graph
The Git Graph visually expresses the Git log.
![d](/Git/img/git-graph.png)

[▲ Top](#collaboration)

<br>

## 2. Version Control
Basic version control and upload to remote repository
### 2.1. Connect remote repository
With Git, version control information is stored in the **local repository** by default.  
It is necessary to upload git information to a **remote repository** *to collaborate with others or to continue working on another computer*.
#### 2.1.1. Usage
    > git remote add origin https://github.com/<id>/<repository-name>.git
### 2.2. Commit
**Commit** is to store version controls in a local repository.
#### 2.2.1. Usage
    > git commit -m "<message>"
### 2.3. Push
**Push** is to upload version control information to a remote repository.
#### 2.3.1. Usage
    > git push origin master

[▲ Top](#collaboration)

<br>

## 3. Collaboration
How to collaborate with others or work on another computer
### 3.1. Clone
**Clone** is to download version information from the remote repository to the local repository.
#### 3.1.1. Usage
    > git clone <url>
### 3.2. Pull
**Pull** performs fetch and merge functions. It receive new commit information from remote repository.  
Clone gets all the files related to the project. So, clone is used first, and then Pull is used.
#### 3.2.1. Usage
    > git pull origin master
### **3.3. Conflict**
**Conflict** is a change in the same line within the same file. Therefore, which version to use have to be chosen.
#### 3.1.1. Solution
1. Correct the conflicted part.
2. Make merge commit.

[▲ Top](#collaboration)

<br>

## Reference
- [Youtube 생활코딩 - Visual Studio Code에서 Git으로 협업하기](https://youtu.be/vI8FFvQge2w)

[▲ Top](#collaboration)

<br>

[← Go back to TIL](https://github.com/jeongyongs/til/)