# Run cellranger in MAC using docker

## Install docker

https://docs.docker.com/desktop/install/mac-install/

```
docker run -v $FOLDER:$FOLDER bioconductor/bioconductor_docker lsb_release -a
```

## Download cellranger and reference 

https://www.10xgenomics.com/support/software/cell-ranger/downloads

## Download raw dataset

https://www.10xgenomics.com/resources/datasets/5k-human-pbmcs-3-v3-1-chromium-controller-3-1-standard

## scRNA-seq data
https://cf.10xgenomics.com/samples/cell-exp/7.0.1/SC3pv3_GEX_Human_PBMC/SC3pv3_GEX_Human_PBMC_fastqs.tar  

Replace the folder with your own folder in which has the cellrange folder, refdata folder and raw data folder

```
FOLDER="/Users/xies4/Desktop/opt"
docker run -v $FOLDER:$FOLDER bioconductor/bioconductor_docker $FOLDER/cellranger-7.2.0/bin/cellranger
```
