# Practical Session 4: Interval Operations

## Basic operations

### Create a new history

1. At the top of the History column click on the Options gear and select **'Create new'**.
2. A new **'Unnamed history'** is created. Rename it to be **'Interval Operations'**. Hit enter to save it.

### Obtain the UCSC repeat regions on human chromosome 22 from UCSC.

1. Go to **'Get Data' > 'UCSC Main'**
2. Select
  - genome: 'Human';
  - assembly: 'Feb. 2009 (GRCh37/hg19)';
  - group: **'Repeats'**;
  - track: 'RepeatMasker'. RepeatMasker is a program that screens DNA sequences for interspersed repeats and low complexity DNA sequences.;
  - table: 'rmsk';
  - region: select **'position'**; enter **'chr22'**
  - output format: 'BED - browser extensible data';
  - tick Send output to 'Galaxy'.
  - Make sure that your settings are exactly the same (in particular, region should be set to **'position' 'chr22'**, output format should be set to **'BED - browser extensible data'**, and **'Galaxy'** should be checked by Send output to option). Click **'get output'**.
5. On next page make sure under Create one BED record per is set to **'Whole Gene'** and click **'Send Query to Galaxy'**.
6. On the right hand side panel, in the history, once the newly created file "UCSC Main on Human knownGene (genome)" turns green, click the pencil **'Edit Attribute'** to change the file name to be '**UCSC_Human_rmsk_chr22**', and click **'Save'**.

### Load all coding exons on human chromosome 22 from shared library.

1. Click on the menu **'Shared Data'** from the top panel, then **'Data Libraries'.**
2. Click on **'GalaxyCam Training'** then on **'loading_data'**.
3. Check the box next to '**UCSC_Human_refGene_chr22_Exons'** and click on top icon **'to History'** to import selected datasets into your history.

### Practice basic interval operations.

1. Click on **'Operate on Genomic Intervals' > 'Intersect'**.
2. Select Return: 'Overlapping intervals' of '**UCSC_Human_refGene_chr22_Exons'** that intersect: '**UCSC_Human_rmsk_chr22**', for at least: '1' (bp). This operation will return the exons which overlap with repeats regions. Click **'Execute'**.
3. Rename the returned file as: **'UCSC_Human_chr22_Intersect_on_Exons_Repeats'**, and click **'Save'**. You should see 392 regions.
4. Load **'UCSC_Human_chr22_Intersect_on_Exons_Repeats'** into UCSC browser.
5. Zoom into individual intersect regions, e.g.:  chr22:22,293,855-22,294,135 and chr22:20,918,588-20,921,366, and compare the relationships between the intersect region as User Track with the exons and repeats regions.
6. Repeat step 2 with alternative return option Overlapping pieces of Intervals, what changed in the intersection regions this time?
7. Return to Galaxy, click on **'Operate on Genomic Intervals' > 'Coverage'**.
8. Select What portion of **'UCSC_Human_chr22_Intersect_on_Exons_Repeats'**, is covered by '**UCSC_Human_rmsk_chr22**'. This returns the counts and percentage of bases for the intervals in the first dataset which are also covered by the intervals in the second dataset. Click **'Execute'**.
9. Rename the result data set to **'UCSC_Human_chr22_Coverage_Intersect_by_rmsk'**, and click **'Save'**.

### Retrieve shared data.

The history of this section can be found in **'Shared Data' > 'Histories'**. It is called **'Interval Operations'**.

## Identify promoter regions containing TAF1 binding sites

### Create a new history

1. At the top of the History column click on the Options gear and select **'Create new'**.
2. A new **'Unnamed history'** is created. Rename it to be **'Promoters with TAF1'**. Hit enter to save it.

### Extract only the TAF1 binding sites on chromosome 11 from TAF1

In the Loading Data section of this practical, we already obtained the genomic intervals of the TAF1 binding sites. Copy it to the current history. We are going to extract all the human gene coordinates.

