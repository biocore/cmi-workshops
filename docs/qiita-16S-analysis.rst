Analysis of Closed Reference Process
------------------------------------

To create an analysis, select "Create new analysis" from the top menu.

This will take you to a list of studies with samples available to you for
analysis, divided between your studies and publicly available studies ("Public Studies").

.. figure::  images/analysis_studies_page2.png
   :align:   center

Find the "CMI workshop analysis" study in Public Studies. You can use the search window at the top right, or filter by tags ("CMIWorkshop" tag).
Click the green plus sign at the left of the row. This will expand the study to expose all
the objects from that study that are available to you for analysis.

.. figure::  images/study_expanded2.png
   :align:   center

You can add each of these objects to the analysis by selecting the “Add” button. We will just add the Closed Reference OTU table object by clicking “Add” in that row.

.. figure::  images/your_study2.png
   :align:   center

Now, the second-right-most icon at the top bar should turn green, indicating that there are samples selected for analysis.

.. figure::  images/clipboard.png
   :align:   center

Clicking on the icon will take you to a page where you can refine the samples you want to include in your analysis. Here, all 30 of our samples are currently included:

.. figure::  images/selected_samples2.png
   :align:   center

You could optionally exclude particular samples from this set by clicking on
"Show/Hide samples", which will show each individual sample name along with a
"remove" option. (Removing them here will mask them from the analysis, but will
not affect the underlying files in any way.)

This should be good for now. Click the "Create Analysis" button, enter a name and
description, then click "Create Analysis".

.. figure::  images/create_analysis_button2.png
   :align:   center

This brings you to the processing network page. Here, pulling down the “Processing Network” tab. This may take 2 to 5 minutes to load. You can analyze data that has been run.

.. figure::  images/processing_network_photo3.png
   :align:   center

Before we process the data, let's have a look at the summary of the contents of the biom file. To create this summary, select the "“dflt_name - BIOM”" artifact and press the generate summary button.

.. figure::  images/generate_summary.png
   :align:   center

Refresh the page until the summary is displayed below. This can take up to 1 minute. You will now see a summary of this file displaying a histogram of the number of features per sample:

.. figure::  images/histogram.png
   :align:   center

As you can see, this file contains 30 samples with between approximately 11,000 and 200,000 features, in our case, picked-OTUs (or operational taxanomic unit).

Now we can begin analyzing these samples. Let’s go ahead and select "dflt_name" then select “Process”. This will take us to the commands selection page. Once there, select “dflt_name - BIOM” so that the commands pull down tab can be accessed which will initially display five actions.

.. figure::  images/command_options2.png
   :align:   center

We will now go through the use of each command which will enable you to generate summaries, plot your data, calculate statistics to help you get the most out of your data.

Rarefying Data
~~~~~~~~~~~~~~

To start, the data must be rarefied. This means that all the samples in the analysis will be randomly subsampled to this number of features, in this case OTUs, reducing potential alpha and beta diversity biases. Samples with fewer than this number of features will be excluded, which can also be useful for excluding things like blanks. To choose a good cutoff for your data, view the histogram that was made when we generated the summary of the data.

.. figure::  images/histogram.png
   :align:   center

An appropriate cutoff would exclude clear outliers, but retain most of the samples. Here we have already removed blanks from our data and eliminated the outliers prior to analysis so we will just use the minimum number of features observed in our samples (11030) as the cutoff.

To rarefy the data, select "Rarefy features" from the dropdown menu. The parameters will appear below the workflow diagram:

.. figure::  images/rarify_parameter_without_number2.png
   :align:   center

Several parameters will have only one option which will be automatically selected for you. In the "p-sampling-depth" field we will specify the number of features to rarefy our samples to. Enter "11030" in this box, and click "Add Command".

.. figure::  images/rarify_parameter_with_sampling_depth.png
   :align:   center

Click the "Run" button above the workflow network to start the process of rarefaction. The view will return to the original screen, while the rarefaction job runs. Then, click on the "dflt_BIOM" artifact to see blue "Jobs using this data" button. Once you click on it, you can see the current status of your job. You can also view it clicking on the server button in the top-right corner of the screen:

.. figure::  images/server.png
   :align:   center

Once the job is completed, you must refresh your browser window to see the result:

.. figure::  images/rarify_workflow2.png
   :align:   center

