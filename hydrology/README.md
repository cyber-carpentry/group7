# Reproducibility note for hydrology project

## 1. Method -1. Follow the following steps to reproduce the project
### Pull pre-built image form DockerHub
```
docker pull jayadevjoshi12/team_7_hydrology_image
```
### Run the image
```
docker run -it jayadevjoshi12/team_7_hydrology_image
```
### IN THE CONTAINER run snakemake
```
cd /Final_hydro/snakemake
```

## 2. Method -2. Follow the following steps to reproduce the project

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

- After download, put the file into hydrology folder. 
IF YOUR ARE USING VM:
to transfer the file from your local machine to VM, use scp command.
example: in your local machine terminal, run
```
scp hampt_rd_data.sqlite username@to_host:/remote/directory/
```

### Step-3 Build docker image
```
Run Command docker build -t test_image -f Dockerfile.ubuntu_16_py27_py_3_r_3 .
```
### Step-4 Run docker image
```
docker run -it test_image
```
### Step-5 Run snakemake 
NOTE: THIS HAS TO BE IN THE DOCKER IMAGE, which means you see something like this root@af643149d197:/#
Firstly, cd into folder with snakemake
WARNING: If you are running this from you laptop or Desktop before running make sure your docker has sufficient RAM and CPU. If not you can increase the docker's RAM and CPU utilization from go to docker Icon ---> Preferences  ----> increase the Value of RAM and CPU by dragging the pointer. Otherwise snakemake step will be killed/stopped at rule 2 due to low memmory. 
```
" cd /Final_hydro/snakemake
```
Secondly, run snakemake
```
snakemake --use-conda
```


## 3. Description of the workflow
### 3.1 Overview
- sadler_JoH_resource_diagram.png - a figure showing workflow
- there are 2 input files, 3 preprocessing script, and 1 model script
- Other inofrmation from author: Project II.pdf - project information I
- Other information from author: Project-II Cheat Sheet.pdf - project information II

![work_flow](https://github.com/cyber-carpentry/group7_repo/blob/master/hydrology/sadler_JoH_resource_diagram.png)


### 3.2 preprocessing I
- STORM_data_flooded_streets_2010-2016.csv - preprocessing-I data
- prepare_flood_events_table_NEW.py - preprocessing-I script
- flood_events.csv - preprocessing-I output

### 3.3 preprocessing II
- preprocessing-II script is too large to be uploaded to Github, see https://www.hydroshare.org/resource/9e1b23607ac240588ba50d6b5b9a49b5/
- make_dly_obs_table_standalone_NEW.py - preprocessing-II script
- nor_daily_observations_standalone.csv - preprocessing-II output

### 3.4 preprocessing III
- by_event_for_model_NEW.py - preprocessing-III script
- for_model_avgs.csv - preprocessing-III output

### 3.5 major R code
- model_flood_counts_rf_ps_cln_NEW.r - Major R code
- poisson_out_test.csv - output
- poisson_out_train.csv - output
- rf_out_test.csv - output
- rf_out_train.csv - output

### 3.6 Workflow
- the work flow runs the first two preprocessing code seperated and use their outputs to run the third preprocessing code.
- use the third output as input to run the R script to generate results.
- the work flow is containerized.

 ## 4. Factors that affect reproducibility
- Python and R versions
- hard coded paths in the scripts
- lack of reproducibility documentation

 ## 5. Difficulties during the project
 - design of container structure: choose a base image and properly set up environent to get every script working
 - call Python2 script within Python3 environment
 - remove hard coded paths
 
  ## 6. Lessons learned
  - participating Cyber Carpentry workshop is really helpful 
  - have data management plan at the begining the project's life cycle
  - consider reproducibility throughout the project
  - get helps from community 
  - good documentation is important for reproducibility
  
