# ChIP-seq Analysis
ChIPseq (pipelines in genomics for Chromatin Immunoprecipitation Sequencing) is an analysis pipeline for preprocessing, alignment and peak calling for ChIP sequencing experiments.The inputs are reads files from the sequencing experiment, and a configuration and meta data file that describes the experiment. 

## Work-flow of the analysis:
-Quality reads using fastqc<br/>
-Trimming of the read using cutadapt tools<br/>
-Mapping the reads to the genome using bowtie2<br/>
-Sorting and indexing using samtools<br/>
-Calling peaks of samples using MACS2<br/>

## Output files generated:
-QC reports<br/>
-Trimmed fastq files<br/>
-Sam files<br/>
-Sorted bam files<br/>
-narrowPeak/ BroadPeak files<br/>

# Setting up the conda environment:
Conda is an open source package management system and environment management system that runs on Windows, macOS and Linux. Conda quickly installs, runs and updates packages and their dependencies. Conda easily creates, saves, loads and switches between environments on your local computer.

## Step 1: Install conda:

```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
chmod u+x Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh

```

Update the conda to the latest version:

```
conda update conda
```

## Step 2: Create a new conda environment and activate it:

```
conda create -n ChIP-seq
conda activate ChIP-seq
```

## Step 3: Install snakemake

```
conda install -c bioconda -c conda-forge snakemake-minimal
```



