# ABD
Creates a table for the number of times a nucleotide (A,T,G and C) is present at each position within a list of genomic intervals of the same size.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

## Usage:
ABD runs on Python 2.7+ interpreter installed on your desired operating system of choice such as Windows, Mac or Linux. 

ABD program needs 4 mandatory parameters to run as described below.

```
python ABD <mapped-fragments.bed> <genome-sequence.fa> <output-file-prefix> <number-of-cores>

Example run: python ABD Sample1.deduped.bed /home/xyz-user/genomes/hg38.genome.fa Pol-II 20
```
### Parameter description:
```
mapped-fragments.bed:      A mapped fragment bed file can be generated from alignment files in sam
                           format using samtools and bedtools. Any bed format file will also work.

genome-sequence.fa:        A fasta format file containing whole genome sequence of an organism.

output-file-prefix:        A prefix for the output file.

number-of-cores:           Total number of cores allocated for this run.
```
### Requirements
Python libraries: joblib, glob

Softwares: bedtools (v2.26.0).

If you have over 10,000 intervals, we recommend using 10 cores or higher for faster result.

If you have 1,000 intervals or less, we recommend using 1 core. 

Please maintain number of cores should always be lower than the number of intervals queried.
### Output:
A table containing the number of times a nucleotide is present at each genomic position across all intervals.
