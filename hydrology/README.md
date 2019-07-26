# Reproducibility note for hydrology project


## 1. Follow the following steps to reproduce the project
### 1.1 Gather files and scripts
- Input files: (1) STORM_data_flooded_streets_2010-2016.csv ; (2) hampt_rd_data.sqlite , download this file from: https://www.hydroshare.org/resource/9e1b23607ac240588ba50d6b5b9a49b5/
- Dockerfile: 
### 1.2 Build and run container
'''
docker build 
'''
'''
docker run
'''

## 2. Description of the workflow
### 2.1 Overview
- sadler_JoH_resource_diagram.png - a figure showing workflow
- there are 2 input files, 3 preprocessing script, and 1 model script
- Other inofrmation from author: Project II.pdf - project information I
- Other information from author: Project-II Cheat Sheet.pdf - project information II

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

 
