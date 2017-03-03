# Practical Session 2: Getting started

## Getting data

### Create a new history

1. At the top of the History column, click on the Options gear and select **'Create new'**.

2. A new **'Unnamed history'** is created.

We shall start by obtaining some data, inspecting it and running a simple job on it.

1. Click on **'Shared Data'** from the menu and select **'Data Libraries'**.

2. In the list of Data Libraries you will see one called **'GalaxyCam Training'**. Click on this and you will see a couple of sub folders.

3. Click on the folder **'getting_started'** and check the box next to **'Test.fasta'**. Click on top icon **'to History'** to import selected datasets into your history, select the history **'Unnamed history' **you wish to import the data into and click **'Import'**.** **

4. A green box signaling that your task has been performed successfully will appear at the top right corner of your screen.

5. Click on **'Analyze Data'** in the menu to return to the main interface. The Test.fasta sequence should now be in your history.

## Renaming the History

Instead of working with an unnamed history, we shall call our history something meaningful.

1. At the top of the History column click on the Options gear and select **'Saved Histories'**. Any histories that are currently available will be shown in the central panel. You should see your **'Unnamed history'** there.

2. Click on your 'Unnamed history' from the right hand side panel, to rename it. A box will appear for you to create a new name for your history. Rename it by calling it something meaningful. In this case we'll call it **'Getting Started'**. Hit enter to save it.

## Examining the data

We'll now have a good look at our data and all of its attributes.

1. Click on the dataset name **'Test.fasta'**.

2. The dataset will expand and we will see lots of information about the dataset, including a quick peek at the data itself and what format Galaxy thinks the data is (fasta).

3. Click on the **eye icon**. The data connected with this dataset will appear in the Main Panel. We can see that the data is in fasta format. If the dataset was very big, then only the first few hundred lines would be displayed.

4. Click on the **pen sign** (attributes). You can now see all the attributes associated with this dataset divided into sections. The name, annotation, data type, etc. are all editable.

5. We shall **rename the dataset**. In the 'Name' field, remove 'Test.fasta' and call it something else, e.g. **'Galaxy_sequence.fasta'**. Click on **'Save'** at the bottom of the current section. You should see that your history item now has a new name.

## Using our data in a tool

### FASTA manipulation

Calculate the length of the sequence

1. Click on the **'FASTA manipulation'** tools from the Tools panel on your left.

2. Select **'Compute sequence length'**. This tool counts the length of each fasta sequence in the file.

3. From the dropdown menu select the FASTA sequence file you wish to get its length, here should be 'Galaxy_sequence.fasta'. Leave '0' to keep the whole thing. Click on **'Execute'.**

4. Click on the dataset newly created in your history **'Getting Started'** to see the result. The length of the sequence is 444 bases.

Change the width of the output FASTA

1. Select **'FASTA Width'** from under **'FASTA manipulation'** tools. This tool reformats a FASTA file, changing the width of the nucleotide lines. Outputting a single line (with width = 0) can be useful for scripting (with grep, awk, and perl). Every odd line is a sequence identifier, and every even line is a nucleotides line.

2. From the dropdown menu select the FASTA sequence file you wish to change the width of, this should be 'Galaxy_sequence.fasta'. Click on **'Execute'.**

### Text manipulation

Galaxy contains a number of text manipulation tools to help us work with files. For example, if we had lots of files all with a single fasta file in each, we could create a single multi-fasta file from them. We'll do that now.

1. Click on **'Shared Data' > 'Data Libraries'** and go back to the **'GalaxyCam Training'** data library.

2. Under **'getting_started'** click on the '**Pinfestans**' folder. You will see three files, each one a P. infestans effector gene. Select all three files (you can select all the files by clicking in the box next to 'name' in the top orange bar) and import them into your current history called 'Getting Started'.

3. Click on **'Analyze Data'** in the menu to return to the main interface. The three sequences should now appear in your history as separate items.

4. We will now use one of Galaxy's tools to create a multi-fasta file. Select the tool **'Text Manipulation' > 'Concatenate datasets'**

5. This will load the tool interface into the main panel. We have 3 P. infestans fasta sequences in our history, select from the drop down list **'PinfestansAVH9.fasta'** for Concatenate Dataset , then use the **'Add new dataset'** button twice to add the other two fasta files. Select as Dataset 1; **'PinfestansAVRblb1.fasta'** and as Dataset 2 **'PinfestansAVRblb2.fasta'**. Hit **'Execute'**.

6. Wait for the tool to finish and then click on the eye symbol of the new history item. You should have all 3 sequences in just one file.

### Filtering data

The Galaxy way to do things is to put different tools together in pipelines to accomplish more complex tasks. This allows us to have a few generic tools that can be used in various analysis steps, rather than having a lot of tools that only do a specific task.

Our last task in this part of the tutorial will be to take two small datasets and use the information in both of them to filter out data we're not interested in and drill down to data that we are interested in.

1. Go to the top of the History panel, click on the gear icon called 'History Options' and select 'Create New' to create a new history. Name the history **'NBLRR Filter'**.

2. Go to **'Shared Data' > 'Data Libraries' > 'GalaxyCam Training' > 'getting_started' > 'NBARC'**, and import the two datasets **'SequenceInfo.tabular'** and **'NB_domains.tabular'**.

3. **EXERCISE 2.1. Select only the NB-ARC sequences that are longer than 1300 nts and have a GC content over 0.5.** Take a look through the tools in Galaxy, try and figure out how to combine the information in both files and then filter for the information that you're interested in.

*Hint*: You'll need to look at tools in the 'Join, Subtract and Group' section and also in the 'Filter and sort' section.
