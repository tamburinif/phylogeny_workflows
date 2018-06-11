# Phylogeny workflows

## Installation

#### (First time only)
1. Download and install [miniconda3](https://conda.io/miniconda.html):

    For Linux:
    
        wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
        bash Miniconda3-latest-Linux-x86_64.sh

2. Clone workflow to the directory where you wish to run the pipeline:

        git clone https://github.com/tamburinif/phylogeny_workflows

3. Create the new conda environment:

        cd phylogeny_workflows
        conda env create -f envs/environment.yaml

Conda env can be updates as follows:

        conda env update -f envs/environment.yaml

#### (Every time)
Activate the environment:

    source activate ftools

## Usage

### Input files

* Reference genome assembly in fasta format
* Two or more short read datasets in fastq format (paired- or single-end)

### Config file

You must update the config.yaml file to include the filepaths to your reference genome assembly, a list of samples, and the directory containing the input samples.

If your reads are paired-end, params 'reads1' and 'reads2' should point to directories with forward and reverse reads respectively. If working with single-end or interleaved files, point to those in 'reads1' and leave 'reads2' blank.

### Running phylogeny workflow

Run as follows:

    snakemake ref.tree -s Snakefile --configfile config.yaml --restart-times 1 --profile scg -j 999 --rerun-incomplete --latency-wait 10
 
