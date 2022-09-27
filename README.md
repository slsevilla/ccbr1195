# CCBR1195
- Project goal: merge several software output into one pipeline

## Conda Environment Workflow
### Add source_conda to bash.rc
```
alias source_conda='. "/data/CCBR_Pipeliner/db/PipeDB/Conda/etc/profile.d/conda.sh"'
```

### Create conda environment
- Conda site: https://docs.conda.io/projects/conda/en/4.6.0/user-guide/tasks/manage-environments.html
```
source_conda
conda create --name {name of conda}
#"Y" to env location of: /data/CCBR_Pipeliner/db/PipeDB/Conda/envs/{name of conda}
```

### Install software
```
mkdir /data/CCBR_Pipeliner/bin/{name of conda}
#Either start download directly from source OR run a git clone from repo
```

### Run Conda
```
module load bowtie/1 R/4.1 # load any biowulf modules
source_conda # run source_conda
conda activate {name of conda}
cd /data/CCBR_Pipeliner/bin/vast-tools/tests/data/Test-100 # for example,  move to data source
vast-tools align Test-100.fq.gz -sp hg38 -c 8 #run tool
```