Select the newly generated "Rarefied table (BIOM)" artifact. Click "Generate Summary" again. This time instead of seeing a histogram of the rarefied samples, you instead see a brief summary confirming that your samples have all be rarefied to the same depth. Now that the data is rarefied, we can begin the analysis.

Taxa Bar Plots
~~~~~~~~~~~~~~

When creating a 16S closed reference BIOM table in Qiita, each sequence is matched to the Green Genes database using a 97% sequence identity threshold, and assigned a taxonomy (See this section for a `refresher on 16S data <http://cmi-workshop.readthedocs.io/en/latest/qiita-16S-processing.html>`__). This enables us to display this data to view the percentage of each taxa within each sample.

When using "Deblurred" data, there is no taxa assignment since features are kept as individual error-corrected sequences, so if you are referencing this tutorial with your own deblurred data you can skip to the next section "Alpha Diversity Analysis".

To display the taxonomic profiles of our samples, we will select our rarefied data artifact, and click "Process". The same processing view we saw previously now appears, so click on "Summarize taxa" from the dropdown menu to arrive at the following view:

.. figure::  images/taxa_barplot_parameter2.png
   :align:   center

All of the parameters for this command are fixed so simply click "Add Comand" to continue. Once the command is added the workflow will appear:

.. figure::  images/taxa_barplot_run2.png
   :align:   center

Click the run button to start the process. The view will return to the original screen, while the taxa barplot generation job runs. Refresh your browser every 10-20 seconds until the "Taxa summaries visualization (q2_visualization)" object biom table appears:

.. figure::  images/taxa_barplot_workflow2.png
   :align:   center

Once the q2 visualization artifact is chosen in the network, the taxa barplot will appear below. The taxa plots offers visualization of the makeup of each sample. Each color will represent a different taxa and each column a different sample. It will have 4 pull-down menus: "Taxonomic Level," "Color Palette," and 2 "Sort Samples By" options.

.. figure::  images/taxa_barplot.png
   :align:   center

The "Taxonomic Level" menu allows you to view the taxa within your samples at different specificities. There are 7 level options: 1- Kingdom, 2- Phylum, 3- Class, 4- Order, 5- Genus, 6- Species, 7- Subspecies.

The "Color Palette" menu allows you to change the coloring of your taxa barplot. You can select through “Discrete” palettes in which each taxa is a different color or “Continuous” palettes in which each taxa is a different shade of one color.

The "Sort Sample By" menus allow you to sort your data either by sample metadata or taxonomic abundance and either by ascending or descending order.

Alpha Diversity Analysis
~~~~~~~~~~~~~~~~~~~~~~~~

Now, let's analyze the alpha diversity of your samples. Alpha diversity metrics describe the diversity of features within a sample or a group of samples. This is used to analyze the diversity within rather than between samples or a group of samples.

Observed Operational Taxonomic Units
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

One type of analysis for alpha diversity is looking at observed OTUs. This type of analysis will provide the number of unique OTUs found in a sample or group of samples.

To perform an observed OTU alpha diversity analysis, select the rarefied "Rarefied table (BIOM)" artifact in the processing network and select "Process". Select "Calculate alpha diversity" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/observed_OTU_parameter2.png
   :align:   center

Several parameters have been automatically selected for you since these options cannot be changed. In the "Diversty metric" field we will specify the alpha diversity analysis to run. Select "Number of distinct features" from the drop-down menu in this box, and click "Add Command".

Once the command is added the workflow should appear as follows:

.. figure::  images/observed_OTU_workflow2.png
   :align:   center

Click the run button to start the process of the alpha diversity analysis. The view will return to the original screen, while the alpha diversity analysis job runs.

Shannon Diversity Index
^^^^^^^^^^^^^^^^^^^^^^^

Another type of alpha diversity analysis is the Shannon diversity index. This analyzes the amount of taxa per the total amount of taxa. It takes into account both diversity as well as abundance.

To perform an Shannon diversity index, select the rarefied "Rarefied table (BIOM)" artifact in the processing network and select "Process". Select "Calculate alpha diversity" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/shannon_diversity_parameter2.png
   :align:   center

Several parameters have been automatically selected for you. In the "Diversty metric" field select "Shannon's index" from the drop-down menu in this box, and click "Add Command".

Once the command is added the workflow should appear as follows:

.. figure::  images/shannon_diversity_workflow2.png
   :align:   center

