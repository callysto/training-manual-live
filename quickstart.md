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

## Version Control with Jupyter Notebooks
Jupyter notebooks are written in a JSON format that, when altered using the notebook interface, result in a very difficult to read git diff output. This is because when you change the contents of a given cell, it will have a downstream effect on the notebook's source code, metadata, and output files. At first you may know where to look based on your memory, but when trying to untangle a old notebook's commit history based on git diff there will be difficulties. For this reason it is recommended that you use a tool that makes code comparisons between versions more readable. Please see [this](https://nextjournal.com/schmudde/how-to-version-control-jupyter) article for more details.

## JIRA - what to work on and coordinating with others
JIRA is an issue tracking product that provides bug tracking, issue tracking, and project management functions. If your team is using JIRA, follow these steps to access it for the first time:  
1. go to jira.cybera.ca  
2. click on the "Can't access your account?" link  
3. in the "Enter your username" field, enter your EMAIL ADDRESS and click "Send"  
4. check your email for password reset instructions

This assumes that your account was already added to JIRA. If not, please contact your team leader or someone on the [Callysto Slack workspace](https://cancode-collaboration.slack.com).

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
Slack is the messaging system used to communicate with the entire Callysto team. If you have not joined the [Callysto Slack workspace](https://cancode-collaboration.slack.com) yet, contact your team leader to get added.