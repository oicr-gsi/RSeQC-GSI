.. RSeQC documentation master file, created by
   sphinx-quickstart on Thu Aug  9 21:50:37 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. toctree::
   :maxdepth: 2
   
RSeQC-GSI: An RNA-seq Quality Control Package
=============================================

This is a fork of the original RSeQC package located at: http://rseqc.sourceforge.net/

It implements customizations and bugfixes in use at `OICR-GSI <https://labs.oicr.on.ca/genome-sequence-informatics>`_.

RSeQC package provides a number of useful modules that can comprehensively evaluate high
throughput sequence data especially RNA-seq data. Some basic modules quickly inspect sequence
quality, nucleotide composition bias, PCR bias and GC bias, while RNA-seq specific modules
evaluate sequencing saturation, mapped reads distribution, coverage uniformity, strand specificity, transcript level RNA integrity etc.

Release history
===================

**RSeQC-GSI v3.0.5**

* Updated setup.py to correct release version
* Added full text of GPLv3 license in LICENSE file
* Split README into multiple files
  
**RSeQC-GSI v3.0.4**

* Bugfix; ensure boxplot input is non-empty in read_quality.py

**RSeQC-GSI v3.0.3**

* Bugfix for divide-by-zero error in geneBody_coverage.py

**RSeQC-GSI v3.0.2**

* Updated setup.py

**RSeQC-GSI v3.0.1**

* Fork repository to GSI Github
* Fix bug in calculation of NVC; count nucleotides separately for read1 and read2
* Change default reduce_fold parameter in read_quality.py from 1 to 1000

**RSeQC v3.0.0**

* **Support Python3**. Please use previous versions (v2.6.5 or older) if you are using Python2.
* add `pyBigWig <https://github.com/deeptools/pyBigWig>`_ as a dependency package.

**RSeQC v2.6.4**

* Two dependency packages bx-python and pysam are **not** shipped with RSeQC starting from v2.6.4. 
* Users could install RSeQC using pip: **pip install RSeQC**. bx-python and pysam will be installed automatically if they haven’t been installed before.

**RSeQC v2.6.3**

* Fix a bug in "read_quality.py" that does not return results if input file containing less than 1000 reads.
* Remove "RPKM_count.py" as it generates erroneous results especially for longer reads. Use "FPKM_count.py" instead.
* "bam_stat.py" prints summary statistics to STDOUT. 

**RSeQC v2.6.2**

* fix bugs in "insertion_profile.py", "clipping_profile.py", and "inner_distance.py "

**RSeQC v2.6.1**

* Fix bug in "junction_annotation.py" in that it would report some "novel splice junctions" that don't exist in the BAM files. This happened when reads were clipped and spliced mapped simultaneously. 
* Add FPKM.py. FPKM.py will report "raw fragment count", "FPM" and "FPKM" for each gene. It does not report exon and intron level count. 

**RSeQC v2.6**

Add 3 new modules:

* deletion_profile.py
* insertion_profile.py
* mismatch_profile.py

**RSeQC v2.5**

* read_duplication.py:

 * add '-q' option filter alignments with low mapping quality.
 * Fix bug related to the labels of right Y-aixs
 
* bam2fq: add '-c' option to call 'gzip' command to compress output fastq file(s).
* divide_bam.py: add '-s' option, skipped unmapped reads.
* clipping_profile.py:

 * add '-q' option filter alignments with low mapping quality.
 * Issue warnning and exit if no clipped reads found. 


**RSeQC v2.4**
rewrite "geneBody_coverage.py"

* Memory-efficient: consumed < 100M RAM

* Flexible input to handle one or more BAM files::

 1. Input a singel BAM file. eg: **-i test.bam**
 2. Input several BAM files (separated by ","). eg: **-i test1.bam,test2.bam,test3.bam**
 3. Input plain text file containing the path of BAM file(s). eg: **-i bam_path.txt**
 4. Input a directory containing BAM file(s). eg: **-i my_folder**

* Generate heatmap to visualize gene body coverage over many samples.

**RSeQC v2.3.9**
 
* Add bam2fq.py. Transform BAM files into fastq format.
* bugs fixed. 

**RSeQC v2.3.7**

* bam_stat.py: Now counts 'Proper-paired reads map to different chrom'
* bam2wig.py: automatically call 'wigToBigwig' if it can be found in system $PATH
* inner_distance.py: add 'PE_within_diff_chrom'

**RSeQC v2.3.3**

* Minor bugs fixed. 

**RSeQC v2.3.2**

* Add split_bam.py: Split orignal BAM file into small BAM files based on provided gene list. User can use this module to estimate ribosome RNA amount if the input gene list is ribosomal RNA.
* Add  read_hexamer.py: Calculate hexamer frequency for multiple input files (fasta or fastq).
* Some parts were optimized and runs little faster.

**RSeQC v2.3.1**

* Add normalization option to bam2wig.py. With this option, user can normalize different sequencing depth into the same scale when converting BAM into wiggle format.
* Add another script. geneBody_coverage2.py. This script uses BigWig? instead of BAM as input, and requires much less memory (~ 200M) 


Download
===============================

