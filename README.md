# Phylogeny workflows

## Installation

#### (First time only)
1. Download and install [miniconda3](https://conda.io/miniconda.html):

    For Linux:
    
        wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
        bash Miniconda3-latest-Linux-x86_64.sh

2. Clone the StrainSifter workflow to the directory where you wish to run the pipeline:

        git clone https://github.com/tamburinif/phylogeny_workflows

3. Create the new conda environment:

        cd phylogeny_workflows
        conda env create -f envs/environment.yaml

#### (Every time)
Activate the environment:

    source activate ftools

## Usage

### Input files

* Reference genome assembly in fasta format
* Two or more short read datasets in fastq format (paired- or single-end)

### Config file

You must update the config.yaml file to include the filepaths to your reference genome assembly, a list of samples, and the directory containing the input samples.

### Running phylogeny workflow

Run as follows:

    snakemake ref.tree -s Snakefile --configfile config.yaml --restart-times 1 --profile scg -j 999 --rerun-incomplete --latency-wait 10
 
