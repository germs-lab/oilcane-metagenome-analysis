
### All reads and MAGs are origin from JGI
https://img.jgi.doe.gov/cgi-bin/mer/main.cgi?section=MetagenomeBins&page=metagenomeBins&taxon_oid=3300056388&dbtype=bin

### Mapped reads with bowtie to each MAG and sorted the resulting SAM file
bowtie2 -x [metagenome] –interleaved [MAG] -S [metagenome.MAG.sam]
samtools view -bS [SAM FILE] | samtools sort -@ 4 -o [SAM FILE sorted]

### HT-seq estimated read coverage of each ORF
htseq-count -t CDS -i ID -f [sam] [MAG.gff] > [MAG.htseq]



