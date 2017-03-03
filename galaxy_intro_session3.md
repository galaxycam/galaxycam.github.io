# Practical Session 3: Loading data

## Create a new history

1. At the top of the History column click on the Options gear and select **'Create new'**.
2. A new **'Unnamed history'** is created. Rename it to be **'Loading Data'**. Hit enter to save it.

## Upload file from your Computer

Upload the file containing Illumina TruSeq chr22 exome targeted regions into the **'Loading Data'** history.

1. Download this file onto your computer: '[https://raw.githubusercontent.com/galaxycam/galaxy-intro/master/data/truseq_exome_targeted_regions.hg19.bed.chr22.bed](https://raw.githubusercontent.com/galaxycam/galaxy-intro/master/data/truseq_exome_targeted_regions.hg19.bed.chr22.bed)' using your browser, then 'File' > 'Save Page As...'
2. On the left Tools panel, click on **'Get Data' > 'Upload File'** from your computer.
3. A popup window called **'Download from web or upload from disk**' appears and at the bottom of it, select **'Choose local file'** if your file is on your local computer or select 'Paste/Fetch data' to retrieve the file from this URL and select from your desktop the file **'truseq_exome_targeted_regions.hg19.chr22.bed'.** In the middle panel, select **'bed'** as the file format in 'Type' column, set Genome: **'Human Feb. 2009 (GRCh37/hg19) (hg19)**' and click **'Start'** at the bottom of the window. When the status is green and shows '100%', click on 'Close' to close the popup window.
4. On the right panel, click on the file name to see the file attributes.
5. Click on the **eye icon** to view the contents of the file in the middle panel.
6. Click on the **pen icon** to edit the attributes of the file like its name. Rename the file to **'illumina_truseq_exome_targeted_regions_hg19_chr22'** and click on **'Save'**.
7. Click on **'display at UCSC main'** to view the target regions as User Track.

## Upload file using a web link

Download the genomic intervals of the TAF1 binding sites.

1. Go to **'Get Data' > 'Upload File'**
2. At the bottom of the pop up window, select the third button **'Paste/Fetch data'**, Copy/Paste in the text box this url: '**http://galaxyproject.org/CPMB/TAF1_ChIP.txt**', Select Genome: **'Human Feb. 2009 (GRCh37/hg19) (hg19)**' and click **'Start'**. When completed, click on **'Close'**.
3. In the History, click on the pencil to edit attributes; change the name of the file to **'TAF1_ChIP'**; and click on the **'Save'** button.

## Retrieve data from UCSC Main

Retrieve all coding exons on human chromosome 22.

1. Go to **'Get Data' > 'UCSC Main'**
2. Select
  - genome: 'Human';
  - assembly: 'Feb. 2009 (GRCh37/hg19)';
  - group: 'Genes and Gene Predictions';
  - track: **'RefSeq Genes'**;
  - table: 'refGene';
  - region: select **'position'**; enter **'chr22'**
  - output format: 'BED - browser extensible data';
  - tick Send output to 'Galaxy'.
  - Make sure that your settings are exactly the same (in particular, region should be set to **'position' 'chr22'**, output format should be set to **'BED - browser extensible data'**, and **'Galaxy'** should be checked by Send output to option). Click **'get output'**.
3. On next page make sure under Create one BED record per is set to **'Coding Exons' **and click **'Send Query to Galaxy'**.
4. On the right hand side panel, in the history, once the newly created file "UCSC Main on Human knownGene (genome)" turns green, click the pencil **'Edit Attribute' **to change the file name to be '**UCSC_Human_refGene_chr22_Exons**', and click **'Save'**.

Examine the output bed file, it should contain 9,037 regions.

## Retrieve data from BioMart Ensembl server

Retrieve Ensembl genes 85 on human chromosome 22 from BioMart.

**EXERCISE 3.1.** Retrieve all the genes (Ensembl Gene ID, Ensembl Transcript ID, start and end positions - if associated gene names selected it returns an error) on human chromosome 22 from Ensembl Genes 85 from BioMart Central server using database query mode.

*Hint*: Unfortunately the BioMart tool in the 'Get Data' section does not work, nevertheless it is still possible to extract the information from [http://www.ensembl.org/biomart](http://www.ensembl.org/biomart) into a file and import it into Galaxy. You should get a result file containing 4,473 genes.  

## Upload large files (>2GB) using FTP

To upload large files into Galaxy, you could use FTP instead of the browser. Files need to be transferred to the Galaxy FTP address and then uploaded into your history. [Here](http://wiki.bits.vib.be/index.php/Galaxy_beginner%27s_tutorial#Upload_big_files_.28.3E_2GB.29_using_FTP) is a clear step by step tutorial for this function.

## Download data from shared data library

Alternatively, you could import into your history all the data files from a shared data library prepared for this part of the practical.

1. Create a new empty history called **'Loading Data from library'.**
2. Click on the menu **'Shared Data'** from the top panel, then **'Data Libraries'.**
3. Click on **'GalaxyCam Training'** from the list of shared data libraries.
4. Check the box next to **'loading_data'** and click on top icon **'to History'** to import selected datasets into your history.
5. A green box signaling that your task has been performed successfully will appear at the top right of your screen.
6. Click on **'Analyze Data'** in the menu to return to the main interface. Four files should now be be in your history.
  - 4: UCSC_Human_refGene_chr22_exons
  - 3: TAF1_ChIP
  - 2: illumina_truseq_exome_targeted_regions_hg19_chr22
  - 1: BioMart_Homo_sapiens_genes_GRCh38p3_chr22

Don't delete these files! They will be used in the next section.