1. From the new history, click on the gear icon 'History Options' and then **'Copy Datasets'**
2. Select **'Loading Data from library'** as Source History and tick the box next to **'TAF1_ChIP'** and select **'Promoters with TAF1'** as Destination History. Click on **'Copy History Items'**.
3. Then click on the Refresh history icon to see the dataset in your current history if it does not appear automatically.

First, let's focus on chromosome 11 and extract only the TAF1 binding sites on chromosome 11 from TAF1.

1. Select in Tools **'Filter and Sort' > 'Filter'**
2. Select Filter: **'TAF1_ChIP'**; with following conditions: **'c2=='chr11''**; leave Number of header lines to skip as 0; and Click **'Execute'**.
3. Rename the output interval file to **'TAF1_ChIP_chr11'**, and click **'Save'**.

### Obtain the coordinates of all the genes on Human chromosome 11.

1. Go to **'Get Data' > 'UCSC Main'**
2. Select
  - genome: 'Human';
  - assembly: 'Feb. 2009 (GRCh37/hg19)';
  - group: **'Genes and Gene Predictions'**;
  - track: **'RefSeq Genes'**;
  - table: 'refGene';
  - region: select **'position'**; enter **'chr11'**
  - output format: 'BED - browser extensible data';
  - tick Send output to 'Galaxy'.
  - Make sure that your settings are exactly the same (in particular, region should be set to **'position' 'chr11'**, output format should be set to **'BED - browser extensible data'**, and **'Galaxy'** should be checked by Send output to option). Click **'get output'**.
3. On next page make sure under Create one BED record per is set to **'Whole Gene'** and click **'Send Query to Galaxy'**.
4. On the right hand side panel, in the history, once the newly created file "UCSC Main on Human: refGene (chr11)" turns green, click the pencil **'Edit Attribute'** to change the file name to be '**UCSC_Human_RefGene_chr11**', and click **'Save'**.
5. Examine the output bed file, it should contain 3,473 regions.

### Retrieve 1000 bp upstream regions of each gene.

1. Select in Tools **'Operate on Genomic Intervals' > 'Get flanks'**
2. Select data '**UCSC_Human_refGene_chr11**' and set the Length of the flanking regions to **'1000'**. Click **'Execute'**.
3. Rename the output table to be '**UCSC_Human_RefGene_chr11_Promoters**', and click **'Save'**.

### Identify the promoter regions containing TAF1 binding sites.

1. Change datatype of **'TAF1_ChIP_chr11'** from tabular to interval by editing the attributes of this dataset (pencil icon in history), click on tab **'Datatype'** , select for New Type: **'interval'** and click on **'Save'** button. Click on tab **'Attributes'**, and select Chrom column: **'2'**, Start column **'3'**, End column **'4'**. Database/Build should be set to 'Human Feb. 2009 (GRCh37/hg19) (hg19)'. Click **'Save'**.
2. Select in Tools **'Operate on Genomic Intervals' > 'Join'**
3. Join '**UCSC_Human_RefGene_chr11_Promoters**' with **'TAF1_ChIP_chr11'** with min overlap set to '1', and Return set to 'Only records that are joined (INNER JOIN)'. Then click **'Execute'**.
4. Rename the output to **'Join_Promoters_TAF1s_chr11'**, and click **'Save'**.
5. It returns 12 regions.

### Examine these intervals in UCSC genome browser.

1. Select in Tools **'Graph/Display Data' > 'Build custom track'**.
2. Click **'Insert Track'**, select Track 1: **'TAF1_ChIP_chr11'**, name: **'TAF1'**, color: **'Blue'**, visibility: **'Full'**;
3. Click **'Insert Track'**, select Track 2: '**UCSC_Human_RefGene_chr11_Promoters**'; name: **'Promoters'**; color: **'green'**, visibility: **'Full'**;
4. Click **'Insert Track'**, select Track 3: **'Join_Promoters_TAF1s_chr11'**, name: **'Overlaps'**; color: **'Red'**, visibility: **'Full'**.
5. Click **'Execute'**. This returns a Build Custom Track.
6. Click on the returned dataset to expend it. Then click **'Display at UCSC main'**.
7. View the custom track file in the UCSC genome browser. Zoom into region **chr11:1,856,968-1,861,997** to check which gene's promoter region contain TAF1 sites.