Click the run button to start the process of the alpha diversity analysis. The view will return to the original screen, while the alpha diversity analysis job runs.

Faith's Phylogenetic Diversity Index
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The final alpha diversity analysis is Faith’s phylogenetic diversity index. This index also measured abundance and diversity but displays it in tree form rather than in a plot.

To perform a Faith's phylogenetic diversity index, select the rarefied "Rarefied table (BIOM)" artifact in the processing network and select "Process". Select "Calculate alpha diversity" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/faith_pd_parameter2.png
   :align:   center

Several parameters have been automatically selected for you. In the "Diversity metric" field select "Faith's phylogenetic diversity" from the drop-down menu in this box and in the "Phylogenetic tree" field select "/databases/gg/13_8/trees/97_otus_no_none.tree" then click "Add Command".

Once the command is added the workflow should appear as follows:

.. figure::  images/faith_pd_workflow2.png
   :align:   center

Click the run button to start the process of the alpha diversity analysis. The view will return to the original screen, while the alpha diversity analysis job runs.

Alpha Diversity Outputs
^^^^^^^^^^^^^^^^^^^^^^^

If you run alpha diversity, you will have an interactive diversity boxplot that shows how different measures of alpha diversity correlate with different metadata categories:

.. figure::  images/alpha_diversity_boxplot.png
   :align:   center

To change the category, choose the "Category" pull-down menu and choose the metadata category you would like to analyze:

.. figure::  images/alpha_diversity_categories.png
   :align:   center

You will also be given the outcomes to Kruskal-Wallis tests:

.. figure::  images/Kruskal_Wallis.png
   :align:   center

Beta Diversity Analysis
~~~~~~~~~~~~~~~~~~~~~~~

Finally, one can measure beta diversity. Beta diversity measures the diversity between samples rather than within. This is used to compare samples to one another.

Bray-Curtis Dissimilarity
^^^^^^^^^^^^^^^^^^^^^^^^^

One way to analyze this is through Bray-Curtis dissimilarity. This quantifies how dissimilar samples are to one another.

To perform a Bray-Curtis beta diversity analysis, select the rarefied "Rarefied table (BIOM)" artifact in the processing network and select "Process". Then select "Calculate beta diversity" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/bray_curtis_beta_diversity2.png
   :align:   center

Several parameters have been automatically selected for you. In the "Distance matrix" field we will specify the beta diversity analysis to run. Enter "Bray-Curtis dissimilarity" in this box, and click "Add Command".

To create a principal coordinates plot of the Bray-Curtis dissimilarity distance matrix, select "Perform Principal Coordinate Analysis (PCoA)" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/bray_curtis_pcoa2.png
   :align:   center

All of the parameter have automatically selected for you just click "Add Command".

Once the command is added the workflow should appear as follows:

.. figure::  images/bray_curtis_workflow2.png
   :align:   center

Click the run button to start the process of the beta diversity analysis. The view will return to the original screen, while the beta diversity analysis job runs.

Unweighted UniFrac Analysis
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Another tool for measuring beta diversity is unweighted UniFrac analysis. Unweighted beta diversity analysis is when the types but not quantity of each taxa is taken into consideration when comparing samples to one another. This differs from weighted analysis which takes into consideration both the amount and variety of taxa in a sample.

To perform unweighted UniFrac analysis, select the rarefied "Rarefied table (BIOM)" artifact in the processing network and select "Process". Then select "Calculate beta diversity" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/unweighted_beta_diversity2.png
   :align:   center

Several parameters have been automatically selected for you. In the "Distance matrix" field enter "Unweighted Unifrac" and in the "Phylogenetic tree" field enter "/databases/gg/13_8/trees/97_otus.tree", and click "Add Command".

To create a principal coordinates plot of the unweighted Unifrac distance matrix, select "Perform Principal Coordinate Analysis (PCoA)" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/unweighted_pcoa2.png
   :align:   center

All of the parameters have been automatically selected for you just click "Add Command". Once the command is added the workflow should appear as follows:

.. figure::  images/unweighted_workflow2.png
   :align:   center

Click the run button to start the process of the beta diversity analysis. The view will return to the original screen, while the beta diversity analysis job runs.

Principal Coordinate Analysis
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Clicking on the "pcoa" (Principal Coordinate Analysis) artifact will open an interactive visualization of the similarity among your samples. Generally speaking, the more similar the samples, the closer the are likely to be in the PCoA ordination. The Emperor visualization program offers a very useful way to explore how patterns of similarity in your data associate with different metadata categories.

