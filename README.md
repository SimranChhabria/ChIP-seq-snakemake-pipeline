# ChIP-seq Analysis
ChIPseq (pipelines in genomics for Chromatin Immunoprecipitation Sequencing) is an analysis pipeline for preprocessing, alignment and peak calling for ChIP sequencing experiments.The inputs are reads files from the sequencing experiment, and a configuration and meta data file that describes the experiment. 

# Work-flow of the analysis:
-Quality reads using fastqc<br/>
-Trimming of the read using cutadapt tools<br/>
-Mapping the reads to the genome using bowtie2<br/>
-Sorting and indexing using samtools<br/>
-Calling peaks of samples using MACS2<br/>

# Output files generated:
-QC reports<br/>
-Trimmed fastq files<br/>
-Sam files<br/>
-Sorted bam files<br/>
-narrowPeak/ BroadPeak files<br/>
