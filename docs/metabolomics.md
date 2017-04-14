# Notes on metabolomics

## Metabolomics background
Some most relevant points from your presentations **and/or** links to
your presentations.

## GNPS
[GNPS](https://gnps.ucsd.edu)

## Demo data in Qiita
* How do I load the data?
* How do I process the data?
* What command do I need to use?
* What are some things to pay attention to?
* What results should I expect?

# GNPS Workshop, Generation of Molecular Networks in 15 minutes

Added by Louis Felix Nothias, last edited by Louis Felix Nothias on Oct 30, 2016  (view change)
Labels:
annotation molecular networks gnps tutorial workshop
ili Workshop: link to the template: [feature_table_with_coordinates.csv](https://www.dropbox.com/s/hjxdce59kdr5bfo/Feature_table_with_coordinates_template.csv?dl=0)

co

## Exploring MS/MS data with the GNPS Data Analysis workflow

### Step 1- Create an account

Go to GNPS main page in an other window (http://gnps.ucsd.edu) and create your own account.

### Step 2- Find a MS/MS dataset on MassIVE (Mass spectrometry Interactive Virtual Environment)

**A)** Go to GNPS (http://gnps.ucsd.edu) and access the MassIVE datasets repository.

**B)** Search for the MassIVE datasets named "GNPS Workshop" (or "GNPS_AMG_SeedGrant" for a larger example). Explore its content, and copy the MassIVE ID number.

**Note:** If you want to upload your own data, go to [DorresteinLab youtube chanel](https://www.youtube.com/channel/UCufTdDIUPjfoN604Igv_29g), here is the video:

<a href="http://www.youtube.com/watch?feature=player_embedded&v=ez9z50FTgvg
" target="_blank"><img src="http://img.youtube.com/vi/ez9z50FTgvg/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="480" height="360" border="10" /></a>


### Step 3 - Access to the Data Analysis workflow

Go to back GNPS main page (http://gnps.ucsd.edu) and open the Data Analysis workflow.

### Step 4 - Configure and launch the Data Analysis workflow

**A)** Indicate a Title.

**B)** Clic on Spectrum Files (required).

**C)** Go to the Share Files spreadsheet and import the data of the "GNPS workshop" MassIVE datasets with the Import Data Share (use the MassIVE ID).

**D)** Go back to the Select Input Files spreadsheet.

**E)** Add the files from the datasets peak/TIPS review/Biotin into Spectrum Files G1.

**F)** Add the files from the datasets peak/TIPS review/Tryptamine spectra into Spectrum Files G2.

**G)** Modifiy parameters to meet high-resolution mass spectrometry: Precursor Ion Mass Tolerance (0.02), Fragment Ion Mass Tolerance (0.02), Min Pairs Cos (0.6), Minimum Matched Fragment Ions (2), Minimum cluster size (use 1)

**H)** Validate the selection with Finish Selection button.

**J)** Launch the Data Analysis workflow using the Submit button.

<a href="http://www.youtube.com/watch?feature=player_embedded&v=ujYR0Hugb2M
" target="_blank"><img src="http://img.youtube.com/vi/ujYR0Hugb2M/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="480" height="360" border="10" /></a>



### Step 5 - Visualize the Data Analysis workflow output

**A)** Return to GNPS main page (http://gnps.ucsd.edu) and go to the Jobs page.

**B)** Explore the spectral library annotations by clicking on view All Library Hits.

**C)** Go back to the Status Page.

**D)** Clic on the View Spectral families and visualize the network 1.

**E)** Map on the molecular network, the parent mass, and the LibraryID.

**F)** Visualize a first MS/MS spectrum by left-clicking on one node. Visualize a second MS/MS spectrum by right-clicking on a second node.

**More on Navigating results:**

<a href="http://www.youtube.com/watch?feature=player_embedded&v=Rpa5UZo69E4
" target="_blank"><img src="http://img.youtube.com/vi/Rpa5UZo69E4/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="480" height="360" border="10" /></a>

