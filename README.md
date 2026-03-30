# project_bioinformatic_01
```bash
conda init bash
source ~/.bashrc
```
## Initial Conda Configuration

Run these commands once to set up the necessary channels for bioinformatics tools:
```bash
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
conda config --set channel_priority strict
```
# Step 1: Quality Control (QC) Environment

This environment is used for raw data trimming and quality assessment. Tools: fastp, fastqc

Installation
```bash
conda create -n QC fastp fastqc -y
```
## Verification
Activate the environment and check the versions:
```bash
conda activate QC
fastp --version
fastqc --version
```
```
bash
conda deactivate
```
# Step 2: Genome Assembly
Contains tools for de novo assembly and evaluating the completeness of your results. Tools: Spades, Busco, Quast
## Installation
```bash
conda create -n Assembly spades busco quast -y
```
## Verification
```bash
conda activate Assembly
spades.py --version
busco --version
quast.py --version
```
# Step 3: Functional Annotation (RGI & Virulence)
These tools identify antibiotic resistance and virulence factors. It is recommended to handle their databases carefully.
## Resistance Gene Identifier (RGI)
### Installation
```bash
conda create -n env_rgi rgi -y
```
```bash
conda activate env_rgi
rgi main --version
```
## Prokka (Rapid Prokaryotic Genome Annotation)
### Installation
```bash
conda create -n env_prokka prokka -y
```
### Verification:
```bash
conda activate env_prokka
prokka --version
```
### VirulenceFinder
Installation
```bash
conda create -n env_virulence virulencefinder -y
```
Verification
```bash
conda activate env_virulence
conda list virulencefinder
virulencefinder.py -h
```
## Save
```bash
git add README.md
git commit -m "Complplete installation and storage management guide"
git push origin main
```