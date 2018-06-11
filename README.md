# Phylogeny workflows

Create env (once)

    conda env create -f /path/to/envs/environment.yaml

Activate env (always)

    source activate ftools

Run pipeline

    snakemake crassphage.tree -s Snakefile --configfile config.yaml --restart-times 1 --profile scg -j 999 --rerun-incomplete --latency-wait 10
