# Intro to GitHub

## What is GitHub

GitHub is a Web-based Git repository hosting service. It offers all of the distributed revision control and source code management (SCM) functionality of Git as well as adding its own features (mostly regarding sharing and security).

GitHub has an emphasis on Open Source software.

What is Open Source?

Open Source software is software for which the original source code is made freely available and (usually) may be freely redistributed and modified.

> Note: some open source software projects have a LICENSE specifying how the source code may be used.

## Getting Started

Create your first GitHub Repository

There are 2 ways to create a GitHub repository:

* Create a new repo in GitHub, then clone it to your laptop and add content.
* Create a new repo on your laptop, add content, then connect it to GitHub.

### Creating a new Repo from GitHub

We can create a new repository in git by selecting the new git repo button on the top right of `github.com`.

Once created, we can copy the HTTPS address provided on the repository landing page.

We can now return to our terminal and create a the repository on our local machine

```bash
git remote add origin <url>
git push -u origin master
```

If we use -u, we are setting the upstream and will not need to enter `origin master` each time we push to the remote repository. We can simply use  `git push` as the remote is stored in our local `.git` configuration.

If we now return to our github repository, all the files which we have just committed should be available in the remote repo.
