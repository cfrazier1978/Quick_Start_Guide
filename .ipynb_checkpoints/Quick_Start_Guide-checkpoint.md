# Quick Start Guide - Labs Platform
## Purpose
The purpose of this document is to list out the steps someone would take when starting a new project all the way through sharing that project with others.
## Part 1: Getting Started
The following steps will walk you through creating a new repo in GitHub, importing the repo into the Labs Platform and then cloning a platform compatible cadCAD template.

- Create a new repo in GitHub
     - Give your repository a name.
    - Provide a description of the repository (Optional)
    - Decide if you want the repository to be public or private
        - This decision will not affect your ability to bring the repository into the Labs Platform.  All repositories are treated as private by default within the Labs Platform until you invite others to your project.
    - Choose the type of license to apply to your repository.
    - Click ‘Create Repository’.

![Create a Repo](https://drive.google.com/file/d/1u3846O-Q1zhTn0ps8wAy34WG_W6mAJYU/view?usp=sharing)


![Test](https://drive.google.com/file/d/1u3846O-Q1zhTn0ps8wAy34WG_W6mAJYU/view?usp=sharing)

![]()

![Create a Repo](https://jupyterhub.blocksciencelabs.com/user/3/quick_start_guide-75/lab/tree/Quick_Start_Guide/Create%20a%20new%20repository.png)



![Create a Repo](D:\BSCI Labs\Images\Quick Start Guide\Create a New Repository.png)

![Create a Repo](Quick_Start_Guide/Quick_Start_Guide/Create a New Repository.png)



- Navigate to app.blocksciencelabs.com
    - If you do not have an account, follow the flow to create a new account.  You can see a video of these steps here: https://www.youtube.com/watch?v=Ev6nl2sI-7U
- Click on ‘New Project’ on the Projects dashboard.
    - Find the new repository you just created in GitHub.
    - Provide the project a name.
    - Provide the project a description (Optional)
    - Click ‘Create’.  This will add the project to your project dashboard.



- Click on the name of your new project.
- Navigate to the tab labeled ‘Notebook’
    - It takes about 1 minute for a link to appear labeled ‘Open JupyterHub Server’.
    - Click on the link labeled ‘Open JupyterHub Server’.




- On the upper right side of the screen, click on the dropdown menu labeled ‘New’ and select ‘Terminal’.



- Create a new directory by typing: mkdir <dir name>
    - Example 1: mkdir my_test_dir
    - Example 2: mkdir My_Labs_Project
- Type cd <dir name>
    - Example 1: cd my_test_dir
    - Example 2: cd My_Labs_Project
- Now that you are in your new directory, type: cadcad-cli --interactive
    - NOTE: This will allow you to clone the cli tool that contains a template for a Labs compatible project.  You can use this as a starting point for your model.  The cli tool has many other useful templates for creating cadCAD models.  Check out https://github.com/cadCAD-org/cadcad-cli to learn more.
    - The terminal will return the following text: Template <simple|normal>:
    - Type: labs
    - Example: Template <simple|normal>: labs
    - You will see the following output:

- At this point you have two options:
    - Option A: Go to your local environment and work with the new repo to build your model.
    - Option B: Close the terminal window and work within the Labs Platform in JupyterHub, updating each file to build your model.


NOTE: If you are building your model in the Labs Platform, be sure to commit your changes in the terminal.  To do so, you will need to do the following:

TBD


## Part 2: Running your Experiments
Once you have a working model, you can then run your experiments in the Labs Platform.

What you will need:
Create a labs.py file in the root of your project
In your labs.py file, import the exp object from your model
In your labs.py file, create a variable called model_dir and assign it the path to the directory that contains your model
In your cadCAD configuration, supply a model_id
 
Because you used the CLI tool to create your starting model, the first three steps have already been taken care of for you.  You will still need to do the last step to create a model_id in your cadCAD configuration.
 
From the Labs Platform, go to your project and select the ‘Simulations’ tab.
Click on ‘Run Simulation’
On the ‘General Info’ step, enter a name for your simulation.  If a branch isn’t selected, you will need to choose which branch your simulation is located.
If you run into a Labs.py error, please review this video on the steps to fix: https://www.youtube.com/watch?v=WFUtcP6u56Y
After a few seconds, your available system models will be listed on the ‘System Models’ step.  Select all the system models that are applicable to the simulation run.
On the ‘Time & Cost’ step, review the estimated time and cost to execute the simulation and make sure you select your payment method.  If everything looks acceptable, click ‘Execute’ on the lower right of the screen.
After you execute the simulation, you will be taken back to the ‘Simulations’ tab of your project and a simulation will be added to your list of simulations.
Once your simulation finishes executing, click on the ‘Notebook’ tab.  You will want to note the ID for your simulation.



It takes about 1 minute for a link to appear labeled ‘Open JupyterHub Server’.
Click on the link labeled ‘Open JupyterHub Server’.



On the upper right side of the screen, click on the dropdown menu labeled ‘New’ and select ‘Python 3 (ipykernel)’.



Type the following text into the first cell of your Jupyter Notebook

import blocksciencelabs as labs
import psycopg2 as pg

conn = pg.connect(
    CENSORED!
)

sim_id = <Simulation ID>

labs.fetch_results(sim_id, conn)

Example 1 (from reference image above):

import blocksciencelabs as labs
import psycopg2 as pg

conn = pg.connect(
    CENSORED!
)

sim_id = 24

labs.fetch_results(sim_id, conn)

Example 2 (from reference image above):

import blocksciencelabs as labs
import psycopg2 as pg

conn = pg.connect(
    CENSORED!
)

sim_id = 26

labs.fetch_results(sim_id, conn)


You can now access your data from the notebook and continue with all your post processing.


NOTE: If you perform your analysis in the Labs Platform, be sure to commit your changes in the terminal.  To do so, you will need to do the following:

TBD

Part 3: Sharing Your Work

Now that you have finished your analysis and have results that you want to share, you will want to add others to your project so that they can see your work.

Within your project, click on the ‘Access Control’ tab.
Click on the ‘Add Collaborator’ button.



Enter in the email address of the user that you want to invite to your project and click the ‘Add Collaborator’ button.



Their name will be added to the list of users with access to the project.
The invited user will now see the project added to their Project’s dashboard.  They will be able to navigate to the ‘Notebook’ tab and see your Jupyter Notebook.
