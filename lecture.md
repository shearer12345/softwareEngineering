##Software Engineering - Introduction To Git

- hosted at: http://shearer12345.github.io/softwareEngineering_introToGit
- source at: https://github.com/shearer12345/softwareEngineering_introToGit



##Software Versioning - What is it?

- AKA:
  - revision control
  - version control
  - source control


>Management of changes to documents, computer programs, large web sites, and other collections of information
  - http://en.wikipedia.org/wiki/Revision_control


###Features

- each revision is associated with a timestamp
- each revision is associated with the person making the change
- revisions can be **compared** (diff), **restored**
- revisions can be **merged** (for some file types, e.g. text files)



##Software Versioning - Why do it?

- Have you ever:
  - Made a change to code, realised it was a **mistake** and wanted to revert back?
  - **Lost code** or had a backup that was too old?
  - Had to maintain **multiple versions** of a product?
  - Wanted to see the **difference** between two (or more) versions of your code?
  - Wanted to prove that a **particular change broke or fixed a piece of code**?
  - Wanted to review the **history** of some code?
  - Wanted to **submit a change to someone else's code**?
  - Wanted to **share your code**, or let other people work on your code?
  - Wanted to see **how much work** is being done, and **where**, **when** and by **whom**?
  - Wanted to experiment with a **new feature without interfering** with working code?
- http://stackoverflow.com/questions/1408450/why-should-i-use-version-control



##Software Versioning - Tools

- distributed version control
  - Git (our focus)
  - Mecurial
- centralised version control
  - Microsoft Visual SourceSafe (VSS)
  - Subversion
  - CVS
- OMG!!
  - manually
  - Dropbox or similar


##Software Versioning - Tools++

- Visual Studio has plugins
- Eclipse has plugins
- XCode has plugins
- Git Shell
- Github for Windows (installs Git Shell)
- Ungit (we'll look at this today)


##Software Versioning - Web support/hosting (git)

- Github (we'll look at this today)
  - github.com
- BitBucket
  - bitbucket.com
- GitLab (open source, host yourself, or hosted)
  - gitlab.com
- Atlassian
- ...


###Hosted tools - extra features

- hosted tools may have extra features, beyond just pure versioning
- e.g.
  - issue tracking (with integration with versioning)
  - forums
  - real-time chat
  - wiki
  - code review
  - team management
  - continuous integration


##GitHub Student Developer Pack

- https://education.github.com/pack
  - five private repositories while you're a student
  - and bunch of other tools



##Version Control - Just for source code?

- **NO**
  - for instance, this presentation is in git, hosted on github
  - hosted at: http://shearer12345.github.io/softwareEngineering_introToGit
  - source at: https://github.com/shearer12345/softwareEngineering_introToGit
- also:
  - documentation
  - configuration files
  - assets


##Version Control - Issues with non-text content?

- version control systems store changes to files efficiently
- by **"diff'ing"** the files
  - finding what's changed between one and another
- very effective for text files
- arbitrarily hard for binary file types
  - e.g. images
  - http://blogs.atlassian.com/2014/05/handle-big-repositories-git/



##Behaviours in Version Control

- initialisation
- add
- commit
- branch
- tag
- checkout
- merge
- clone
- pull
- push


###initialisation

- Create an empty Git repository or reinitialize an existing one
  - in the **current** directory
  - http://git-scm.com/docs/git-init

```bash
git init
```

###add

- updates the index using the current content found in the working tree, to prepare the content staged for the next commit
  - http://git-scm.com/docs/git-add

```bash
git add FILENAME
```

```bash
git add FILENAME1 FILENAME2
```

```bash
git add FILENAME*
```

```bash
git add *.png
```


###commit

- Record changes to the repository
- Stores the current contents of the index in a new commit along with a log message from the user describing the changes
  - http://git-scm.com/docs/git-commit

```bash
git commit #will then prompt for commit message
```

```bash
git commit -m "this is the commit message"
```

```bash
git commit -a #automatically stage files that have been modified and deleted
#but new files you have not told Git about are not affected.
```


###branch

- List, create, or delete branches
  - http://git-scm.com/docs/git-branch

```bash
git branch NewBranchName #create
```

```bash
git branch -l #list local branches
```

```bash
git branch -r #list remote branches
```

```bash
git branch -d BranchToDelete #delete a branch
```


###tag

- Create, list, delete or verify a tag object signed with GPG
  - http://git-scm.com/docs/git-tag

```bash
git tag NewTagName
```

```bash
git tag -d TagNameToDelete
```


###checkout

- Checkout a branch or paths to the working tree
  - http://git-scm.com/docs/git-checkout

```bash
git checkout BranchToCheckout
```

```bash
git checkout TagToCheckout
```

```bash
git checkout -b NewBranchToCreateAndCheckout
```



###merge

- Join two or more development histories together
  - http://git-scm.com/docs/git-merge
- may lead to merge conflicts

```bash
git merge BranchX #Merge BranchX into present branch
```


###clone

- Clone a repository into a new directory
  - http://git-scm.com/docs/git-clone
  - automatically sets up the ```remote```


```bash
git clone https://github.com/shearer12345/softwareEngineering_introToGit.git
  #clone this lecture
  #will get the content, but not the submodule for reveal.js
  #so won't work as a presentation
```

```bash
git clone --recursive https://github.com/shearer12345/softwareEngineering_introToGit.git
  #clone this lecture, clone submodules also
```


###pull

- Fetch from and integrate with another repository or a local branch
  - http://git-scm.com/docs/git-pull
  - incorporates changes from a remote repository into the current branch
  - in default mode, git pull is shorthand for
    - ```git fetch```
    - followed by ```git merge FETCH_HEAD```

```bash
git pull
```

```bash
git pull origin #pull from the remote called origin
```


###push

- Update remote refs along with associated objects
  - http://git-scm.com/docs/git-push

```bash
git push
```

```bash
git push origin #push to the remote called origin
  #will need enough rights for this
```


##When to commit?

- commit often
- commit after reaching some logical milestone
- commit at least everyday
  - or better, break up your work into smaller chunks



##Live Demo