Once the Emperor visualization program loads, the PCoA result will look like:

.. figure::  images/full_pcoa.png
   :align:   center

You will see tabs including "Color", "Visibility", "Shape", "Axes", and "Scale"

Under "Color" you will notice two pull-down menus:

.. figure::  images/color_tab.png
   :align:   center

Under "Select a Color Category" you can select how the samples will be grouped. Under "Classic QIIME Colors", you can select how each group will be colored.

Under the "Visibility" tab you will notice 1 pull-down menu:

.. figure::  images/visibility_tab.png
   :align:   center

Under "Select a Visibility Category" you can select which group will be displayed on the PCoA plot.

Under the "Shape" tab you will notice 1 pull-down menu:

.. figure::  images/shape_tab.png
   :align:   center

Under "Select a Shape Category" you can alter the shape of each group on the PCoA plot to the following:

.. figure::  images/shape_options.png
   :align:   center

Under the "Axis" tab you will notice 5 pull-down menus:

.. figure::  images/axis_tab.png
   :align:   center

The first 3 pull-down menus located under "Visible" allow you to change the axis that are being displayed.
The "Axis and Labels Color" menu allow you to change the color of your axis and label of the PCoA.
The "Background Color" menu allows you to change the color of the background of the PCoA.
The % Variantion Expanded graph displays how different the most dissimilar samples are by percentage for each axis that can be used.

Under the "Scale" tab you will notice 2 pull-down menus:

.. figure::  images/scale_tab.png
   :align:   center

Under "Select a Scale Category" you can choose the grouping of your samples. Under "Global Scaling" you can change the point size for each group on the PCoA plot.

Let’s take a few minutes now to explore the various features of Emperor. Open a new browser window with the `Emperor tutorial <https://biocore.github.io/emperor/tutorial_index.html#section1>`__ and follow along with your test data.

Beta Diversity Group Significance
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Another way to study the beta diversity is by measuring the beta diversity group significance. Beta diversity group significance measures whether groups of samples are significantly different from one another using a permutation-based statistical test.

To perform a beta group significance analysis, select the rarefied "dflt_name - BIOM" artifact in the processing network and select "Process". Then select the "dflt_name - BIOM" artifact and select "beta_diversity" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/beta_group_significance_beta.png
   :align:   center

Several parameter have automatically selected for you. In the "p-metric" field enter "unweighted Unifrac" and in the "i-tree" field enter "/databases/gg/13_8/trees/97_otus.tree", and click "Add Command".

To create the beta group significance analysis, select "beta_group_significance" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/significance_matrix.png
   :align:   center

All of the parameter have automatically selected for you just click "Add Command". Once the command is added the workflow should appear as follows:

.. figure::  images/beta_group_significance_workflow.png
   :align:   center

