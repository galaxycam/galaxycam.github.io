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

Tabular results can be visualised with Galaxy using Charts.  We will be looking at functional interaction scores between proteins.

### Unclustered Heatmap

1. Create new history named **'Charts'**
2. Get data from this URL: [http://www.compsysbio.org/bacteriome/dataset/functional_interactions.txt](http://www.compsysbio.org/bacteriome/dataset/functional_interactions.txt)
3. Click on the dataset newly uploaded to expend it. Click on the Visualize chart icon, and select **'Charts'** to make a new chart.
4. Give it a name **'Unclustered Heatmap'**
5. Double click on **'Heatmap'** type
6. Choose Column: 1 for Column labels; Column: 2 for Row labels; and Column: 3 for Observation.
7. Click on **'Draw'** in the right corner.

To retrieve your graphs, you can go to the top menu **'Visualization'** > **'Saved Visualizations'**, 'Unclustered Heatmap' should be listed**.**

### Clustered Heatmap

1. Make a new chart from the same dataset called [http://www.compsysbio.org/bacteriome/dataset/functional_interactions.txt](http://www.compsysbio.org/bacteriome/dataset/functional_interactions.txt)
2. Give it the name **'Clustered Heatmap'**
3. Double click on **'Clustered Heatmap'** type
4. Choose Column: 1 for Column labels; Column: 2 for Row labels; and Column: 3 for Observation
5. Click **'Draw'**
6. Use the mouse	wheel or your touchpad to zoom into	the bottom left hand side of the graph as shown below
7. Tooltips pop up if you move the mouse pointer over a box. Find the interaction between B4143 and B3295, you should be able to see it associated value of 0.271021.
8. Click on the **Editor** icon in the right corner to further customize this chart.
9. Go to the **Configuration** tab.
10. Paste a database URL into the template URL field and add the __LABEL__ tag. You may	use [http://www.ncbi.nlm.nih.gov/geoprofiles/?term=__LABEL__](http://www.ncbi.nlm.nih.gov/geoprofiles/?term=__LABEL__) or any other database. Click on **'Draw'** to redraw the chart. Data points are now linked to web sources.
11. Double click on a box and the browser will open two	new tabs using the previously defined URL template.
12. Select one element, find the interaction between B4143 and B3295 again. What are the corresponding protein functions?

### Analyze the protein distribution with a discrete histogram

1. Make a new chart from the same dataset called [http://www.compsysbio.org/bacteriome/dataset/functional_interactions.txt](http://www.compsysbio.org/bacteriome/dataset/functional_interactions.txt)
2. Give it a name **'Discrete Histogram'**
3. Double click on **'Discrete Histogram'** type
4. Choose Column: 1 for Observations
5. Click **'Add Data'**, select Column: 2 for Observations
6. Click on **'Draw'**
7. Which proteins have most interactions?
  - B4143 Chaperon ([http://www.ncbi.nlm.nih.gov/geoprofiles/?term=B4143](http://www.ncbi.nlm.nih.gov/geoprofiles/?term=B4143))
  - B3295 RNA Polymerase ([http://www.ncbi.nlm.nih.gov/geoprofiles/?term=B3295](http://www.ncbi.nlm.nih.gov/geoprofiles/?term=B3295))
8. Click on **Screenshot** and select **'Save as PNG'** to save the chart onto your desktop as a PNG file.

### Retrieve shared data.

The visualisations created in these sections can be found in **'Shared Data' > 'Visualizations'**. They are called 'Unclustered Heatmap', 'Clustered Heatmap', and 'Discrete Histogram'.

### Scratchbook

1. Click on **'Analyze Data'**, then on the top right corner, click on the square icon near the percentage usage bar. When the scratchbook is activated, the icon should be yellow.
2. Click on **'Visualization' > 'Saved Visualizations'**
3. Select a visualization and repeat the process by selecting **'Visualization' > 'Saved Visualizations'** and select one again
4. Resize all visualizations so they fit into the screen
5. To show/hide scratchbook, click on the new eye icon on the top right corner.
