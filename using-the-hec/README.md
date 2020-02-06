# Using the HEC
The HEC can be accessed through your terminal (Mac users) using the bash coding language.

## Useful commands in bash
### Navigating
```pwd``` - the directory path you are currently in \
```ls``` - view a list of files and folders are in this directory\
```cd``` - return to the uppermost directory level\
```cd foldername``` - go to this folder in your current directory\
```exit``` - close connection with the HEC\

### Connecting to the HEC
```ssh -X your_lancaster_username@wayland.hec.lancaster.ac.uk```

Remote - local (NEED TO DO THIS ON MAX, NOT WAYLAND!)
```rsync --progress --partial -avz eyrem1@wayland.hec.lancs.ac.uk:/home/hpc/41/eyrem1/ /Users/Max/Documents/Lancaster/HEC```
Local - remote
```rsync --progress --partial -avz /Users/Max/Documents/Lancaster/HEC eyrem1@wayland.hec.lancs.ac.uk:/home/hpc/41/eyrem1/```

### Deleting files or folders
```rm -r filename``` 

### Submitting jobs
```qsub -N somename 001-Rcode.com```Submit a single job with job id 'somename'
```qsub -t 1-10 -N tasks 001-runRat.com.txt``` (this is an array - need to ensure saving with task ID - see array.com)

```qstat``` - status of submitted jobs
```qdel jobID``` - delete job with id = jobID
```panquota``` - check the amount of memory you have used/have available on the HEC

## Mounting the HEC on your computer
