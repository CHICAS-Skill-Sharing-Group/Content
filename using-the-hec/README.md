# Using the HEC
The HEC can be accessed through your terminal (Mac users) using the bash coding language.

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

Close connection with the HEC\
```exit``` 

### Deleting files or folders
```rm -r filename``` 

### Submitting jobs
Submit a single job with job id 'taskname'\
```qsub -N taskname 001-Rcode.txt```

Submit a task array of 10 tasks with job id 'taskname'\
```qsub -t 1-10 -N tasks 001-Rcode.txt```

```qstat``` - status of submitted jobs\
```qdel jobID``` - delete job with id = jobID\
```panquota``` - check the amount of memory you have used/have available on the HEC

## Sample code for use with the HEC
To run R code on the HEC you need to submit a job file (e.g. 001-Rcode.txt above) which tells the HEC to run your .R file. You also need some code in your .R file which can extract the job/task ID.

- bash code for running a job
- R code
