# Iris Deployment

This application is designed to deploy a random forest algorithm to predict iris subtype based on user slider input using StreamLit. 



<p align="center"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Screenshot.png" width=60%></p>


![Python](https://img.shields.io/badge/python-v2.7%20%2F%20v3.6-blue.svg)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)
[![GitHub issues](https://img.shields.io/github/issues/glickmac/GRAB.svg)](https://github.com/glickmac/GRAB/issues)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)


# GRAB

## Table of Contents
[What is GRAB?](#intro)    
[Why is this important?](#importance)    
[GRAB Workflow](#workflow)    
[Quickstart](#quickstart)    
[Installing GRAB](#install)    
[GRAB Usage](#usage)    
[GRAB Examples with Pictures](#testing_and_validation)    
[Additional Functionality](#additional)    

## <a name="intro"></a>What is GRAB?

GRAB is short for Genomic Retrieval and Blast Database Creation. GRAB currently is only able to mine **bacterial** genomic information by taxonomy. GRAB consists of python scripts to mine the NCBI FTP sites for genomes, coding regions, or proteins of interest. 

## <a name="importance"></a>Why is this important?

GRAB automates the retrieval of genomic information to build custom BLAST databases. The current method of finding genomic information is laborious and time intensive and human error may result in missed information. GRAB provides an automated system to overcome current limitations in creating custom databases. 

## <a name="workflow"></a>GRAB Workflow

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
   

## <a name="install"></a>Installing GRAB

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


## <a name="usage"></a><a name="quickstart"></a>GRAB Usage

GRAB consists of two python scripts. One to pull genomic, coding regions, or proteins from bacteria of choice and another to automatically build a database. 

+ GRAB.py Help: 

```
python GRAB.py -h
```

+ Build.py Help: 

```
python Build.py -h
```

### GRAB.py (Information Retrieval from NCBI)

Either -q or -f is required, however please use only one flag at a time

#### Required arguments :

| Option     | Description                                     |
|------------|-------------------------------------------------|
| **-q** or **-f**   | -q: -query seperated by commas **(no spaces)** or -f: -file with query seperated by new lines  |
| **-l**   | -level: Taxanomic level: options include *phylum, order, class, family, genus, species, or subspecies*  |

#### Optional arguments:

| Option    | Description |
|-----------|-------------|
| **-m**    |-material: Material to download from NCBI FTP: options include *genomic* **(DEFAULT)**, *coding* (DNA Coding regions), *protein* (Proteins)|
| **-o**    |-output: Create a custom output directory for retrieval, GRAB_Output **(DEFAULT)** |


### Build.py (Automated BLAST Database Creation)

Either -o or -f is required, however please use only one flag at a time. The -o option specifies the output name of GRAB.py

#### Required arguments :

| Option     | Description                                     |
|------------|-------------------------------------------------|
| **-o** or  **-f**    | -o: -output of GRAB.py seperated by commas **(no spaces)** or -f: -file with GRAB.py outputs seperated by new lines  |

#### Optional arguments:

| Option    | Description |
|-----------|-------------|
| **-m**    |-material: Material to build database: options include *nucl* (Nucleotide, **DEFAULT**), *prot* (Proteins)|
| **-t**    |-title: Create a custom name for database, GRAB_DB **(DEFAULT)** |


## <a name="testing_and_validation"></a>GRAB Examples with Pictures

GRAB currently operates only in the GRAB directory. The directories from GRAB.py are needed to run Build.py. You can remove the BLAST database (GRAB_DB is the default) created by Build.py and use it as a functional [blast db](https://www.biostars.org/p/88944/) for blastn, blastx, tblastx, blastp. 

### GRAB.py 

#### Query flag
The query flag (**-q**) can take more than one input seperated by commas. Here we search for two subspecies of Mycobacterium abscessus: massiliense and bolletii

```
python GRAB.py -q massiliense,bolletii -l subspecies
```

Output: 
The default output directory is **GRAB_Output** 

<p align="center"><img src="https://github.com/glickmac/GRAB/blob/master/images/Query_taxa.png" width=80%></p>


The directory contains a folder Nucleotides and three text files. Taxonomy names is a good file to check if the retrieval was successful. By without any other flags, the genomes are by default downloaded from the NCBI FTP.

#### File flag
The file flag (**-f**) must contain a text file seperated by new lines. An example of a properly formatted file is given in demo/file_flag_demo.txt. 

```
python GRAB.py -f demo/file_flag_demo.txt -l subspecies
```
Output: 
The default output directory is **GRAB_Output**. This will overwrite the previous directory. The output directory will contain three Mycobacterium Avium Complex Subspecies. 

<img src="https://github.com/glickmac/GRAB/blob/master/images/query_output.png" height="300" width="350">


#### Download Genes / Proteins with Material Flag
The material flag (**-m**) contains three options 
+ genomic (Full Genomes)
+ coding (Gene Sequences)
+ protein (Proteins)

```
python GRAB.py -m protein -q massiliense,bolletii -l subspecies
```
Output:
The default output directory is **GRAB_Output** 

Now the output directory contains a folder Proteins and three text files. Using the coding or genomic flag will result in the folder being called Nucleotides. 


<p align="center"><img src="https://github.com/glickmac/GRAB/blob/master/images/Protein_Default.png" width=80%></p>

#### Named Output Directory 
The output flag (**-o**) allows for a user to specify the title of the output directory. **Caution**: if no directory is specified the default is GRAB_Output and that directory will be overwritten each time GRAB.py is run. Any output directory will be overwitten if it exists prior to running GRAB.py. 

```
python GRAB.py -m genomic -q massiliense,bolletii -l subspecies -o Abscessus_subspecies
```

Output:

A new output directory will appear in the folder titled Abscessus_subspecies. Grab.py can be run multiple times to create directories with different organisms or pull from mulitple taxonomic levels. 

<p align="center"><img src="https://github.com/glickmac/GRAB/blob/master/images/protein_named.png" width=80%></p>



### Build.py
Build is a script to build a blast database automatically from multiple runs of GRAB.py. The input to Build.py must be the directory names of GRAB.py. **Be careful to select libraries with the same genetic material**

#### Output flag and File flag
Much like the GRAB.py script, An output flag (**-o**) or a file flag (**-f**) is needed to select all outputs of GRAB.py.

```
python Build.py -o GRAB_Output,Abscessus_subspecies 
```
Output:
The default output directory is **GRAB_Combined** and the default BLAST database name is **GRAB_DB**. The GRAB_DB can now be referenced for BLAST searches with the path /GRAB_DB/GRAB_DB. 

<p align="center"><img src="https://github.com/glickmac/GRAB/blob/master/images/Build_default.png" width=80%></p>

#### Material Flag
The material flag (**-m**) is used to specify the creation of a nucleotide (**DEFAULT**) or protein BLAST database. The flag options are nucl (nucleotide) or prot (protein). The flag is optional and nucleotide is the default if no -m option is used. 


```
python Build.py -m nucl -o GRAB_Output,Abscessus_subspecies 
```

Output:
The output of the above code should be the same as the Output and File flags. The default output directory is **GRAB_Combined** and the default BLAST database name is **GRAB_DB**.

#### Title flag
The title flag (**-t**) allows the user to label the newly created BLAST database. 

```
python Build.py -m nucl -o GRAB_Output,Abscessus_subspecies -t NTM_DB
```

Output:
The default output directory is **GRAB_Combined** and the BLAST database name is now defined by the user, in this case **NTM_DB**.

## <a name="additional"></a>Edge Cases

### Edge Cases
There exists edge cases which can affect the retrieval in taxonomic querying in GRAB.py. For example, at the species level if the search term Abscessus is used to find Mycobacterial Abscessus species, other bacteria with the term Abscessus will be present in the retreival. To counter, a user must enter the full search term in the query or file. 

For example:

```
python GRAB.py -m genomic -q 'Mycobacterium abscessus' -l species -o Abscessus_species
```


