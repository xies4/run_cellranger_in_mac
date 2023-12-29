# Run cellranger in MAC using docker

## Install docker

First open `About This Mac`, choose `Apple menu ` > `About This Mac`. 
In "Processor" section, you will tell whether you have `Mac with  Intel chip` or ` Mac with Apple silicon`. 

In the "About This Mac" window, look for the "Chip" information. If your Mac has an Apple silicon chip, it will specify the name of the chip (e.g., Apple M1). 

Then follow the instruction below to install docker: 
https://docs.docker.com/desktop/install/mac-install/


The following command line checkes the version of the linux system: 
```
docker run -v $FOLDER:$FOLDER bioconductor/bioconductor_docker lsb_release -a
```

## Download cellranger and reference 

https://www.10xgenomics.com/support/software/cell-ranger/downloads

```
tar zxvf <file_with_suffix_tar.gz>
tar xvf <file_with_suffix_tar>
```

## Download raw dataset

https://www.10xgenomics.com/resources/datasets/5k-human-pbmcs-3-v3-1-chromium-controller-3-1-standard

```
tar xvf SC3pv3_GEX_Human_PBMC_fastqs.tar 
```

## scRNA-seq data
https://cf.10xgenomics.com/samples/cell-exp/7.0.1/SC3pv3_GEX_Human_PBMC/SC3pv3_GEX_Human_PBMC_fastqs.tar  

Replace the folder with your own folder in which has the cellrange folder, refdata folder and raw data folder

```
FOLDER="/Users/xies4/Desktop/opt"
 docker run --workdir $FOLDER -v $FOLDER:$FOLDER bioconductor/bioconductor_docker $FOLDER/cellranger-7.2.0/bin/cellranger count --id Chromium_3p_GEX_Human_PBMC --transcriptome $FOLDER/refdata-gex-GRCh38-2020-A/ --fastqs $FOLDER/Chromium_3p_GEX_Human_PBMC_fastqs/
```