**EXERCISE 4.1**. Repeat above steps for looking at overlapping pieces of intervals with the Intersect function using **'Operate on Genomic Intervals' > 'Intersect'** and compare the difference between the outputs.

### Retrieve shared data.

The history of this section can be found in **'Shared Data' > 'Histories'**. It is called **'Promoters with TAF1'**.

## Finding coding exons with highest SNP density

The goal here is to list all the exons on chromosome 22, sort them in descending order by the number of single nucleotide polymorphism they contain, and name the gene symbols associated with the top 100 exons in the list.

*Outline*:
* Retrieve all Human coding exons on chr22 from UCSC.
* Retrieve all Human SNP data on chr22 from UCSC.
* Joining exons with SNPs to find the intersections between these two files.
* Count the number of SNPs falling in each exon and rank the exons by their associated SNP density.

### Create a new history

1. At the top of the History column click on the Options gear and select **'Create new'**.
2. A new **'Unnamed history'** is created. Rename it to be **'Exons with SNPs Density'**. Hit enter to save it.

### Retrieve all Human coding exons on chr22 from UCSC.

1. From the new history, click on the gear icon 'History Options' and then **'Copy Datasets'**
2. Select **'Loading Data from library'** as Source History and tick the box next to '**UCSC_Human_refGene_chr22_Exons**' and select **'Exons with SNPs Density'** as Destination History. Click on **'Copy History Items'**.
3. If needed, click on the Refresh history icon to see the dataset in your current history.

Examine the output bed file, it should contain 9,141 regions.

*Note:* The bed file 'UCSC_Human_refGene_chr22_Exons' in the shared history has 12,410 regions because it has been uploaded with track set to 'UCSC Genes' instead of 'RefSeq Genes'.

### Retrieve all Human SNP data on chr22 from UCSC.

1. Go to **'Get Data' > 'UCSC Main'**
2. Select
  - genome: 'Human';
  - assembly: 'Feb. 2009 (GRCh37/hg19)';
  - group: **'Variation'**;
  - track: **'Common SNPs(147)'**;
  - table: **'snp147Common'**;
  - region: position type **'chr22'**;
  - output format: **'BED - browser extensible data'**;
  - tick Send output to **'Galaxy'**.
  - Make sure that your settings are exactly the same then click **'get output'**.
3. On next page make sure under Create one BED record per is set to **'Whole Gene'** and click **'Send Query to Galaxy'**.
4. Rename the output dataset to '**UCSC_Human_chr22_SNPs**', and click **'Save'**.
5. Click the eye logo to view the returned file. It contains ~190,000 regions.

### Joining exons with SNPs

1. Go to **'Operate on Genomic Intervals' > 'Join'**
2. Select Join: '**UCSC_Human_refGene_chr22_Exons**' with: '**UCSC_Human_chr22_SNPs**' with min overlap: '**1**', Return: **'Only records that are joined'**, and click **'Execute'**.
3. Rename the returned file '**UCSC_Human_chr22_Exons_SNPs_join**'. It contains 5,715 regions.

*Note:* With the right 'UCSC_Human_refGene_chr22_Exons' dataset, the returned file contains 4,018 regions.

### Counting the number of SNPs per exon

1. This can be easily done with the **'Join, Subtract, and Group' > 'Group'** tool.
2. Select data '**UCSC_Human_chr22_Exons_SNPs_join**'.
3. Choose column 4 by selecting **'Column: 4'** in Group by column.
4. Then click on **'Insert Operation'**
5. Operation 1 Type: **'Count'**, On column: **'Column: 4'**, and click **'Execute'**.
6. Rename the result dataset to **'UCSC_Human_chr22_Exons_SNPs_join_count'** and click **'Save'**.
7. The result dataset contains two columns and 3,403 lines. The first contains the exon name while the second shows the number of times this name has been repeated in the dataset '**UCSC_Human_chr22_Exons_SNPs_join**'.

