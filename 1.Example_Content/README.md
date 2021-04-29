# Example content

## Aims
1. Make directories for raw data and FastQC outputs.
2. Download some raw data to a directory.
3. Use the FastQC tool to quality check our raw data.

## Tools required
[FastQC][https://github.com/s-andrews/FastQC]

## 1. Setting up directories

Once you are logged on to NeSI, move into your project directory.
```
cd /nesi/project/PROJECT_ID/
```

Here we want to set up three directories:
1. A project directory that will hold: 
  2. A directory within the project directory for raw data;
  3. A directory within the project directory for our results outputs.

```
# First let's make our project directory that will contain everything.
mkdir fastqc_tutorial

# Now we will move into this project directory before creating our raw data and outputs directories.
cd fastqc_tutorial

mkdir raw_data
mkdir fastqc_outputs
```

Today we will be using yeast genomic data. What would be a more informative name for your project directory?

## 2. Getting the raw data

Now we have our directories established, let's get the raw data.
```
# Change to data directory, and download data from FigShare
cd raw_data
wget -O yeast.fastq https://ndownloader.figshare.com/files/4790242
```

## 3. Quality assessment of fastq data

Now we can check the quality of our raw genomic data.

```
# First let's load the FastQC software module.
module load fastqc

fastqc yeast.fastq > ../fastqc_outputs/
```