Download RSeQC
--------------------------------
* `RSeQC (v2.6.4) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.6.4.tar.gz/download>`_ (Note: Downloading "RSeQC-2.6.4.tar.gz" to local computer is unnecessary if you use **pip install RSeQC**)
* `RSeQC (v2.6.3) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.6.3.tar.gz/download>`_
* `RSeQC (v2.6.2) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.6.2.tar.gz/download>`_
* `RSeQC (v2.6.1) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.6.1.tar.gz/download>`_
* `RSeQC (v2.6) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.6.tar.gz/download>`_
* `RSeQC (v2.5) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.5.tar.gz/download>`_
* `RSeQC (v2.4) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.4.tar.gz/download>`_
* `RSeQC (v2.3.9) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.3.9.tar.gz/download>`_
* `RSeQC (v2.3.8) <http://sourceforge.net/projects/rseqc/files/RSeQC-2.3.8.tar.gz/download>`_
* `RSeQC (v2.3.7) <https://sourceforge.net/projects/rseqc/files/RSeQC-2.3.7.tar.gz/download>`_
* `RSeQC (v2.3.6) <http://rseqc.googlecode.com/files/RSeQC-2.3.6.tar.gz>`_
* `RSeQC (v2.3.3) <http://rseqc.googlecode.com/files/RSeQC-2.3.3.tar.gz>`_
* `RSeQC (v2.3.2) <http://rseqc.googlecode.com/files/RSeQC-2.3.2.tar.gz>`_
* `RSeQC (v2.3.1) <http://rseqc.googlecode.com/files/RSeQC-2.3.1.tar.gz>`_

Download test datasets
--------------------------------
 
Pair-end strand specific (Illumina). BAM file md5sum=fbd1fb1c153e3d074524ec70e6e21fb9

* `Pairend_StrandSpecific_51mer_Human_hg19.bam <https://drive.google.com/file/d/0BwAUopGWU_khNmozSHhWdDVncXc/view?usp=sharing>`_
* `Pairend_StrandSpecific_51mer_Human_hg19.bam.bai <https://drive.google.com/file/d/0BwAUopGWU_khc2g4akJlN25KVzQ/view?usp=sharing>`_
 
Pair-end  non-strand specific (Illumina). BAM file md5sum=ba014f6b397b8a29c456b744237a12de

* `Pairend_nonStrandSpecific_36mer_Human_hg19.bam <https://drive.google.com/file/d/0BwAUopGWU_khbjJPX3BxRzNtOWs/view?usp=sharing>`_
* `Pairend_nonStrandSpecific_36mer_Human_hg19.bam.bai <https://drive.google.com/file/d/0BwAUopGWU_khUi02dGc0VjhORlk/view?usp=sharing>`_
  
Single-end strand specific (SOLiD). BAM file md5sum=b39951a6ba4639ca51983c2f0bf5dfce

* `SingleEnd_StrandSpecific_50mer_Human_hg19.bam <https://drive.google.com/file/d/0BwAUopGWU_khUDNTRHhFc29RQms/view?usp=sharing>`_
* `SingleEnd_StrandSpecific_50mer_Human_hg19.bam.bai <https://drive.google.com/file/d/0BwAUopGWU_khSVFLdUhGRjJpS0k/view?usp=sharing>`_
 
Download gene models (update on 08/07/2014)
--------------------------------------------


* `Human (hg38, hg19) <https://sourceforge.net/projects/rseqc/files/BED/Human_Homo_sapiens/>`_
* `Mouse (mm10,mm9) <https://sourceforge.net/projects/rseqc/files/BED/Mouse_Mus_musculus/>`_
* `Fly (dm3) <https://sourceforge.net/projects/rseqc/files/BED/fly_D.melanogaster/>`_
* `Zebrafish (danRer7) <https://sourceforge.net/projects/rseqc/files/BED/Zebrafish_Danio_rerio/>`_

**NOTE:**

* BED file for other species and the most recent release of these files can be downloaded from `UCSC Table Browser <https://genome.ucsc.edu/cgi-bin/hgTables?command=start>`_ 
* Make sure the annotation file and the genome assembly are matched. For example, if you aligned RNA-seq reads to `hg19/GRCh37 <http://www.ncbi.nlm.nih.gov/assembly/2758/>`_ you should download `hg19/GRCh37 <http://www.ncbi.nlm.nih.gov/assembly/2758/>`_ based BED files. 


Download ribosome RNA (update on 07/08/2015)
---------------------------------------------
We only provide rRNA bed files for human and mouse. We download these ribosome RNAs from UCSC table browser,
we provide them here to facilitate users with NO WARRANTY in completeness.

* `GRCh38_rRNA.bed <http://sourceforge.net/projects/rseqc/files/BED/Human_Homo_sapiens/GRCh38_rRNA.bed.gz/download>`_
* `hg19_rRNA.bed <http://sourceforge.net/projects/rseqc/files/BED/Human_Homo_sapiens/hg19_rRNA.bed.gz/download>`_
* `mm10_rRNA.bed <http://sourceforge.net/projects/rseqc/files/BED/Mouse_Mus_musculus/mm10_rRNA.bed.gz/download>`_
* `mm9_rRNA.bed <http://sourceforge.net/projects/rseqc/files/BED/Mouse_Mus_musculus/mm9_rRNA.bed.gz/download>`_


Contact
================================
* Iain Bancarz (RSeQC-GSI fork): ibancarz@oicr.on.ca
* Liguo Wang: wangliguo78@gmail.com
* Shengqin Wang: wzsqwang@gmail.com
* Wei Li: superliwei@gmail.com 

Reference
================================
* Wang, L., Wang, S., & Li, W. (2012). **RSeQC: quality control of RNA-seq experiments**. *Bioinformatics* (Oxford, England), 28(16), 2184–2185. http://doi.org/10.1093/bioinformatics/bts356
* Wang, L., Nie, J., Sicotte, H., Li, Y., Eckel-Passow, J. E., Dasari, S., et al. (2016). **Measure transcript integrity using RNA-seq data**. *BMC Bioinformatics*, 17(1), 1–16. http://doi.org/10.1186/s12859-016-0922-z
