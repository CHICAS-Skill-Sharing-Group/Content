# Using the HEC
The HEC can be accessed through your terminal (Mac users) using the bash coding language. 

Two great resources created by Barry are [this](https://b-rowlingson.gitlab.io/hec-template/) and template files and folders are [here](https://gitlab.com/b-rowlingson/hec-template/-/tree/master).

## Useful commands in bash
### Navigating
```pwd``` - the directory path you are currently in \
```ls``` - view a list of files and folders are in this directory\
```cd``` - return to the uppermost directory level\
```cd -``` - navigate up one directory level\
```cd foldername``` - go to this folder in your current directory\

### Interacting with the HEC
Connecting to the HEC\
```ssh -X your_lancaster_username@wayland.hec.lancaster.ac.uk```

Putting files onto the HEC (upload 'hecfolder' onto your storage space on the HEC)\
```rsync --progress --partial -avz /Users/JoeBloggs/Documents/hecfolder username@wayland.hec.lancs.ac.uk:/home/hpc/41/username/```

Downloading files from the HEC (download 'hecfolder' into 'foldername' on your computer)\
```rsync --progress --partial -avz username@wayland.hec.lancs.ac.uk:/home/hpc/41/username/hecfolder /Users/JoeBloggs/Documents/foldername```

*Please see the section below about adding a Symlink - once you have done this you will want to change your filepath for file storage to the 'storage' or 'scratch' folders for intensive jobs that require more than 10GB of storage.*

Close connection with the HEC\
```exit``` 

### Deleting files or folders
```rm -r filename``` 

### Submitting jobs
Submit a single job with job id 'taskname'\
```qsub -N taskname 001-Rcode.txt```

Submit a task array of 10 tasks with job id 'taskname'\
```qsub -t 1-10 -N taskname 001-Rcode.txt```

```qstat``` - status of submitted jobs\
```qdel jobID``` - delete job with id = jobID\
```qdel jobID.1:5``` - delete tasks 1-5 for job with id = jobID\
```gpfsquota``` - check the amount of memory you have used/have available on the HEC

### Install a missing R package in your HEC session
```module add R/3.6.0``` - specify the R version you are using\
```R``` - load the R shell\
```install.packages(INLA)``` - specify the package you need to install, e.g INLA\
```library(INLA)```

### Sample code for use with the HEC
To run R code on the HEC you need to submit a job file (e.g. 001-Rcode.txt above) which tells the HEC to run your .R file. You also need some code in your .R file which can extract the job/task ID, load data and save results on the HEC.

Examples
- bash code for running a single job (add link) or task array (add link)
- R code for a single job (add link) or task array (add link)

### Add a Symlink to your storage and scratch folders
On the HEC you have three areas you can store data: home (10GB), storage (100GB) and scratch (1000GB, but deletes every 4 weeks). When you log in to the HEC your current directory is the home folder. To be able to easily use the storage and scratch folders you need to create a Symlink to these folders in your home folder. Do this with the following steps:
1. Log into the HEC
2. Enter ```pwd``` to see your current pathname and make a note of the number (XX) in /home/hpc/XX/username
3. Enter ```ln -s /storage/hpc/XX/username storage``` with ```XX``` replaced by the number identified in the previous step and ```username``` replaced by your HEC log-in username.
4. Enter ```ln -s /scratch/hpc/XX/username scratch``` with ```XX``` replaced by the number identified in the previous step and ```username``` replaced by your HEC log-in username.
5. You can now access these folders like any normal folder via your home directory.
