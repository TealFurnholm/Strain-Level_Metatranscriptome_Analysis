<h2>The Complete Muscato Metatranscriptome Pipeline</h2>

<h3>Purpose:</h3>
This pipeline was created so scientists could run the complete microbiome RNA-seq analysis in a single simplified process. 
It is designed to input a complete set of raw fastq files and output files for community structure, sample statistics, differentially expresssed genes and functional analysis. Samples are processed in parallel through these steps (each optional):
<h4>trimming -> read cleaning -> ribosomal RNA removal -> gene alignment -> differential analysis</h4>

<h3>Requirements:</h3>
Metatranscriptomics data is very large and requires substantial computing power. Therefore this software was designed to run on a HPC system using batch scripts/job submission. You can contact hpc-support@umich.edu (http://arc-ts.umich.edu/) to get an on-demand Flux partition, and can use Globus (https://www.globus.org) to securely transfer the files to and from your computer. 

<h3>How to Use:</h3>
<h5>1. copy and unzip MUSCATO.zip in your Flux folder</h5>
<h5>2. transfer your fastq files into the folder called FASTQ</h5>
<h5>3. fill in the design.matrix = the sample names and which group they belong (eg. control, disease-only, drug-only, disease+drug)</h5>
<h5>4. fill in the contrast.matrix = each group and how you want them compared (eg. disease+drug vs drug-only)</h5>
<h5>5. open your shell (see http://arc-ts.umich.edu/document/flux-in-10-easy-steps/ for help)</h5>
<h5>6. run the command: perl BOSS.pl      #this allows you to set the Muscato parameters, decide which steps you want to run</h5>
<h5>6. In your shell, run the command: qsub BOSS.pbs   #this submits all samples listed in the design.matrix at the same time</h5>
<h5>7. You can monitor progress by running: qstat -u yourusername</h5>
<h5>8. You will see several emails as the various processes end. They were successful if Exit_status=0</h5>

<h3>Note on usage:</h3>
This is a work in progress. We are working to improve the automation, speed, and flexibility of the pipeline. Currently the pipeline can take nearly a week to complete depending on sample complexity (aka. number of organisms and unique reads) and options you select. We are also transitioning to a faster computing system early in 2018 which will make this pipeline free and should dramatically reduce run times. While all of the pipeline is modifiable, I highly suggest you begin with default settings. If there is something odd you've noticed, or a function we need to add, please email Dr. Furnholm (tealfurn@umich.edu). 


