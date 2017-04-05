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

**B)** Search for the MassIVE datasets named "GNPS Workshop". Explore its content, and copy the MassIVE ID number.

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

### Step 5 - Visualize the Data Analysis workflow output

**A)** Return to GNPS main page (http://gnps.ucsd.edu) and go to the Jobs page.

**B)** Explore the spectral library annotations by clicking on view All Library Hits.

**C)** Go back to the Status Page.

**D)** Clic on the View Spectral families and visualize the network 1.

**E)** Map on the molecular network, the parent mass, and the LibraryID.

**F)** Visualize a first MS/MS spectrum by left-clicking on one node. Visualize a second MS/MS spectrum by right-clicking on a second node.
