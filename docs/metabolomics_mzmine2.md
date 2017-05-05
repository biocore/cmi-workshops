# Feature finding with MZmine2

 <b><span style="color:red">Please follow this <a href="http://mzmine.github.io/download.html">(link)</a> to install the software and dependencies</span>.</b>

## Complete workflow view

![complete workflow view](figs/Workflow_mzmine.png)


### **1.** Start mzMine2
![start mzMine](figs/1_Start.png)


### **2.** Click on raw data import in drop down menu and select .mzxml files
![import data](figs/2_import-raw.png)


### **3.** Click on mass detection in drop down menu
![mass detection](figs/3_mass-detection.png)


### **4.** Specify intensity cut-off and mass list
![specify intensity cut-off](figs/4_mass-detection_select-cutoff_preview.png)


### **5.** Build XICs with chromatogram builder
![Build XICs with chromatogram builder](figs/5_Chrom-builder.png)


### **6.** Specify mass list, mass tolerance min. time span and min. hight
![Specify mass list, mass tolerance min. time span and min. hight](figs/6_Chrom-builder_parameters.png)


### **7.** Deconvolute isobaric peaks with chromatogram deconvolution
![Deconvolute isobaric peaks with chromatogram deconvolution](figs/7_deconv.png)


### **8.** Specify algorithm (base line cut-off or local minimum search and parmaters
![Specify algorithm (base line cut-off or local minimum search and parmaters](figs/8_deconv_parameters.png)


### **9.** Perform deisotopization through isotope peak grouper
![Perform deisotopization through isotope peak grouper](figs/9_de-isotope.png)


### **10.** Specify parameters for isotope peak grouping
![Specify parameters for isotope peak grouping](figs/10_de-isotope_parameters.png)


### **11.** Align XICs from different sample to one matrix
![Align XICs from different sample to one matrix](figs/11_aligner.png)


### **12.** Specify join aligner parameters
![Specify join aligner parameters](figs/12_aligner_parameter.png)


### **13.** [optional] Filter aligned feature matrix with peak list row filter
![Filter aligned feature matrix with peak list row filter](figs/13_filter.png)


### **14.** [optional] Depending of your experimental design use n minimum peaks in a row (n should be around the number of replicates or samples you expect to be similar) and 2-3 minimum peaks per isotope pattern
![use n minimum peaks in a row](figs/14_filter_parameter.png)


### **15.** [optional] You gap filling the re-analyses missed peaks and fill gaps in the feature matrix
![You gap filling the re-analyses missed peaks and fill gaps in the feature matrix](figs/15_gap-filling.png)


### **16.** [optional] Depending on experimental design you can normalize your peak intensities to internal standards, TICs or total peak area.
![normalize your peak intensities to internal standards, TICs or total peak area](figs/16_gap-filling_parameters.png)


### **17.** [optional] Specify normalization parameters
![Specify normalization parameters](figs/17_norm.png)


### **18.** Export your matrix as .csv file for down stream data analysis
![Export your matrix as .csv file for down stream data analysis](figs/18_norm_parameters.png)


### **19.** select file name and parameters you want to export
![select file name and parameters you want to export](figs/19_exp.png)

![select file name and parameters you want to export](figs/20_exp_parmeters.png)

**Here is also a video for [MZmine 2 documentation](http://mzmine.github.io/):**

<a href="http://www.youtube.com/watch?feature=player_embedded&v=VS_Zpyl5chQ
" target="_blank"><img src="http://img.youtube.com/vi/VS_Zpyl5chQ/0.jpg"
alt="IMAGE ALT TEXT HERE" width="480" height="360" border="10" /></a>
