# ABD
Creates a table for the number of times a nucleotide (A,T,G and C) is present at each position within a specified genomic interval.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

## Usage:
ABD runs on Python 2.7+.

```
python ABD <mapped-fragments.bed file> <genome-sequence.fa> <output-file-prefix> <number-of-cores>

Example run: python ABD Sample1.deduped.bed /home/xyz-user/genomes/hg38.genome.fa Pol-II 20

```
### Parameter description:
```
mapped-fragments.bed file: A mapped fragment bed file can be generated from alignment files in sam
                           format using samtools and bedtools.
genome-sequence.fa:        A fasta format file containing whole genome sequence of an organism.

output-file-prefix:        A prefix for the output file.

number-of-cores:           Total number of cores allocated for this run.

```
### Requirements
Python libraries: joblib, glob
Softwares: bedtools (v2.26.0).

### Output:
A table containing the number of times a nucleotide is present at each genomic position across all intervals.
