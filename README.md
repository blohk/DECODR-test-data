# DECODR-test-data
These datasets were used in the manuscript, "Deconvolution of Complex DNA Repair (DECODR):  Establishing a novel deconvolution algorithm for comprehensive analysis of CRISPR-edited Sanger sequencing data," by Kevin Bloh, Rohan Kanchana, Pawel Bialk, Kelly Banas, Zugui Zhang, Byung-Chun Yoo and Eric B. Kmiec.

These files contain chromatogram data from a wide variety of gene editing projects performed by various authors of the manuscript, which were all used to generate the manuscript's main and supplemental figures.

Access options and source code queries can be made to geneeditinginstitute@christianacare.org.

# DECODR Usage Instructions

In order to use DECODR, three (3) core inputs are needed prior to analysis: a gRNA sequence, reference sequence and an experimental sequence.  These are detailed below:

-The gRNA sequence is the 5>3' sequence of the guide RNA that was used in the experiment to generate the data to be analyzed.  Up to two (2) guide sequences may be entered.

-The Reference sequence is the unedited or wild-type sequence of the gene target.  The reference sequence can be in either .ab1 or basecall formats (i.e. .txt, .fasta).  Plain text may also be used.

-The Experimental sequence is the DNA sequence that needs to be deconvoluted.

Once all three of these inputs are gathered, DECODR can be used.  The layout of the main page contists of 6 input fields, detailed below:

-Nuclease:  This dropdown box details the Cas protein used in the experiment.  It is necessary to correctly input this information, as choosing an incorrect nuclease will lead to an incorrect cleavage site being identified, which may result in an incorrect analysis.

-Sample type:  This dropdown box details whether the sample being run is a clonal or bulk sample.  If the sample contains the DNA of many different edited cells, choose "bulk," as this will lower the detection threshold and lead to a more complete, accurate analysis.  If the samples being deconvoluted are from lconally-expanded cells, choose "clonal."  If you are unsure, choose "bulk."

-Guide Sequences (Max 2):  Enter in the 5>3' sequence of the guide RNA that was used in the experiment to generate the data to be analyzed.  Up to two (2) guide sequences can be used for analysis.

-Donor Sequence:  If the editing experiment involved a DNA donor fragment that differs from the WT sequence, enter the sequence of the donor sequence here in plain text.  If no donor template was used in the experiment, this field can be left blank.

-Wild Type/Control File:  Enter in your reference sequence here.  The reference sequence can be in either .ab1 or basecall formats (i.e. .txt, .fasta).  The reference sequence may also be entered in plain text by selecting the "text input" option up and to the right of the data box.  Files may be dragged-and-dropped directly into the input field or uploaded by clicking on the input field.

-Comparison/Experiment File(s):  Enter in the sequences to be deconvoluted here.  The experimental sequences may  be in .ab1 format, as well as basecall formats such as .fasta (please note that inputting basecall formats will simply return sequence alignments, not deconvolution).  Multiple experimental sequences can be uploaded simultaneously, in which case they will all be analyzed independently using the same reference sequence and other input parameters.  Files may be dragged-and-dropped directly into the input field or uploaded by clicking on the input field.
*Please note that in the current software version (DECODR v2.9), the number of experimental sequences is limited to 30 in order to mitigate server load.  This limit will be removed in later software versions.

Once all input fields are filled out, click "Analyze Data" to submit.  The analysis tab will update in real-time as the samples are analyzed.  Individual analyses should not take longer than a few seconds, but batch uploading multiple experimental files will increase the time needed to perform all analyses.

Once all data is analyzed, you will be automatically taken to the analysis tab.  If multiple experimental files were batch uploaded, you will see a summary page containing all of your analyses.  Clicking on any of these readouts will take you to a more detailed page for that specific analysis.  If only one experimental file is analysed, you will be taken directly to this more detailed analysis page.  Any experimental sequences that could not be analyzed will be displayed on the top-right of the page, under the "Failed Experimental Files" tab, along with descriptions for why they failed.  Within the analysis tab, you will see a summary of the submitted sequences at the top.  If a donor template is used, you wil be able to visualize the alignment of the donor to the reference sequence by clicking the "View Donor Alignment" button.

On the detailed individual analysis page, you will see a bar graph displaying all of the sequence's inferred indels, plotted by net indel size, along with an R^2 value for the whole analysis.  Beneath this, the individual sequences of the deconvolution will be displayed.  To the left, you will see a description of the indel, the % of the whole sequence the indel contributes, and a p-value indicating the statistical significance of the inferred indel.  To the right, you will see the sequences of each inferred indel.  Above the reference sequence at the top of this list, the gRNA sequences and PAM sequences will be displayed by a green bar and a red bar, respectively.  The cut site/s will be indicated by a pipe (|) within the sequence text.  Inserted bases will be boxed in to visually distinguish them, and deleted bases will show as a dash (-).  Hovering your mouse over an inserted base will populate the inserted base probabilities chart to the right of the bar graph.  This graph will visualize the probabilities that a given base is an A, T, C, or G.

Any errors can be reported using the "Report Errors/Suggestions" button on the top right of the analysis tab.  Data can also be downloaded locally using the "Download Analysis Data" button on the bottom right.
