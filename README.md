# rsamcounts
The goal of this program is to report read counts for various genomic features (genes, transcripts, exons and junctions) 
and summary QC stats/metrics, through a single pass through a RNA-Seq alignment file (SAM/BAM/CRAM)

Currently, programs like featureCounts (subRead) and regtools require multiple passes in order to generate such count and QC data, 
while this program aims to provide all these data in a single pass. 

An annotation file (GFF/GTF) must be provided (Gencode annotation is recommended), and the alignment file must be sorted by coordinate (`samtools sort`).

The program outputs multiple tab delimited files (compressed):
 * _outprefix_.gene.tab
 * _outprefix_.exon.tab
 * _outprefix_.tx.tab
 * _outprefix_.jx.tab
 * _outprefix_.qc_stats.tab
 
_outprefix_ is the output file name prefix, default `RSAMC`, which can be provided by the user with `--prefix/-l` option.


