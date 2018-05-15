# Git workflow

The following is a recommended git workflow for developing notebooks. Its main goals are to encourage regular commits of notebook code and to provide release coordinators with flexibility when preparing for a release.

## Levels

There will be 3 basic levels of branches:

1. master
2. staging
3. individual notebooks

Most developers will do work solely within the 3rd level, making sure to occasionally fetch and merge changes from the staging branch.

In a usual software development project, the 3rd level would more commonly be referred to as *feature branches*. In this project, individual notebooks take the place of individual features.

Keeping to a single notebook per *feature branch* gives release coordinators the flexibility to grab notebooks that are ready and leave those that are not when it comes time to prepare for a release.

More than one developer can work on the same notebook branch, and you shouldn't be terribly concerned with checking in polished work at this level, except to the extent that it may disrupt anyone else working with you on the same notebook. A little communication goes a long way here. That said, we expect that it will largely be a single developer working on a particular notebook at a time.

Get comfortable with making regular, small commits to your notebook branch, and push to Github fairly often. This makes merging easier down the line, makes it easier for other developers to review progress, and ensures that your work is backed up.

## Basic Flow

Here’s a diagram of the basic flow of changes from the lower branches up to the master branch:

![github-workflow](images/github-workflow.png)

## Branch: staging

As the diagram illustrates, this setup allows continual commits to work going on in notebooks A-C. It also allows, when preparing for a release, to grab only notebooks A and B, while commits can still actively be made on notebook C (perhaps this notebook ran into some technical issues that extended the amount of work that had to be done on it).

Occasionally developers working on the individual notebook branches will want to do the following:

```bash
git fetch
git merge staging
```

to make sure they’re up to date with the upstream changes and are always ready to be merged into *staging*. This will become more important the closer those individual notebook branches get to being integrated into *staging*.

Notebooks will undergo reviews before being added to staging and also while in staging.

## Branch: master

This represents "releasable" code. In theory, anyone checking out code from the *master* branch should expect to see the best quality notebook code that we can offer. It won’t necessarily be bug free, but it's free of the bugs we know about (and that are serious enough to block a release).

## Commit messages

Capitalize the first letter, no period. Use the imperative "Fix bug" not "Fixes bug" or "Fixed bug". 
Include the Jira task identifier in the commit message (not in the file title), for example: "CC-33 Add interactivity to the plots". For longer commit message write a short description followed by a blank line and then the longer description. Try to wrap at 72 characters, in Vim this is done with ```:set textwidth=72```. Use the body to explain what and why but not how.

## Tagging

It’s often helpful to mark a specific commit of the master branch when that commit represents code we know has been "released" and will likely not be continually updated from Github until the next release. This can come in handy when tracking down bug reports that may or may not have been fixed since that release.

Individual developers working on notebook branches do not have to worry about tagging, but in the event that a release coordinator wants to tag a release, they can run the following:

```bash
git tag -a v1.0 -m "our first release"
```

## Common commands

Here are some of the common commands that developers will be using:

### Committing and pushing code:

```bash
git add some_file
git add some_other_files*
git commit
git push
```

### Create a branch locally and remotely, based off of *staging*:

```bash
git checkout staging # if not already there
git checkout -b branch_name
git push -u origin branch_name
```

### Merge staging into a notebook (feature) branch:

```bash
# Fetch the remote branch and merge it into the local branch
git pull
git checkout branch_name # if not already there
git merge staging
```

### Merge a notebook (feature) branch into staging:

```bash
# Fetch the remote branch and merge it into the local branch
git pull
git checkout staging # if not already there
git merge branch_name
```

### Compare changes to committed work:

```bash
git diff
```

### Compare differences between branches:

```bash
git diff staging notebook_a
```

Compare with upstream changes on the same branch and then merge (more complicated than git pull, but also avoids potential surprise merge conflicts):

```bash
git fetch
git checkout branch_name
git diff origin/branch_name
# assuming the changes are okay...
git merge origin/branch_name
```

### Temporarily stash local changes:

```bash
git stash
```

The moves local changes out of the way, making your repository look clean. It can be useful when you realize there are upstream changes but don't want to commit your current changes just to see those upstream changes.

When ready, you can then reapply your local changes via:

```bash
git stash pop
```
