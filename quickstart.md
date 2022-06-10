# Quickstart

This Quickstart assumes that you are familiar with Jupyter notebooks and Python. After getting set up with the Quickstart, please see additional sections in the training guide for more details.

## Programming language
To provide consistency, we use Python 3 in Jupyter notebooks. We also recommend using other standardized approaches as outlined in the Best Practices for Code Development section.

## Where to develop
It is recommended that you develop notebook using [hub.callysto.ca](https://hub.callysto.ca), as it is the environment teachers and students will use to run these notebooks.

### Setting up GitHub with hub.callysto.ca
We recommend setting up SSH authentication for interacting with GitHub. To do so, create a new private key on hub.callysto.ca and add the corresponding public key to your GitHub account as per the following instructions.

1. Using your GitHub email, open a terminal and create the key using the following command and hitting enter when prompted.
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Note that by default, the new key will overwrite any key stored in *.ssh/id_rsa*, so don't accept the default path unless you either have no key stored here or no longer need the original private key file.

2. Copy the contents of your public key. This is easiest done by opening a new Jupyter notebook and copying the output of the following (the notebook will make it easier to copy and paste the key)
```
!cat .ssh/id_rsa.pub
```
3. Add the public key to your GitHub account at [github.com/settings/keys](https://github.com/settings/keys)  

There are other options for interacting with GitHub as well. Please see [this page](https://developer.github.com/v3/guides/managing-deploy-keys/) for more information.

### Working Locally/Offline
It may be necessary or convenient to be able to run examples or develop on a local copy on your computer/laptop. This might be because you expect to be working without internet access, 
or working with complex git branches. Jupyter is easy to run after pip installing it, but it is best to match the entire environment (libraries, os, python version, etc.) 
as the Callysto Hub. The docker images used are hosted on the [callysto docker hub](https://hub.docker.com/u/callysto) and uses the [callysto/pims-r](https://hub.docker.com/r/callysto/pims-r/tags) 
image. This does require [installing docker](https://docs.docker.com/get-docker/) first. 

You also need to clone the github repo in the directory you are working. From a terminal on a *nix system, that can look like the following:
```
mkdir Callysto
cd Callysto
git clone https://github.com/callysto/curriculum-notebooks.git
docker run -it -p 8888:8888 -v "${PWD}":/home/jupyter --name callysto -d --rm callysto/pims-r:latest
docker logs callysto
```
The options we've added to the `docker run` command do the following:
 - `-it` adds some terminal "niceness", 
 - `-p 8888:8888` gives access to the default port (8888),
 - `-v "${PWD}":/home/jupyter` shares the file contents with the server,
 - `--name callysto` names the container "callysto",
 - `-d "detaches"` the container and lets us use the terminal,
 - `--rm` removes the container after quitting (lets us re-use the callysto name in other runs).

The port mapping may need to be adjusted if other jupyter servers are running on 
your machine. The last 3 options itemized above can safely be omitted.

Following successful launch of the container, navigating to `localhost:8888` or using the
address+token from the logs will start Jupyter in the web browser as expected. Changes
to the files will be synced between the container and the directory where the repository was 
cloned. 

If using this to develop and work with git branches, 
care should be taken that resources used do not exceed 
those available on the Callysto Hub: 1GB disk space, 2 GB RAM). 
Disk usage can be checked using, e.g., `du -sh curriculum-notebooks` and cannot exceed 1GB for 
usage on the Hub. RAM usage can be limited by adding a `-m 2G` to the docker 
run command. 

## Version Control with Jupyter Notebooks
Jupyter notebooks are written in a JSON format that, when altered using the notebook interface, result in a very difficult to read git diff output. This is because when you change the contents of a given cell, it will have a downstream effect on the notebook's source code, metadata, and output files. At first you may know where to look based on your memory, but when trying to untangle a old notebook's commit history based on git diff there will be difficulties. For this reason it is recommended that you use a tool that makes code comparisons between versions more readable. Please see [this](https://nextjournal.com/schmudde/how-to-version-control-jupyter) article for more details.

## JIRA - what to work on and coordinating with others
JIRA is an issue tracking product that provides bug tracking, issue tracking, and project management functions. If your team is using JIRA, follow these steps to access it for the first time:  
1. go to jira.cybera.ca  
2. click on the "Can't access your account?" link  
3. in the "Enter your username" field, enter your EMAIL ADDRESS and click "Send"  
4. check your email for password reset instructions

This assumes that your account was already added to JIRA. If not, please contact your team leader or someone on the [Callysto Slack workspace](https://callysto.slack.com).

## Notebook Formatting
Please see the [Notebook Template](notebook_template.md) and [Notebook Format](NotebookFormat.md) sections for more details. Some examples of Callysto curriculum module notebooks can be found in this [GitHub repository](https://github.com/callysto/curriculum-notebooks).

## Contributing Notebooks
Once a notebook or other content has been developed, files should be pushed to a [GitHub branch](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository) off of the master repository.

Remember to `Restart and clear output` then `Shutdown` your notebooks before committing your work. This will avoid any odd Git issues that result from some of the git with Jupyter Notebooks issues mentioned above.  

### Using GitHub
If you are new GitHub, here are a couple of guides to get started.

* [Simple Guide - the basics](http://rogerdudler.github.io/git-guide/)
* More [in-depth guide](https://www.atlassian.com/git/tutorials/what-is-version-control) with good explanations

## Slack team messaging
Slack is the messaging system used to communicate with the entire Callysto team. If you have not joined the [Callysto Slack workspace](https://callysto.slack.com) yet, contact your team leader to get added.
