# CASPIAN
A shiny app to visualize and analyse genome coverage data

R 4.1.0 and Rsamtools are required

library(shiny)
library(shinydashboard)
library(ggplot2)
library(DT)
library(Rsamtools)

Create Bin, scan coverage and filter repeated sequences and use bamfile to find breaks in coverage
Use with R studio
Input are fichier tsv generate with bedtools as follows
Needs also a bamfile generated with samtools using the same reference genome used for bedtools
first align on ref genome using minimap2 : minimap2 -ax map-ont refgenome.fa fichier.fq | samtools sort -o  fichier.bam)
index ref genome : samtools faidx
generate bedfile : bedtools genomecov -d -ibam ./fichier.bam > fichier.tsv
