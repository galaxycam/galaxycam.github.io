# Practical Session 5: Workflows

The Galaxy workflow system allows users to create pipelines of analysis that they can then use to re-run the same analysis steps as often as they require. They can also share the workflows between other  Galaxy users (e.g. users in the same lab or collaborators at distant institutions) who can then import the workflow and then run the analyses using the same parameters. Galaxy workflows can also be published as supplementary data for papers, so making all analysis totally transparent.

## Create workflow from history

One of the powerful functions of Galaxy is its ability to allow you to extract a workflow from the tasks you have completed and to re-apply the workflow to similar tasks repeatedly.

1. In History panel, click **'Options'** > **'Saved Histories'**. Select the history which you would like to extract the workflow process from. In this case, let's select the task we completed earlier from the history named **'Exons with SNPs Density'**.
2. Once the datasets of this history are all loaded and can be viewed from the History panel, click **'Options'** > **'Extract workflow'** to start the extraction process.
3. Rename the workflow to **'Finding_Exons_with_highest_SNP_density'**.
4. All the tools and history items used in your current history will appear in the main panel. It shows that the first steps of loading data from UCSC cannot be automated, and the output files from these steps need to be provided to the workflow. Following that, the steps which could be included are: Join, Group, Sort, Select first, and Compare two Datasets. Tick these functions by order to include them in the new workflow. If there are tools or datasets you don't want to use, uncheck them.
5. Click **'Create workflow'.**

### Modify the existing workflow.

1. Click **'Workflow'** from the Menu to go to the workflow view, select the workflow **'Finding_Exons_with_highest_SNP_density' **to modify, and click on **'Edit'**.
2. In the workflow view, each box represents either an input/output file or a function in the process. The arrows between the boxes represent the input and the output directions and the order of the process. The relationship between two boxes can be modified or removed by dragging and adding or deleting the arrows between the boxes.
3. Select the function **'Select first' **to modify, in the right panel called Details, change the parameter 'Select first:' from '100' to **'10'** to have the top 10 records to be selected.
4. When finishing adjusting all the parameters of all the functions on the workflow canvas, do not forget to save it by clicking on the gear icon and select **'Save'**.

### Apply the workflow on a new dataset.

Workflow can be run over and over again on any suitable datasets.

