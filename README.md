# rsamcounts
The goal of this program is to report read counts for various genomic features (genes, transcripts, exons and junctions) 
and summary QC stats/metrics, in a single pass through a RNA-Seq alignment file (SAM/BAM/CRAM)

Currently, multiple programs and multiple passes through a BAM/CRAM file seem to be in order to generate such count data, 
while this program aims to provide all these data in a single pass. 

## Requirements
The program expects these inputs:
* an alignment file (BAM/CRAM format), sorted by coordinate (`samtools sort`)
* an annotation file (GFF/GTF, a recent Gencode annotation is recommended)
* (optional) the genome fasta file with the genomic sequence for the reference that was used for aligning the reads; this might be needed for some of the program functionality, especially when the input is in CRAM format

## Output
The program outputs multiple tab delimited files (compressed):
 * _outprefix_.gene.tab
 * _outprefix_.exon.tab
 * _outprefix_.tx.tab
 * _outprefix_.jx.tab
 * _outprefix_.qc_stats.tab
 
_outprefix_ is the output file name prefix, default `RSAMC`, which can be provided by the user with `--prefix/-l` option.


