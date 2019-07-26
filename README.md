# This is a repository for group 7 project

![group7_logo](https://cdn.archonia.us/images/1-63650-1-1-original1/naruto-shippuden-fabric-poster-team-7.jpg)


## 2. Group members
- _Chen_ -MIT
- _Jay_ -Cleveland Clinic
- _An_ -LSU


## 2. Goals by members
- Reproduce paper workflow
- Practice container, singularity, and snakemake
- Machine learning
- Run singularity on cloudv

## 3. Materials
- Sadler et al. 2018 paper preprint - http://faculty.virginia.edu/goodall/Sadler_JHE_2018_Preprint.pdf
- Sadler et al. 2018 paper GitHub repository - https://github.com/uva-hydroinformatics/flood_data
- Sadler et al. 2018 paper Hydroshare repository - https://www.hydroshare.org/resource/9db60cf6c8394a0fa24777c8b9363a9b/
- Other materials https://drive.google.com/drive/folders/1T4bUQztoRkm5S6P6fnpC-a5FttteE-jz

## 4. Deliverables
- dockerfile with all required environment configuration

## 6. Tasks
### 6.1 Hydrology project tasks
**Phases**
- project preparation: read paper, make plan, gather script and data
- try to run each script, including 3 preprocssing scripts, 1 model script
- run multiple scripts pipeline using workflow
- push container to DockerHub
- try singularity

**Detailed tasks**
- [x] done       - [] undone
- [] read the paper
- [] download all raw materials to Github repository
- [] Jetstream VM to test python code (note: need python version 2.7 )

### 6.2 Seismology project tasks

## 7. Tricks
- Move file from local machine to Jetstream 
> scp file.txt username@to_host:/remote/directory/
- Move file from Jetstream to local machine
> scp username@from_host:file.txt /local/directory/

## 8. Factors that affect reproducibility
- Python version
- Script and data documentation

