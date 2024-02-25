# Iris Deployment

![Python](https://img.shields.io/badge/python-v3.9.5-blue.svg)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)
[![GitHub issues](https://img.shields.io/github/issues/glickmac/GRAB.svg)](https://github.com/glickmac/GRAB/issues)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)


This application is designed to deploy a random forest algorithm to predict iris subtype based on user slider input using StreamLit. 



<p align="center"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Screenshot.png" width=60%></p>


## Table of Contents
[What is deployment?](#intro)    
[Why is model deployment important?](#importance)    
[Deployment Workflow](#workflow)    
[Quickstart](#quickstart)    
[Building your own StreamLit Deployable Model](#install)       

## <a name="intro"></a>What is deployment?

GRAB is short for Genomic Retrieval and Blast Database Creation. GRAB currently is only able to mine **bacterial** genomic information by taxonomy. GRAB consists of python scripts to mine the NCBI FTP sites for genomes, coding regions, or proteins of interest. 

## <a name="importance"></a>Why is model deployment important?

GRAB automates the retrieval of genomic information to build custom BLAST databases. The current method of finding genomic information is laborious and time intensive and human error may result in missed information. GRAB provides an automated system to overcome current limitations in creating custom databases. 

## <a name="workflow"></a>Deployment Workflow

<p align="center"><img src="https://github.com/glickmac/GRAB/blob/master/images/GRAB.png" width=60%></p>


### Useful References

[BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=Download)

BLAST is a sequence searching algorithm that searches for a query against a database

#### BLAST

[Install Command Line BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=Download)

Make sure to add ncbi-blast to the system environment path

[BLAST Command Line Manual](https://www.ncbi.nlm.nih.gov/books/NBK279690/)

The scripts are split to allow a user to create a BLAST database their own way
 
[BLAST makeblastdb Example](https://www.haktansuren.com/blast-makeblastdb/) 

A helpful post on BLAST command makeblastdb 
   

## <a name="install"></a>Building your own StreamLit Deployable Model

Required software
+ NCBI-BLAST: [download](https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=Download) 
Must be in environmental path
+ Argparse & Pandas: 
```
pip install argparse
pip install pandas
```
[Argparse](https://pypi.python.org/pypi/argparse/) || [Pandas](http://pandas.pydata.org/pandas-docs/stable/install.html)


## [Download GRAB](https://github.com/glickmac/GRAB/raw/master/GRAB.zip)

#### Unzip GRAB and CD into Directory

```
unzip GRAB.zip
cd GRAB
```

#### Other installations (Git)

```
git clone https://github.com/glickmac/GRAB
```

