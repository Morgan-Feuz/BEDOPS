# BEDOPS Workflows

### Background
[BEDOPS](https://bedops.readthedocs.io/en/latest/index.html) is an open-source command-line toolkit that performs highly efficient and scalable Boolean and other set operations, statistical calculations, archiving, conversion and other management of genomic data. For example tools in the BEDOPS suite include `bam2bed`, `gtf2bed`, `sort-bed`, `bedmap`, `sam2bed`, `wig2bed`, and many others. 

<ins>Citation:</ins>
+ Shane Neph, M. Scott Kuehn, Alex P. Reynolds, et al. BEDOPS: high-performance genomic feature operations. Bioinformatics (2012) 28 (14): 1919-1920. doi: 10.1093/bioinformatics/bts277

-----------------------------------------------------------------------------------------------------------------------

### Linux Installation
1 - For Linux, first download the 64-bit package from the [GitHub BEDOPS Releases](https://github.com/bedops/bedops/releases). <br/>
2 - Next, extract the package to an appropriate location using: 

```
# Extract the package. Replace x, y, and z with the version number of BEDOPS that was downloaded. 
$ tar jxvf bedops_linux_86_64-vs.y.z.tar.bz2
```

<ins>Note:</ins> `tar` command for Linux is short for Tape Archive and is used to create and extract archive, or compressed, files. The options `jxvf` mean create an archive file using the bzip2 compression, extract the archive file, print verbose information for any tar operation on the terminal, and specifies the filename of the archive file, respectively. More information on `tar` for Linux is located [here](https://www.tutorialspoint.com/linux-tar-command). 
<br/>
<br/>

3 - Finally, add symbolic link from BEDOPS location to the bin (if not already in the bin) to make the programs execuatble from anywhere: 
```
$ sudo ln -s path/to/BEDOPS/bin/* /usr/bin/

# check symbolic link
$ bam2bed
```

------------------------------------------------------------------------------------------------------------------------------
### Basic Usage
+ `bam2bed`: The `bam2bed` script parses BAM data from standard input and prints [sorted](https://bedops.readthedocs.io/en/latest/content/reference/file-management/sorting/sort-bed.html#sort-bed) BED to standard output.
```
# Simple example 
$ bam2bed < path/to/file/file.bam > output/file/path/file.bed 
```
<br/>
<br/>

+ `gtf2bed` : The `gtf2bed` script converts 1-based, closed `[start, end]` [Gene Transfer Format v2.2](http://mblab.wustl.edu/GTF22.html) (GTF2.2) to sorted, 0-based, half-open `[start-1, end)` extended BED-formatted data.
```
# Simple example
$ gtf2bed < path/to/file/file.gtf > output/file/path/file.bed

# Take a look at the new bed file
$ cat file.bed | less -S
```