### Sorting Exons by SNPs counts

To see which exon has the highest number of SNPs we can simply sort the dataset **'UCSC_Human_chr22_Exons_SNPs_join_count'** on the second column in descending order.

1. This is done with **'Filter and Sort' > 'Sort'** tool.
2. Select Dataset: **'UCSC_Human_chr22_Exons_SNPs_join_count'**, on column **'Column: 2'**, with flavor 'Numerical sort', everything in: 'Descending order', the click on **'Execute'**
3. You can now see that the highest number of SNPs per exon is 31.
4. Rename the dataset to **'UCSC_Human_chr22_Exons_SNPs_join_count_sort'**

### Selecting top one hundred

Now let's select top 100 exons with the highest number of SNPs.

1. For this we will use **'Text Manipulation' > 'Select First'** tool.
2. Select first: **'100'** from **'UCSC_Human_chr22_Exons_SNPs_join_count_sort'**
3. Rename the dataset to '**UCSC_Human_chr22_Exons_SNPs_join_count_sort_top100'**

### Recovering exon information and displaying data in genome browsers

Now we know that in this dataset the top one hundred exons contain between 5 and 31 SNPs. But what else can we learn about these? To know more we need to get back the positional information (coordinates) of these exons. This information was lost at the grouping step and now all we have is just two columns.

To get coordinates back we will match the names of exons in dataset '**UCSC_Human_chr22_Exons_SNPs_join_count_sort_top100'** (column 1) against names of the exons in the original dataset '**UCSC_Human_refGene_chr22_Exons**' (column 4).

1. This can be done with **'Join, Subtract and Group' > 'Compare two Datasets'** tool
2. Compare: '**UCSC_Human_refGene_chr22_Exons**' Using column: **'Column: 4'** against: '**UCSC_Human_chr22_Exons_SNPs_join_count_sort_top100'** and column: **'Column: 1'** To find **'Matching rows of 1st dataset'**, then click **'Execute'.**
3. Rename the result file to **'UCSC_Human_chr22_Exons_top100_coordinates'**.
4. The best way to learn about these exons is to look at their genomic surrounding. There is really no better way to do this than using genome browsers. Because this analysis was performed on 'standard' human genome, you have two choices: UCSC Genome Browser and Ensembl.
5. For example, clicking on **'display at UCSC main'** will show the regions, look at 'User Track' on top of the browser image.

### Retrieve shared data.

The history of this section can be found in **'Shared Data' > 'Histories'**. It is called **'Exons with SNPs Density'**.

### Something To think about

Why not use the Intersect function here? What happens if you use Intersect here? What happens when you swap the order of the two files to be intersected?

The resulting table by the Join function Exons_SNPs_joined is a combination of 6 columns of the exon table and 6 columns of the SNP table. It returns n-to-n matches between the exon records and the SNP records, i.e. every exon can map to multiple SNPs and every SNPs can map to multiple exons. The resulting table by the "intersect" function returns 1-to-n matches, and every record of the first input file are compared against all the records of the second input file. Also, the results of Intersect do not contain information on both exons and SNPs.

**EXERCISE 4.2.** Apart from the above functions that we have introduced, there are also the following useful genomic interval functions: Subtract, Merge, Base coverage, Complement, Cluster etc... Practice these functions with your existing datasets.

Below are relevant tutorials for you to view in your own time:
* [http://screencast.g2.bx.psu.edu/GOPS_Cluster/](http://screencast.g2.bx.psu.edu/GOPS_Cluster/)
* [http://screencast.g2.bx.psu.edu/quickie5_join/flow.html](http://screencast.g2.bx.psu.edu/quickie5_join/flow.html)

## Next session

[Practical Session 5: Workflows](galaxy_intro_session5.md)
