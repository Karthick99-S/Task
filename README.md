# Task
Data Analysis and Statistics and NGS Alignment and Mutation Calling

Here’s an additional section to include in your README.md file for Whole Exome Sequencing (WES) analysis. This part will describe how to perform WES-based analysis and what the results mean.

Whole Exome Sequencing (WES) Analysis for Cancer and Normal TissuesOverview
Whole Exome Sequencing (WES) focuses on sequencing the exonic regions of the genome, providing valuable insights into mutations (e.g., SNVs, indels) associated with diseases like cancer. This analysis compares exonic variations between tumur and normal samples to identify somatic mutations.

**Tools Used**
**FastQC**: Quality control tool for high-throughput sequence data.

**Trimmomatic:** Tool for trimming Illumina sequencing adapters and low-quality sequences.

**BWA-MEM:** Alignment tool to map sequencing reads to a reference genome.
**SAMtools:** Suite of tools for manipulating SAM/BAM files.

**GATK:** Toolkit for variant discovery and genotyping.
**Mutect2:** A GATK tool for somatic mutation calling.

**Annovar:** Tool for annotating variants with biological information.

**Steps for WES Analysis**

**1. Quality Control (FastQC)**
We start by running FastQC to assess the quality of raw sequencing reads. This step helps identify any issues with the data, such as adapter contamination or low-quality sequences.

**2. Read Trimming (Trimmomatic)**
After quality control, Trimmomatic is used to trim low-quality sequences and remove adapter sequences from the raw reads.

**3. Alignment (BWA-MEM)**
Next, BWA-MEM is used to align the trimmed reads to a reference genome (e.g., hg38 for human samples).

**4. SAM/BAM File Conversion and Sorting (SAMtools)**
After alignment, we convert the SAM files to BAM format, sort them, and mark duplicates using SAMtools.

**5. Base Recalibration (GATK)**
Base recalibration is performed to adjust for systematic errors in the sequencing process.

**6. Somatic Mutation Calling (Mutect2)**
We use Mutect2 to call somatic mutations (mutations present in the tumor but not in the normal sample).

**7. Filtering Mutations (GATK)**
We filter out low-confidence mutations and keep the high-confidence somatic mutations.

**8. Variant Annotation (Annovar)**
Finally, we use Annovar to annotate the mutations, providing information such as the gene affected, the mutation type, and clinical relevance.

**Conclusion**:

This workflow enables efficient analysis of WES data to identify somatic mutations associated with cancer and normal tissue comparison. The analysis involves quality control, read trimming, alignment, mutation calling, and annotation, with the ultimate goal of discovering relevant mutations for cancer biomarker identification.
