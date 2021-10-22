# ABD
Creates a table for the number of times a nucleotide (A,T,G and C) is present at each position within a specified genomic interval.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

## Usage:
ABD runs on Python 2.7+ interpreter installed on your desired operating system of choice such as Windows, Mac or Linux. 

ABD program needs 4 mandatory parameters to run as described below.
```
python ABD /path-to-file/<mapped-fragments.bed> /path-to-file/<genome-sequence.fa> <output-file-prefix> <number-of-cores>

Example run: python ABD /home/xyz-user/mapped/Sample1.deduped.bed /home/xyz-user/genomes/hg38.genome.fa Pol-II 20
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
Python libraries: ``` joblib, and glob. ```

Softwares: ``` bedtools (v2.26.0). ```

Please provide a whole file path to the program arguement.

Please run one mapped-fragments file at a time for all the intervals.

If you have over 10,000 intervals, we recommend using 10 cores or higher for faster result.

If you have 1,000 intervals or less, we recommend using 1 core. 

All intervals should follow the bed format specifications described in https://genome.ucsc.edu/FAQ/FAQformat.html#format1.

Strand must be specified for all intervals. Incase, the strand is unknown please mention "+" in the 6th field of each interval.

Please maintain number of cores should always be lower than the number of intervals queried.

### Output:
A file at /path-to-file/<output-file-prefix>.totalcount containing a table of the number of times a nucleotide is present at each genomic position across all intervals.
