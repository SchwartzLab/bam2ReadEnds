# bam2ReadEnds
Compute paired-end coverage—extracting read start and end positions—in transcriptomic (exon) space based on a BED-12 gene annotation. The script converts a paired-end BAM alignment into per-gene exon annotations and count data, then saves the result as an RData file.

### Requirements

- R (≥ 3.5)
- CRAN packages: `optparse`, `magrittr`, `parallel`, `plyr`
- System tools: `samtools`, `bedtools`

### Usage


Rscript bam2ReadEnds.R \
  -i <BAMfile> \
  -g <geneAnnotation.bed> \
  -l <maxInsertLength> \
  -m <minInserts> \
  -n <nCores>

Options

-i	--BAMfile	string	—	Input BAM alignment file
-g	--geneAnnotation	string	—	Gene annotation in BED-12 format
-l	--maxInsLen	integer	200	Maximum insert length (in bp)
-m	--minInsG	integer	15	Minimum number of inserts required to report gene
-n	--nCores	integer	2	Number of CPU cores to use
