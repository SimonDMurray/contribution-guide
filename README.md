# A guide to through my Organisational contributions

The following lists should help guide you through various repositories I have contributed to during my career. They will be in a chronological order of my work history and then split up based on what these repositories evidence. If you think anything is unclear or have suggestions to improve the layout please raise an issue!

## Cellular Genetics Informatics - Wellcome Sanger

### Nextflow 
The following repositories show the high throughput scRNA-seq pipelines I developed in Nextflow. They were configured to work on Sanger's IBM LSF HPC (using dynamic resourcing) and have a separate branch to be compatible with Seqera Platforms deployment on Sanger's HPC:

* `cellgeni/nf-starsolo` - This pipeline aligns various scRNAseq protocols to a reference genome using the STAR software.
* `cellgeni/nf-demultiplex` - This pipeline demultiplexes pooled scRNAseq data by donor.
* `cellgeni/nf-velocyto` - This pipeline runs RNA velocity anallysis on ScRNAseq data.
* `cellgeni/nf-reprocessing-public-10x` - This pipeline downloads publicly available scRNAseq 10x protocol data and realigns the data using the STAR software.
* `cellgeni/nf-cellbender` - This pipeline removed artefacts from scRNAseq data.

The following Nextflow pipelines I did not develop but made contributions to:
* `cellgeni/cellatac` - I added the episcanpy clustering option.
* `cellgeni/rnaseq` - Allowed environmental variables to properly be seen which had caused pipeline to fail.
* `cellgeni/vsn-pipelines` - I configured the pipeline for Sanger's IBM LSF HPC and wrote scripts to deploy the pipeline: `cellgeni/grnboost2-configuration`. `cellgeni/grnboost2-configuration` also contains scripts for converting between Anndata versions 0.78 and 0.8 which have version incompatability.
* `cellgeni/nf-irods-to-fastq` - I taught the developer how to use Nextflow and wrote the workflow logic which groups CRAM files by samples and then transposes them.
* `cellgeni/nf-scautoqc` - I taught the developer how to use Nextflow and wrote the workflow scaffold for them to develop from. I also wrote the `gather_matrics` and `run_qc` processes as demonstration. I also developed the container this pipeline runs in.

### Containerisation
`cellgeni/dockage` show various containers that I built using Docker. These containers were then converted to singularity to be run on Sanger's IBM LSF HPC as singularity does not require root permissions. **Please note:** All Nextflow pipelines I developed contain Dockerfiles with the containers I built for those pipelines.

### Python Package Publishing
`hemberg-lab/sc3s` shows a Python package written by a post-doc at Sanger. I wrote the GitHub actions that built the Python wheel and published to both PyPI and Conda. I was credited in the acknowledgements section of the [paper](https://www.biorxiv.org/content/10.1101/2021.05.20.445027v1.full). 

### Downstream Analysis
The following repositories show downstream analysis I wrote for various purposes:
* `cellgeni/notebooks` - This repository contains various basic scRNAseq downstream analysis in both Python and R which I developed and updated when major updates to the tools (such as Seurat) came out. The scripts are designed to teach new bioinformaticians how to process scRNAseq data.
* `cellgeni/scRNA.seq.course` - This repository contains teaching materials for the bioinformatics component of a week long introduction to scRNAseq [course](https://coursesandconferences.wellcomeconnectingscience.org/event/single-cell-technologies-and-analysis-20220715/). I updated these materials when major updates of tools came out prior to each teaching of the course. 

### Documentation and Web Development
`cellgeni/docs` contains documentation for various common practices completed by CellGen faculty at Sanger. I had to help develop a website using GitHub pages to store the documentation CellGenIT writes these faculty members. 

### Miscellaneous
* `SCimpleton/simpleSCENIC` - A PhD student was struggling with gene regulatory network analysis so I exported the data from a genie3 vignette before the genie3 analysis (this is a bottleneck step) so that the analysis could utilise the much faster grnboost2 function in Python. I then exported the data back to R so that the PhD student could continue the genie3 vignette. 
* `cellgeni/various_cellrangers` - This repository contains scripts for submitting cellranger alignment scripts to Sanger's IBM LSF cluster. Cellranger has various functions depending on the sequencing protocol used and so multiple scripts have been written to show how to process different data.
* `Teichlab/tracer` - A PhD student developed a tool for TCR sequencing analysis and so I updated the container and the setup script, fixed the repository structure and added examples of how to run the tool so that the repository was more readable.

# Eco-Flow - University College London

### Nextflow 
The following repositories show the high throughput pipelines I developed in Nextflow for ecological analysis as part of the Eco-Flow project. They adhere to nf-core standards, have unit testing implemented with nf-test and are designed to be deployed locally, on HPC or cloud:
* `Eco-Flow/synteny` - This pipeline runs synteny analysis in a pairwise manner on a list of provided species.
* `Eco-Flow/pollen-metabarcoding` - This pipeline runs taxonomy predictions on sequencing data designed for a project on pollen metabarcoding.
* `Eco-Flow/excon` - This pipeline runs expansion and contraction analysis on gene families.

### Nextflow Configuration
* `Eco-Flow/configs` - This repository is inspired by the nf-core configs repository and contains config files developed to allow our collaborators to deploy Nextflow on the HPC configurations at their university.

### Containerisation
* `Eco-Flow/docker-build` - This repository contains Dockerfiles for each image published to Eco-Flow's [quay.io page](https://quay.io/repository/) which are utilised in the Nextflow pipelines.

### Web Development
* `Eco-Flow/Eco-Flow.github.io` - This repository contains the GitHub pages structure and content for the [Eco-Flow Website](https://eco-flow.github.io/).
