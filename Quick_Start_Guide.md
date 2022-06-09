# Quick Start Guide - Labs Platform
## Purpose
The purpose of this document is to provide you with an overview of how to use the BlockScience Labs Platform.  After reviewing this document, you will know how to to create a new repo, use the CLI tool to add a new cadCAD template, run a simulation and then review the data within JupyterLab using the Labs SDK and finally how to invite others to join you in your project.
## Part 1: Getting Started
The following steps will walk you through creating a new repo in GitHub, importing the repo into the Labs Platform and then cloning a platform compatible cadCAD template.

1. Create a new repo in GitHub
    - Give your repository a name.
    - Provide a description of the repository (Optional)
    - Decide if you want the repository to be public or private
        - This decision will not affect your ability to bring the repository into the Labs Platform.  All repositories are treated as private by default within the Labs Platform until you invite others to your project.
    - Choose the type of license to apply to your repository.
    - Click ‘Create Repository’.

![Create a Repo](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/Create%20a%20new%20repository.png)

2. Navigate to https://app.blocksciencelabs.com
    - If you do not have an account, follow the flow to create a new account.  You can see a video of these steps here: https://www.youtube.com/watch?v=Ev6nl2sI-7U


3. Click on ‘New Project’ on the Projects dashboard.
    - Find the new repository you created in GitHub.
    - Provide the project a name.
    - Provide the project a description (Optional).
        - Descriptions are helpful for collaborators to know the goals of the project.
    - Click ‘Create’.  This will add the project to your project dashboard.

![Import Project from GitHub](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/Import%20Project%20from%20GitHub.png)

4. Click on the name of your new project.

5. Navigate to the tab labeled ‘JupyterLab’
    - If the SERVER STATUS = NOT RUNNING, then click on the button labeled 'Start Server'.
        - It takes about 1 minute the server status to change to RUNNING.
    - Once the button changes to 'Open Server', click on the button to launch JupyterLab.

![JupyterLab Tab](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/JupyterLab%20Tab%20Not%20Started.png)

![JupyterLab Tab Started](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/JupyterLab%20Tab%20Started.png)

6. Once in JupyterLab, you will see the Launcher tab.  Click on the button labeled 'Terminal'.

![JupyterLab Launcher](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/JupyterLab%20Launcher.png)

- If you don't see the Launcher screen, or if you ever need to bring it back, you can click on the plus sign button under the main menu.

![Launcher Plus Sign](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/JupyterLab%20Plus%20Button%20for%20Launcher.png)

7. Create a new directory by typing: `mkdir <dir name>`
    - Example 1: `mkdir my_test_dir`
    - Example 2: `mkdir My_Labs_Project`


8. Type cd `<dir name>`
    - Example 1: `cd my_test_dir`
    - Example 2: `cd My_Labs_Project`


9. Now that you are in your new directory, type: `cadcad-cli --interactive`
    - NOTE: This will allow you to clone the cli tool that contains a template for a Labs compatible project.  You can use this as a starting point for your model.  The cli tool has many other useful templates for creating cadCAD models.  Check out https://github.com/cadCAD-org/cadcad-cli to learn more.
    - The terminal will return the following text: `Template <simple|normal>:`
    - Type: `labs`
    - Example: `Template <simple|normal>: labs`
    - You will see the following output:

![Output from Terminal](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/CLI%20Output%20from%20Terminal.png)
    
10. At this point you have two options:
    - Option A: Go to your local environment and work with the new repo to build your model.
    - Option B: Close the terminal window and work within the Labs Platform in JupyterHub, updating each file to build your model.


NOTE: If you are building your model in the Labs Platform, be sure to commit your changes in the terminal.  To do so, you will need to do the following:

1. Change your directory using `cd ` to where you want to make the commit.
- Example 1: `cd Quick_Start_Guide`
- Example 2: `cd my_test_dir`


2. Add the content to your commit by typing `git add .`

3. Create the commit by typing `git commit -m 'message'`
- You will enter some short message about why you are making the commit.

