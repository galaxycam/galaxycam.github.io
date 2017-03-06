# Practical Session 6: Data visualisation

## Biological visualisation

As we have already experienced, we can visualise data using UCSC genome browser but biological data can also be visualised in the Galaxy in-built genome browser called *Trackster*. Trackster is for the high-throughput sequencing era. It deals particularly well with very large data sets, and numerous simultaneous tracks.

### Visualise in Trackster.

1. Go to **'Shared Data' > 'Histories'**. Import in your history **'Promoters with TAF1'**.
2. Click on data set **'TAF1_ChIP_chr11',** then **'Visualize'** chart icon and **'Trackster'**.
3. Click **'View in new visualization'** and enter the name **'TAF1_ChIP_chr11_Vis'** and click on **'Create'** button.
4. Select **'chr11'** from the drop down menu.
5. Click on the plus icon **'Add tracks'** and select '**UCSC_Human_RefGene_chr11_Promoters**' and **'Join_Promoters_TAF1s_chr11'.** Click **'Add'**.
6. Zoom into region **chr11:1,856,968-1,861,997.**
7. Track can be configured by clicking on the gear icon next to them when going over their names.
8. Do not forget to click **'Save'** to keep your visualisation within Galaxy for viewing it another time or sharing it with others.

### Retrieve shared data.

The visualisation created in this section can be found in **'Shared Data' > 'Visualizations'**. It is called **'TAF1_ChIP_chr11_Vis'**.

## Numerical visualisation

Tabular results can be visualised with Galaxy using Charts plugin.  We will be looking at a [Gapminder](https://www.gapminder.org/) dataset as well as differentially expressed genes for breast cancer.

### Scatter plot with Gapminder dataset

From the famous YouTube presentation on *'The best stats you've ever seen'* by Hans Rosling, we are going to plot GDP against life expectancy for all the countries in the given dataset for 2002.

1. Create new history named **'Gapminder'**
2. Get data from this URL: [https://raw.githubusercontent.com/galaxycam/galaxy-intro/master/data/gapminder.txt](https://raw.githubusercontent.com/galaxycam/galaxy-intro/master/data/gapminder.txt)
3. Filter only 2002 data using **Filter and Sort > Filter** tool and rename the result to **'gapminder_2002'**
4. Click on the dataset newly created to expend it. Click on the Visualize chart icon, and select **'Charts'** to make a new chart.
5. Provide a title **'Gapminder 2002'**
6. Click on **'Scatter plot'** type
7. Click on **'Select data'** tab, and fill the forms with label and columns:
  - Provide a label: **country (2002)**
  - Data point labels: **Column: 1 (country)**
  - Values for x-axis: **Column: 6 (GDP)**
  - Values for y-axis: **Column: 4 (lifeExp)**
8. Click on **'Customize'** tab to set X-Axis and Y-Axis labels, X-Axis should be set to 'GDP' and Y to 'lifeExp'.
9. Click on **'Visualize'** in the top right corner.

**EXERCISE 6.1.** Do the same plot for 1952 data. Join these two datasets from 2002 and 1952 to draw a scatter plot for these two different years on one panel only.

#### Retrieve shared data.

The visualisations created in this section can be found in **'Shared Data' > 'Visualizations'**. They are called **'Gapminder 2002'**, **'Gapminder 1952'**, and **'Gapminder 1952vs2002'**.


### Heatmap of differentially expressed genes

We are now going to visualize a Breast cancer dataset of 337 patients, for 75 most differentially-expressed genes.

1. Create new history named **'Heatmap'**
2. Get data from this URL: [https://raw.githubusercontent.com/galaxycam/galaxy-intro/master/data/heatmap.txt](https://raw.githubusercontent.com/galaxycam/galaxy-intro/master/data/heatmap.txt) and rename it to **'heatmap_data'** and convert it to **'tabular'** format
3. Click on the dataset newly uploaded to expend it. Click on the Visualize chart icon, and select **'Charts'** to make a new chart.
4. Provide a title **'Heatmap'**
5. Click on **'Clustered heatmap'** type
6. Click on **'Select data'** tab, and fill the forms with label and columns:
  - Provide a label: **Heatmap of differentially expressed genes**
  - Column labels: **Column: 2 (sample)**
  - Row labels: **Column: 1 (gene)**
  - Observation: **Column: 3 (value)**
7. Click on **'Customize'** tab to set X-Axis and Y-Axis labels, X-Axis should be set to 'samples' and Y to 'genes'.
8. Click on **'Visualize'** in the top right corner.

To retrieve your graphs, you can go to the top menu **'Visualization'** > **'Saved Visualizations'**, **'Heatmap'** should be listed.

#### Retrieve shared data.

The visualisations created in this section can be found in **'Shared Data' > 'Visualizations'**. They are called **'Heatmap'**.

## Scratchbook

Galaxy comes with a Scratchbook to help you visualise different plots at the same time. You can try add both Gapminder plots next to each other for 152 and 2002 using this functionality.

1. Click on **'Analyze Data'**, then on the square icon near the 'User' menu. When the scratchbook is activated, the icon should be yellow.
2. Click on **'Visualization' > 'Saved Visualizations'**
3. Select a visualization and repeat the process by selecting **'Visualization' > 'Saved Visualizations'** and select one again
4. Resize all visualizations so they fit into the screen
5. To show/hide scratchbook, click on the new eye icon on the top right corner.

## Congratulation! You reached the end!

Remember...

- Our course webpage: [http://galaxycam.github.io/](http://galaxycam.github.io/)
- Galaxy main: [https://usegalaxy.org/](https://usegalaxy.org/)
- To fill the course survey ;-)