Beta Group Significance Output Analysis
"""""""""""""""""""""""""""""""""""""""

Once the q2 visualization artifact is chosen in the network, the beta diversity box plots will appear:

.. figure::  images/beta_significance_boxplot.png
   :align:   center

The `PERMANOVA (Permutational multivariate analysis of variance) <http://onlinelibrary.wiley.com/doi/10.1111/j.1442-9993.2001.01070.pp.x/full>`__ test results will also be displayed:

.. figure::  images/permanova_results.png
   :align:   center

Filtering Data
~~~~~~~~~~~~~~

Using QIITA you can also filter your data. This allows you to filter out samples.

To filter the data, select the rarefied "dflt_name - BIOM" artifact in the processing network and select "Process". Then select the "dflt_name - BIOM" artifact and select "filter_samples" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/filtered_unweighted_filtering2.png
   :align:   center

Several parameters have been automatically selected for you. In the "p-where" field we are filtering out certain samples. In this case we wanted to filter our samples in which :code:`subject = 'Volunteer 3'`, and click "Add Command". **Keep in mind that all fields are case sensitive**.

An example of how you can use filtering in your analysis is explained in the following "Filtered Unweighted UniFrac Analysis" section.

Filtered Unweighted UniFrac Analysis
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

By filtering, you can perform unweighted UniFrac analysis but this time without certain sample.

After filtering your data (shown in the previous "Filtering Data" section), you can perform a beta diversity analysis by selecting "beta_diversity" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/filtered_unweighted_beta.png
   :align:   center

Several parameters have been automatically selected for you. In the "p-metric" field enter "unweighted Unifrac" and in the "i-tree" field enter "/databases/gg/13_8/trees/97_otus.tree", and click "Add Command".

To create a principal coordinates plot of the unweighted Unifrac distance matrix, select "pcoa" from the drop-down menu. The parameters will appear below the workflow diagram:

.. figure::  images/filtered_unweighted_pcoa.png
   :align:   center

All of the parameters have been automatically selected for you just click "Add Command". Once the command is added the workflow should appear as follows:

.. figure::  images/filtered_unweighted_workflow.png
   :align:   center

Click the run button to start the process of the beta diversity analysis. The view will return to the original screen, while the beta diversity analysis job runs.

Altering Workflow Analysis Names
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To alter the name of a result, click the artifact then use the edit button on the processing network page.

.. figure::  images/rename_data_on_workflow.png
   :align:   center

This will cause a window to pop-up where you can input the name you’d like to replace it with.

.. figure::  images/rename_data_popup.png
   :align:   center

Analysis of Deblur Processed Data
---------------------------------

Creating an analysis of your deblurred data is virtually the same as the process for the Closed Reference data, but there are a few quirks.

First, because the deblur process creates two separate BIOM tables, you’ll want to make a note of the specific object ID number for the artifact you want to use. In my case, that’s ID 33331, the deblurred table with "only-16S" reads.

.. figure::  images/Deblur_processing_screen.png
   :align:   center

The specific ID for your table will be unique, so make a note of it, and you can use it to select the correct table for analysis.

Creating a Meta-Analysis
------------------------

One of the most powerful aspects of Qiita is the ability to compare your data with hundreds of thousands of samples from across the planet. Right now, there are almost 130,000 samples publicly available for you to explore:

.. figure::  images/world_map_data.png
   :align:   center

(You can get up-to-date statistics by clicking “Stats” under the “More Info” option on the top bar.)

Creating a meta-analysis is just like creating an analysis, except you choose data objects from multiple studies. Let’s start creating a meta-analysis by adding our Closed Reference OTU table to a new analysis.

Next, we’ll look for some additional data to compare against.

You noticed the "Other Studies" table below "Your Studies" when adding data to the analysis. (Sometimes this takes a while to load - give it a few minutes.) These are publicly available data for you to explore, and each should have processed data suitable for comparison to your own.

There are a couple tools provided to help you find useful public studies.

First, there are a series of “tags” listed at the top of the window:

.. figure::  images/admin_user_photo.png
   :align:   center

There are two types of tags: admin-assigned (yellow), and user-assigned (blue). You can tag your own study with any tag you’d like, to help other users find your data. For some studies, Qiita administrators will apply specific reserved tags to help identify particularly relevant data. The “GOLD” tag, for example, identifies a small set of highly-curated, very well-explored studies. If you click on one of these tags, all studies not associated with that tag will disappear from the tables.

Second, there is a search field that allows you to filter studies in real time. Try typing in the name of a known PI, or a particular study organism – the thousands of publicly available studies will be filtered down to something that is easier to look through.

.. figure::  images/filter_results_for_meta_analysis.png
   :align:   center

Let’s try comparing our data to the “Global Gut” dataset of human microbiomes from the US, Africa, and South America from the study `“Human gut microbiome viewed across age and geography” by Yatsunenko et al <http://www.nature.com/nature/journal/v486/n7402/abs/nature11053.html>`__. We can search for this dataset using the DOI from the paper: 10.1038/nature11053.

.. figure::  images/data_comparison.png
   :align:   center

Add the closed reference OTU table from this study to your analysis. You should now be able to click the green analysis icon in the upper right and see both your own OTU table and the public study OTU table in your analysis staging area:

You can now click “Create Analysis” just as before to begin specifying analysis steps. This time, let’s just do the beta diversity step. Select the Beta Diversity command, enter a rarefaction depth of 11030, and click “Start Processing”.

.. figure::  images/sample_comparisons.png
   :align:   center

Because you’ve now expanded the number of samples in your analysis by more than an order of magnitude, this step will take a little longer to complete. But when it does, you will be able to use Emperor to explore the samples in your test dataset to samples from around the world!

.. figure::  images/pcoa_sample_comparison.png
   :align:   center
