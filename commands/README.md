# Codes for submission oxdna simulations on agave
- Files required to create in one folder and need to send to /scratch/ddeeksha
- input; Controls the oxdna parameters
- submit.sh; Controls the simulation time, gpu and Agave stuffs
- oxDNA2_sequence_dependent_parameteres.txt;
- input.dat (varies with each structure);
- input.top (varies with each structure)

```bash
ls
cd filename
agave send filename /scratch/ddeeksha
```

### Code required to start oxdna job
*stay in the folder where simulation needs to be performed*

`sbatch submit.sh`


### To check job and to remove unwanted jobs

```bash
myjobs
rm -rf jobid
```

### To download processed files back into computer

```bash
pwd #get the path
agave receive /scratch/ddeeksha/filename/last_conf.dat .
```
### To obtain mean structure and rmsf
oat mean -p 20 -o mean.dat -d rmsf.json trajectory.dat
