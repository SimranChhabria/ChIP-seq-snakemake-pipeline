# ChIP-seq Analysis
ChIPseq (pipelines in genomics for Chromatin Immunoprecipitation Sequencing) is an analysis pipeline for preprocessing, alignment and peak calling for ChIP sequencing experiments.The inputs are reads files from the sequencing experiment, and a configuration and meta data file that describes the experiment. 

# Work-flow of the analysis:
-Quality reads using fastqc.
-Trimming of the read using cutadapt tools.
-Mapping the reads to the genome using bowtie2.
-Sorting and indexing using samtools.
-Calling peaks of samples using MACS2.

# Output files generated:
-QC reports
-Trimmed fastq files
-Sam files
-Sorted bam files
-narrowPeak/ BroadPeak files
