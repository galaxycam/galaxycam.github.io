# Practical Session 1: The Galaxy interface

Galaxy allows experimental biologists without any programming experience to easily manipulate sequencing data using a point and click interface. For this practical, all the necessary tools and software are pre-installed.

# Setting up your Galaxy account

Go to [*group 1*] [http://52.207.211.93/](http://52.207.211.93/) or [*group 2*] [http://54.208.203.229/](http://54.208.203.229/)

Go to the **User** link at the top of Galaxy interface and choose **Register** (unless of course you already have an account). Then enter your information and you're in!

This will allow all the work that you create to be saved between sessions and allow you to name, save, share, and publish Galaxy histories, workflows, datasets and pages in a limited space set by your administrator of usually of 250GB.

The little indication bar at the top right corner of your Galaxy page **'Using ...MB'** will show your current usage. If you exceed your quota, no further jobs will be run until you have (permanently) deleted some of your datasets.

# The Galaxy UI

The left-hand panel is the *tool panel*, which contains our tools. The *main panel* is the interface between tools and data and is located in the middle. The Menu appears across the top of the main panel. The *history panel* is on the right.

# The tool panel

The tool panel contains all the tools available to Galaxy. The tools are categorised into groups of similar function (e.g. Text Manipulation). Clicking on a group reveals an expanded list of tools available under that category.

# The main panel

The main panel is where you set the parameters for the current tool in use. Clicking on a tool will load it into the main panel, where you will see a range of parameters (most with default settings) applicable to that tool. This is also where you select which datasets to load into the tool.

# The history panel

The history panel contains details of all the datasets that we have imported or created, plus the order in which they were created. All imported data will appear as a history item in the panel and the output from each tool will appear as at least one history item (depending on the number of output files the tool creates).

A history item will usually be one of 4 colours:

* **Green** - the task has completed successfully
* **Yellow** - the task is currently running
* **Grey** - the task is queued to run
* **Red** - the task failed

## History items

Each consecutively numbered history item has a number of parts to it. In the top right corner of each history item are three icons - an eye, a pen and a cross.

* **Eye** - clicking on the eye icon will show the data for that item in the main panel.
* **Pen** - this will show all the attributes for this history item (history item name, datatype, number of comment lines, etc.). It can be used to rename the history item or change information about it (e.g. to specify that a fastq file is actually in fastq sanger format).
* **Cross** - clicking on this will delete the history item.

By clicking on the history item name the item will expand to reveal a number of extra items. It will also show the first few lines of the dataset.

# The top panel menu

This menu appears across the top of the main panel. It contains a number of menu items:

* **Analyze Data** - this brings you back to the Home Screen.
* **Workflow** - this allows you to use workflows - pre-written pipelines of analysis.
* **Shared Data** - this is where you will obtain data shared with you on this Galaxy instance.
* **Visualization** - this is where you will visualise dataset or retrieve stored ones.
* **Help** - this is where you'll find the Galaxy wiki, tutorials and help from the Galaxy community.
* **User** - Saved Datasets: this is where you'll be able to see all your datasets from each of your histories. If you want to move data between histories, this is where you can do it. You can also see all your current histories and any Pages (notes and instructions that you can write and share with others).

# Galaxy Interactive Tour

1. Click on **'Help'** from the top panel menu and select **'Interactive Tours'**
2. Click on **'Galaxy UI'** for a gentle introduction to the Galaxy User Interface. This short tour will upload data into your history, and guide you through Galaxy's user interface.
3. Name this history **'Interactive Tour'**.
