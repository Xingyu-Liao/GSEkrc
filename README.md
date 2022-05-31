Latest Version
==============
Please see the latest version of GSET:https://github.com/Xingyu-Liao/GSEkrc


License
=======

Copyright (C) 2022    Xingyu Liao    ( Xingyu_Liao@126.com / xingyu.liao@kaust.edu.sa )

Computer, Electrical and Mathematical Sciences and Engineering Division,
King Abdullah University of Science and Technology (KAUST),
Thuwal, 23955, Saudi Arabia.


Installation and operation of GSEkrc 
==================================

### Dependencies

When running GSEkrc from GitHub source the following tools are required:

* [Matlab 2012a or above]
 
### Install GSEkrc

GSEkrc is a Matlab function script and therefore will require a machine with Matlab pre-installed.

Start Matlab and copy the file GSE.m to current work directory.

Usage: GSE(infile,L,K,[error])

    infile: the .histo file contain k-mer frequencies, which generated by jellyfish or other tools.
	L: the average length of reads.
    K: the length of a k-mer.
    error: estimation of sequencing error rate, optional, default is 0.005.	

### Example
	
    Step1: generate .histo file from fasta or fastq files.
	    zcat *.fastq.gz | jellyfish count /dev/fd/0 -C -o data_15mer -m 15 -t 8 -s 5G
        jellyfish histo -h 3000000 -o data_15mer.histo data_15mer
	Step2:Start Matlab and keep data_15mer.histo and GSE.m both in the current work directory, and Run
		GSE('data_15mer.histo',101,15);
	