4. Push the commit to your repo with `git push origin <branch>`
- You will need to enter in the name of the branch that you are pushing the commit to.
    - Example 1: `git push origin main`
    - Example 2: `git push origin TestBranch`


## Part 2: Running your Experiments
Once you have a working model, you can then run your experiments in the Labs Platform.

What you will need:
1. Create a `labs.py` file in the root of your project.
2. In your `labs.py` file, import the `exp` object from your model.
3. In your `labs.py` file, create a variable called `model_dir` and assign it the path to the directory that contains your model.
4. In your cadCAD configuration, supply a `model_id`.
 
Because you used the CLI tool to create your starting model, the first three steps have already been taken care of for you.  You will still need to do the last step to create a model_id in your cadCAD configuration.
 
1. From the Labs Platform, go to your project and select the ‘Simulations’ tab.

2. Click on ‘Run Simulation’
- On the ‘General Info’ step, enter a name for your simulation.  If a branch isn’t selected, you will need to choose which branch your simulation is located.
- If you run into a Labs.py error, please review this video on the steps to fix: https://www.youtube.com/watch?v=WFUtcP6u56Y
- After a few seconds, your available system models will be listed on the ‘System Models’ step.  Select all the system models that are applicable to the simulation run.
- On the ‘Time & Cost’ step, review the estimated time and cost to execute the simulation and make sure you select your payment method.  If everything looks acceptable, click ‘Execute’ on the lower right of the screen.
3. After you execute the simulation, you will be taken back to the ‘Simulations’ tab of your project and a simulation will be added to your list of simulations.

4. Once your simulation finishes executing, You will want to note the ID for your simulation.

![Simulation ID](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/Simulation%20ID.png)

5. click on the ‘JupyterLab’ tab and start the server.  
- It takes about 1 minute the server status to change to RUNNING.
6. Once the button changes to 'Open Server', click on the button to launch JupyterLab.

![JupyterLab Tab Started](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/JupyterLab%20Tab%20Started.png)

7. Using the Launcher tab, click on the Python3 (ipyKernal) under the Notebook section to open a new Jupyter Notebook.

8. Since you entered JupyterLab from the Labs Platform, you are auto authenticated under the same username and password you use to log into the Labs Platform.  Because of this, you can use the Labs SDK to access the simulation results in the database.  In the first cell, enter in the following code:

`import pandas as pd`

`from blocksciencelabs import Client`

`labs = Client()`

`results = labs.fetch_results(<simulation ID>)`

`df = pd.DataFrame(results)`

`df`

- Example 1: `results = labs.fetch_results(24)`
- Example 2: `results = labs.fetch_results(136)`

9. Now that your simulation results are in a dataframe, you can proceed to explore your data during your post-processing analysis.  Visualization and graphical Python packages are not added intentionally so that you can choose the package that works best for you.  You can `pip install` the package of your choice directly in the Jupyter Notebook using the following example code:
- Example 1: `!pip install matplotlib`
- Example 2: `!pip install plotly`

REMINDER: If you perform your analysis in the Labs Platform, be sure to commit your changes in the terminal.  See the example above to make your commits from the terminal.

# Part 3: Sharing Your Work

Now that you have finished your analysis and have results that you want to share, you will want to add others to your project so that they can see your work.

1. Within your project, click on the ‘Access Control’ tab.

![Add Collaborator Tab](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/Add%20Collaborator%20to%20a%20Project.jpg)

2. Click on the ‘Add Collaborator’ button.

![Add Collaborator Button](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/Add%20Collaborator%20Button.png)

3. Enter in the email address of the user that you want to invite to your project and click the ‘Add Collaborator’ button.

![Add Collaborator Modal](https://raw.githubusercontent.com/cfrazier1978/Quick_Start_Guide/main/Images/Add%20Collaborator%20Modal.png)

- Their name will be added to the list of users with access to the project.
- The invited user will now see the project added to their Project’s dashboard.  They will be able to navigate to the ‘Notebook’ tab and see your Jupyter Notebook.

Do you have any questions or comments regarding this quick start guide?  Please let us know at contact@blocksciencelabs.com.