1. Click on **'Analyze Data' **menu and create a new history called **'Run Exons with SNPs Density on chrX'**
2. Download all Human coding exons of chrX instead of chr22, [following these steps done previously for chr22,](#heading=h.18uaj65a7fvg) and save it as **'UCSC_Human_refGene_chrX_Exons'** from UCSC.
3. Download all Human SNP dataset of chrX, [following these steps done previously for chr22, ](#heading=h.vvvycopd9htp)and save it as '**UCSC_Human_chrX_SNPs**'.
4. Click **'Workflow'** in the Menu, select the workflow **'Finding_Exons_with_highest_SNP_density'** to be run, click on the drop down menu and select **'Run'**.
5. On the 'Running workflow' page select the input data files.
6. Select for Step 1 Input dataset **'UCSC_Human_refGene_chrX_Exons'** and for Step 2 Input dataset '**UCSC_Human_chrX_SNPs**'. Then click **'Run workflow'**. All the steps will be sequentially executed without any further interventions needed.
7. When all the jobs have finished, click on the last dataset in your history to see the result file.

### Share the workflow.

You could share the workflow. Go to the workflow view and select the workflow you would like to share. Click the dropdown menu and select **'Share or Publish'**. Same as sharing the histories, you can share your workflow either through a publicly accessible link e.g.  [http://52.207.211.93/u/pajanne/w/findingexonswithhighestsnpdensity](http://52.207.211.93/u/pajanne/w/findingexonswithhighestsnpdensity) [group 1] or [group 2] or with specific users.

### Retrieve shared data.

The workflow used in this section can be found in **'Shared Data' **> **'Workflows'**. It is called 'Finding_Exons_with_highest_SNP_density'**.**

The history of this section can be found in **'Shared Data' **> **'Histories'**. It is called 'Run Exons with SNPs Density on chrX'.

## Create a new workflow

### Select 50 longest exons from a list of exons.

1. Go to the workflow view, click **'Create new workflow' **button, name it **'Select_50_longest_Exons'** and click **'create'**. This will take you to a blank workflow canvas, where we will create our workflow.
2. To get your first tool onto the canvas just click on it, so go to the tool section **'Text Manipulation'** and click on the tool **'Compute'** to calculate the length of exons.
3. A box entitled 'Compute' will appear on your canvas. The box should be surrounded in blue, which means that it's the currently selected box.
4. Put your cursor over the top part of the box and you should notice that it changes from a pointer to a cross. Click on the box and drag it to the top left corner of the canvas. You'll also notice that the box has a cross on it in the top right corner. Clicking on the cross will remove the tool from the canvas.
5. In the right-hand column (where your history usually is) are the details and parameters associated with the tool. We will edit some of these parameters.
6. Then, add the input dataset for this new workflow. On the left hand panel, at the top of all the tools, click **'Inputs'** and then **'Input dataset'** to select the input file for this workflow. A box entitled 'Input dataset' will appear on your canvas.
7. To connect the Input dataset and the Compute tool, simply click the outward arrow of the dataset, hold and drag to the inward arrow symbol of the tool. A green arrow indicates the input dataset datatype is compatible with the function. You can remove the connection by mousing over the connection and clicking on the cross.
8. Add next functions of this workflow in order: **'Filter and Sort' **> **'Sort'**, and **'Text manipulation' **> **'Select first'**. Now we have a workflow of three steps: Compute, Sort, and Select first. Connect the output file from each previous function to the next function as an input.  
9. Connect the output of the Compute tool with the input of the Sort tool; and the output of the Sort tool to the input of the Select first tool.
10. Now we are going to adjust the parameters for each tools by clicking on each tool box.
11. Click on the **'Compute'** tool, the input file has two columns that indicates the starts of an exon (c2) and its ends (c3). Therefore c3-c2 returns the length of that exon. In the right-hand column, under 'Add expression', you should have **'c3-c2'**. This will create a 7th column into the output dataset.
12. Click on the **'Sort'** tool, in the right-hand column under Sort Dataset on column enter **'7'** to order the length of the exon calculated at the previous step (be careful not to add a new column selection by hitting enter).
13. Click on the **'Select first'** tool,  in the right-hand column under Select first enter **'50'** to only get the first 50 results.
14. Go to the options at the top of the canvas, and click on **'Save'** to save the entire workflow.

**Congratulations!** - you've just created your first workflow and will save yourself lots of time!

### Running a workflow

1. Go to **'Analyze Data'**
2. Create a new history called **'Run Select 50 Longest Exons'**
3. Retrieve all Human coding exons of chr22 from data library 'GalaxyCam Training' > 'loading_data', called '**UCSC_Human_refGene_chr22_Exons'**.
4. Go to the workflow view, select the workflow you've just created called **'Select_50_longest_Exons'**, click on the drop down menu and select **'Run'**.
5. Select '**UCSC_Human_refGene_chr22_Exons'** as the input dataset, then click on **'Run workflow'.**
6. When all the jobs have finished, click on the last dataset in your history to see the result file. Examine the output, the last column shows the exon length by descending order.

### Retrieve shared data.

The workflow used in this section can be found in **'Shared Data' **> **'Workflows'**. It is called 'Select_50_longest_Exons'**.**

The history of this section can be found in **'Shared Data' **> **'Histories'**. It is called 'Run Select 50 Longest Exons'.

## Importing a workflow

From the Galaxy main portal [https://usegalaxy.org](https://usegalaxy.org) you can view and access all the published workflows and publish your own workflows there to share with others.

[https://usegalaxy.org/workflow/list_published](https://usegalaxy.org/workflow/list_published)

In addition to the Dataset, History, and Workflow objects, Galaxy also allows **Page** object to be published and shared. The Galaxy pages feature allows the creation of documents that integrate datasets, histories, and workflows, and it is often used as a complete document to record an entire analysis for a publication. This enables others to easily access and repeat the analysis.

The histories, workflows and visualisations of this tutorial are accessible on our Galaxy training instance as a published page under 'Shared Data' > 'Pages' and then **'GalaxyCam Intro Practical'**.

For example, **Galaxy Variant 101: Introduction to Polymorphism Detection via Variant Analysis**, Heteroplasmy: Mother-Child mtDNA Variant Polymorphism is a Galaxy page accessible here:

[https://usegalaxy.org/u/galaxyproject/p/galaxy-variant-101](https://usegalaxy.org/u/galaxyproject/p/galaxy-variant-101)

Try to download the published workflow and view it.

1. Go to the project page [https://usegalaxy.org/u/galaxyproject/p/galaxy-variant-101](https://usegalaxy.org/u/galaxyproject/p/galaxy-variant-101), and find **'Workflow'** section. Click on the **disk icon to save the workflow** file onto your computer and import it into another Galaxy instance, for example the one we are currently using for training today.
2. To import an external workflow, click on 'Workflow' in the Galaxy training instance and then click on the blue arrow button **'Upload or import workflow'**. Click on **'Browse…'** button and select the file you've just downloaded from the main Galaxy instance called 'Galaxy-Workflow-Galaxy_Variant_101.ga', then click **'Import'***.
3. When the import step completes, a message will show you the option to start using this workflow. Click **'Edit'** to view the graph of the entire workflow of this project. You can modify the parameters and apply this workflow to either the project dataset or your own dataset. Explore further options when you have the time.

> ***** If this import failed, you may wish to try a much simpler workflow: [https://usegalaxy.org/u/aun1/w/galaxy101-2015-1](https://usegalaxy.org/u/aun1/w/galaxy101-2015-1)

**EXERCISE 5.1.** Extract the genomic sequence of the 50 base pair region flanking each of the SNPs on human chromosome Y, and then package these steps into a reusable workflow.

*Hint*. Outline of steps:
* Extract coordinates of SNPs on Human chromosome Y.
* Extract coordinates of flanking regions around these SNPs.
* Extract genomic sequences of these flanking regions.
* Extract a workflow out of this task and share it.

## Next session

[Practical Session 6: Data visualisation](galaxy_intro_session6.md)
