# What is knotAnnotSV?
A simple script to create a customizable html file from an AnnotSV output.

The user can customize the order, the number and the comments of the columns thanks to a configuration file (config_cyto.yaml)

Check AnnotSV repo: https://github.com/lgmgeo/AnnotSV

TODO: explain mouseovering / filter / tab (full-split)

# Installation

To download knotAnnotSV, please use git to download the most recent development tree.

Currently, the tree is hosted on github, and can be obtained via:

```bash
$ git clone https://github.com/thomasguignard/knotAnnotSV.git
```

# Requirements 

- Linux OS
- Perl library via cpan : YAML::XS, Sort::Key::Natural


# Input

## AnnotSV output Files


## configuration of output columns

Use a indented yaml file to configure output (use space instead of tab for indentation, tabs are not allowed).

Precise the POSITION field you want to display.

Precise which fields you want to include in COMMENTLIST.

Inactivate fields you don't care with a starting '#' or 'POSITION: 0' or by deleting line.

```bash
---
AnnotSV ID:
    POSITION: 1
    COMMENTLIST:
        - SV length
        - SV type
AnnotSV ranking:
    POSITION: 2
SV chrom:
    POSITION: 0
#SV start:
#    POSITION: 0
```
# Output

An AnnotSV html File is produced to be displayed on web browser (Firefox 81.0, Chrome 86.0.4240.75, Edge 83.0.478.54, IE 11, tested so far). It should be in the same directory as Datatables folder. 

See exemple annotSV.html


# Command line:
```bash
#Basic output
perl knotAnnotSV.pl --annotSVfile example.annotated.tsv --configFile config_cyto.yaml

#Integrate annotSV ranking File
perl knotAnnotSV.pl --annotSVfile example.annotated.tsv --configFile config_cyto.yaml --annotSVranking example.ranking.tsv

#USAGE arguments of knotAnnotSV.pl
perl knotAnnotSV.pl

    --configFile <YAML config file for customizing output>

    --annotSVfile <annotSV annotated file> 

    --annotSVranking <annotSV ranking explanations file>

    --outDir <output directory (default = current dir)> 

    --outPrefix <output file prefix (default = "")> 

    --datatableDir <directory containing datatables files (default = "")>
  
```


--------------------------------------------------------------------------------

**Montpellier Bioinformatique pour le Diagnostic Clinique (MoBiDiC)**

*CHU de Montpellier*

France

![MoBiDiC](https://raw.githubusercontent.com/mobidic/Captain-ACHAB/master/img/logo-mobidic.png)

[Visit our website](https://neuro-2.iurc.montp.inserm.fr/mobidic/)
