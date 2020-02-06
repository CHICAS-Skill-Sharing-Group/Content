# Using the HEC
The HEC can be accessed through your terminal (Mac users) using the bash coding language.

## Useful commands in bash
### Navigating
```pwd``` - the directory path you are currently in \
```ls``` - view a list of files and folders are in this directory\
```cd``` - return to the uppermost directory level\
```cd foldername``` - go to this folder in your current directory\
```exit``` - close connection with the HEC

### Connecting to the HEC
```ssh -X your_lancaster_username@wayland.hec.lancaster.ac.uk```

Putting files onto the HEC\
```rsync --progress --partial -avz /Users/JoeBloggs/Documents/foldername username@wayland.hec.lancs.ac.uk:/home/hpc/41/username/``` - upload 'foldername' onto your storage space on the HEC

Downloading files from the HEC\
```rsync --progress --partial -avz username@wayland.hec.lancs.ac.uk:/home/hpc/41/username/hecfolder /Users/JoeBloggs/Documents/foldername``` - download 'hecfolder' into 'foldername' on your computer

### Deleting files or folders
```rm -r filename``` 

### Submitting jobs
```qsub -N taskname 001-Rcode.txt``` - submit a single job with job id 'taskname'\
```qsub -t 1-10 -N tasks 001-Rcode.txt``` - submit a task array of 10 tasks with job id 'taskname'

```qstat``` - status of submitted jobs\
```qdel jobID``` - delete job with id = jobID\
```panquota``` - check the amount of memory you have used/have available on the HEC

## Mounting the HEC on your computer
