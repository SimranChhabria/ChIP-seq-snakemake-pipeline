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

# Snakemake Workflow

1. Git clone this repository
```
git clone https://github.com/SimranChhabria/ChIP-seq-snakemake-pipeline.git
```

2. Load all the required modules 
```
module load python
module load MACS2
module load snakemake 
module load gbc-bowtie2
module load gbc-cutadapt
module load gbc-fastqc
module load gbc-samtools
```
3. Activate the snakemake environment.
```
conda activate snakemake
```

4. Edit all the config files.

5. Ensure meta-data table contains all of the necessairy fields (TABBED-DELIMITED)

Example:meta-part1

```
#SampleName	SampleFiles
CAL27_EHF_G2_S2_R1_001	CAL27_EHF_G2_S2_R1_001.fastq
```
 Example:meta-part2
 
 ```
 #SampleName	InputFile	SampleFiles	Range
CAL27_EHF_G2_S2_R1_001	CAL_Input.bam	CAL27_EHF_G2_S2_R1_001.bam	--broad
CAL27_EHF_5A5_S1_R1_001	CAL_Input.bam	CAL27_EHF_5A5_S1_R1_001.bam	
```
** NOTE EXACT HEADERS HAVE TO BE ENFORCED or key errors will be thrown during processing**

6. Launch jobs

```
snakemake --latency-wait 120 -pr -j 16 --use-conda -s Snakemake-part1 --cluster "sbatch --partition gbc --cluster faculty --qos gbc --account gbcstaff --mem=24G"
```