# Feature finding with MZmine 2

 <b><span style="color:red">Please follow this <a href=" http://mzmine.github.io/download.html">(link)</a> to install the software and dependencies</span>.</b>


## Complete workflow view

<img src="figs/Workflow_mzmine.png" alt="Drawing" style="width: 750px;"/>


### **1.** Start mzMine
<img src="figs/1_Start.png" alt="Drawing" style="width: 750px;"/>


### **2.** Click on raw data import in drop down menu and select .mzxml files
<img src="figs/2_import-raw.png" alt="Drawing" style="width: 750px;"/>


### **3.** Click on mass detection in drop down menu
<img src="figs/3_mass-detection.png" alt="Drawing" style="width: 750px;"/>


### **4.** Specify intensity cutt-off and mass list
<img src="figs/4_mass-detection_select-cutoff_preview.png" alt="Drawing" style="width: 750px;"/>


### **5.** Build XICs with chromatogram builder
<img src="figs/5_Chrom-builder.png" alt="Drawing" style="width: 750px;"/>


### **6.** Specify mass list, mass tolerance min. time span and min. hight
<img src="figs/6_Chrom-builder_parameters.png" alt="Drawing" style="width: 750px;"/>


### **7.** Deconvolute isobaric peaks with chromatogram deconvolution
<img src="figs/7_deconv.png" alt="Drawing" style="width: 750px;"/>


### **8.** Specify algorithm (base line cut-off or local minimum search and parmaters
<img src="figs/8_deconv_parameters.png" alt="Drawing" style="width: 750px;"/>


### **9.** Perform deisotopization through isotope peak grouper
<img src="figs/9_de-isotope.png" alt="Drawing" style="width: 750px;"/>


### **10.** Specify parameters for isotope peak grouping
<img src="figs/10_de-isotope_parameters.png" alt="Drawing" style="width: 750px;"/>


### **11.** Align XICs from different sample to one matrix
<img src="figs/11_aligner.png" alt="Drawing" style="width: 750px;"/>


### **12.** Specify join aligner parameters
<img src="figs/12_aligner_parameter.png" alt="Drawing" style="width: 750px;"/>


### **13.** [optional] Filter aligned feature matrix with peak list row filter
<img src="figs/13_filter.png" alt="Drawing" style="width: 750px;"/>


### **14.** [optional] Depending of your experimental design use n minimum peaks in a row (n should be around the number of replicates or samples you expect to be similar) and 2-3 minimum peaks per isotope pattern
<img src="figs/14_filter_parameter.png" alt="Drawing" style="width: 750px;"/>


### **15.** [optional] You gap filling the re-analyses missed peaks and fill gaps in the feature matrix
<img src="figs/15_gap-filling.png" alt="Drawing" style="width: 750px;"/>


### **16.** [optional] Depending on experimental design you can normalize yoru peak intensities to internal standrads, TICs or total peak aerea.
<img src="figs/16_gap-filling_parameters.png" alt="Drawing" style="width: 750px;"/>


### **17.** [optional Specify normalization parameters
<img src="figs/17_norm.png" alt="Drawing" style="width: 750px;"/>


### **18.** Export your matrix as .csv file for down stream data analysis
<img src="figs/18_norm_parameters.png" alt="Drawing" style="width: 750px;"/>


### **19.** select file name and parameters you want to export
<img src="figs/19_exp.png" alt="Drawing" style="width: 750px;"/>

<img src="figs/20_exp_parmeters.png" alt="Drawing" style="width: 750px;"/>

**Here is also a video for [MZmine 2 documentation](http://mzmine.github.io/):**

<a href="http://www.youtube.com/watch?feature=player_embedded&v=VS_Zpyl5chQ
" target="_blank"><img src="http://img.youtube.com/vi/VS_Zpyl5chQ/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="480" height="360" border="10" /></a>
