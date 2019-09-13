# Salmo_salar_RNA_seq

#### These scripts comprise an analysis pipeline for differential expression, weighted gene co-expression network, and gene ontology overrepresentation analyses of RNA-seq data.

Run order for RNA-seq data:

1. hisat2.sh: Builds HISAT2 index for reference genome and maps reads to reference genome. Outputs SAM file per sample.

2. samtools_example.sh: Sorts SAM files and writes sorted BAM files.

3. stringtie_example.sh: Assembles transcripts for each sample, merges all transcripts from all samples and the reference annotation, and compares assembled sample transcripts to known transcripts. Writes merged GTF file.

4. feature_counts.sh: Generates text file with count matrix for all samples using sorted BAM files and merged GTF file.

5. deseq2.R: Conducts differential gene expression analyses using DESeq2 in R. Requires count matrix generated with featureCounts and CSV file of sample information (i.e., family, treatment, sample name).

6. wgcna.R: Constructs weighted gene co-expression network analysis using normalized counts written from DESeq2.

#### A script is also included for survival analyses using mortality data.

survival_analysis.R: Constructs Kaplan-Meier survival distributions and fits Cox proportional hazards regression model to get hazard ratio values for genetic families.
