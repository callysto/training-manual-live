# Quickstart

This Quickstart provides the most basic information needed to get started in order to develop content for the Callysto project. The Quickstart assumes that the creator is familiar with Jupyter notebooks and is an experienced programmer. After getting set up with the Quickstart, please see additional sections in the training-guide for more details.

## Programming language
In order to make the notebooks produced as easy to follow for teachers and to provide consistency throughout the notebooks, all developers must use Python 3. We also recommend using other standardized approaches to attain consistency throughout the notebooks, as outlined in the Best Practices for Code Development section.

## Where to develop
The recommended way to run the sample notebooks is to use the JupyterHub set up for this project.
[hub.callysto.ca](https://hub.callysto.ca) is the environment teachers and students will use to run notebooks created as part of the Callysto project. As such, it should be ensured that any notebooks that are created work on hub.callysto.ca. One step to help do so is to develop directly on the hub.

### Setting up GitHub with hub.callysto.ca
Once logged in at [hub.callysto.ca](https://hub.callysto.ca), it is recommended to set up SSH authentication for interacting with GitHub. To do so, create a new private key on hub.callysto.ca and add the corresponding public key to your GitHub account as per the following instructions.

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

NB: there are other options for interacting with GitHub as well. Please see [this page](https://developer.github.com/v3/guides/managing-deploy-keys/) for more information.

### Setting up notebook specific git tools
Any GitHub project, including this one, can be initialized with a filter to remove output blocks from checkins and give more readable git diffs by running the following from a terminal:
```
bin/git-nb-tools
```
in the root of the project (adjusting the path to the setup script if running from outside of this project).

To use the notebook specific git tools, you will also need to make sure there is a .gitattributes file in your project root with at least the following lines:

```
*.ipynb filter=nbstripout  
*.ipynb diff=jupyternotebook  
*.ipynb merge=jupyternotebook
```

Note that this file should have been pulled automatically from this repository.

## JIRA - what to work on and coordinating with others
JIRA is an issue tracking product that provides bug tracking, issue tracking, and project management functions. The Callysto project uses JIRA in order to keep track of tasks and objectives that must be completed for the project. Creators should be working towards tasks as outline in JIRA and updating those tasks with comments and other progress.

Follow these steps to access JIRA for the first time:  
1. go to jira.cybera.ca  
2. click on the "Can't access your account?" link  
3. in the "Enter your username" field, enter your EMAIL ADDRESS and click "Send"  
4. check your email for password reset instructions

NB: this assumes that your account was already added to JIRA. If not, please contact your PIMS leader or someone on the [Callysto Slack workspace](https://cancode-collaboration.slack.com).

## Notebook Formatting
Please see the [Notebook Template](notebook_template.md) and [Notebook Format](NotebookFormat.md) sections for more details. Some examples of Callysto curriculum module notebooks can be found in this [GitHub repository](https://github.com/callysto/callysto-sample-notebooks). These specific examples should help you get started: [Investigating Conductivity](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Science/investigating_conductivity.ipynb), [Radioactive Decay](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Physics/Nuclear.ipynb), [Flipping Coins](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Math/FlippingCoins.ipynb), [Interactive Geometry](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Math/Interactive%20Geometry.ipynb), [American Revolution](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Social_Sciences/History/American_revolution_with_animated_slider.ipynb) and [Shakespeare and Statistics](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Social_Sciences/Humanities/Shakespeare_and_Statistics.ipynb).

## Contributing Notebooks
Once a notebook/content has been developed, it should be pushed to GitHub to share with the team and to put under for version control. In order to ensure notebooks are working correctly, any notebooks initially created should be first committed for review in the Callysto-development repository (exact repo name to be confirmed).

**NB**: please ensure that you `Shutdown` any running notebooks (click on "Running" tab from Jupyter web interface) before committing your work. This will avoid any odd Git issues that result from running the `bin/git-nb-tools` mentioned above.  

### Using GitHub
If you are new GitHub, here are a couple of guides to get started.

* [Simple Guide - the basics](http://rogerdudler.github.io/git-guide/)
* More [in-depth guide](https://www.atlassian.com/git/tutorials/what-is-version-control) with good explanations

## Slack team messaging
Slack is the messaging system used to communicate with the entire Callysto team. If you have not joined the [Callysto Slack workspace](https://cancode-collaboration.slack.com) yet, contact your PIMS leader in order to get added.
