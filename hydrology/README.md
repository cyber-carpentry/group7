# Reproducibility note for hydrology project


## 1. Follow the following steps to reproduce the project

### Step-1 Download the repository which has the input files, scripts, and Dockerfile
open terminal and cd to your working directory, then run the following command
```
git clone https://github.com/cyber-carpentry/group7_repo.git
```
```
cd group7_repo/
```
```
cd hydrology
```
The repository has two folders. After clone the repo to host, cd into hydrology folder

### Step-2 Download the large input file "hampt_rd_data.sqlite"
- Download the file from 
https://www.hydroshare.org/resource/9e1b23607ac240588ba50d6b5b9a49b5/

- After download, put the file into hydrology folder

-IF YOUR ARE USING VM:
to transfer the file from your local machine to VM, use scp command.
example: in your local machine terminal, run
```
scp hampt_rd_data.sqlite username@to_host:/remote/directory/
```

### Step-3 Build docker image
```


```
### Step-4 Run docker image
```
docker run -it Test_image
```
### Step-5 Run snakemake 
NOTE: THIS HAS TO BE IN THE DOCKER IMAGE, which means you see something like this root@af643149d197:/#
Firstly, cd into folder with snakemake
```
" cd /Final_hydro/snakemake
```
Secondly, run snakemake
```
snakemake --use-conda
```

## 2. Description of the workflow
### 2.1 Overview
- sadler_JoH_resource_diagram.png - a figure showing workflow
- there are 2 input files, 3 preprocessing script, and 1 model script
- Other inofrmation from author: Project II.pdf - project information I
- Other information from author: Project-II Cheat Sheet.pdf - project information II

![work_flow](https://github.com/cyber-carpentry/group7_repo/blob/master/hydrology/sadler_JoH_resource_diagram.png)


### 2.2 preprocessing I
- STORM_data_flooded_streets_2010-2016.csv - preprocessing-I data
- prepare_flood_events_table_NEW.py - preprocessing-I script
- flood_events.csv - preprocessing-I output

### 2.3 preprocessing II
- preprocessing-II script is too large to be uploaded to Github, see https://www.hydroshare.org/resource/9e1b23607ac240588ba50d6b5b9a49b5/
- make_dly_obs_table_standalone_NEW.py - preprocessing-II script
- nor_daily_observations_standalone.csv - preprocessing-II output

### 2.4 preprocessing III
- by_event_for_model_NEW.py - preprocessing-III script
- for_model_avgs.csv - preprocessing-III output

### 2.5 major R code
- model_flood_counts_rf_ps_cln_NEW.r - Major R code
- poisson_out_test.csv - output
- poisson_out_train.csv - output
- rf_out_test.csv - output
- rf_out_train.csv - output

### 2.6 Workflow
- the work flow runs the first two preprocessing code seperated and use their outputs to run the third preprocessing code.
- use the third output as input to run the R script to generate results.
- the work flow is containerized.

 ## 3. Factors that affect reproducibility
- Python and R versions
- hard coded paths in the scripts
- lack of reproducibility documentation

 ## 4. Difficulties during the project
 - design of container structure: choose a base image and properly set up environent to get every script working
 - call Python2 script within Python3 environment
 - remove hard coded paths
