#Agshin Balayev, 22.09.2020, Day 3 report

## Question 1: Why do we use the terminal in bioinformatics? 
Answer: Command line enables users to store, load and process large-scale metadata files. It also allows us to make modifications and produce \
the summary results from the input files of large size such as in FASTQ and SAM formats. 

 
## Question 2: What is a plain text file? 
Answer: Plain Text File is a type of file composed by bytes mapped directly to ASCII characters: 7-bit character set containing 128 characters (numbers 0-9, \
uppercase and lowercase English alphabet letters, special characters). Plain Text File can't contain any formatting as bold letters and different fonts. 


## Question 3: In bioinformatics, most of the data are stored in plain text files with added syntax/structure (and commonly compressed afterwards). For instance, fasta or fastq files we have discussed \
them today, but also SAM, BED, GTF, VCF and others (to be discussed next week). Why is that? 
Answer: Plain Text Files are portable across different operating systems as Windows, Mac OS, Linux and easily opened by many text-editing softwares as Notepad, TextEdit unlike .doc documents for \
example. Moreover, they are easy to use with no prior general information mandatory to be able to make them. 


## Question 4: How can we list files are in a directory? Please provide the command(s).
Answer: ls -l directory_name


## Question 5: What | and > do in a terminal? 
Answer: "|" stands for piping (i.e. redirects output of first command as the input for the second command). ">" is a sign writing the output of the command into the file named after ">" sign. 

## Question 6: How do we print the last 10 lines of the file named /mnt/test/test.txt? Please provide the command(s).
Answer: tail -10 /mnt/test/test.txt

## Question 7: How do we print the first column of the file named /mnt/test/test.txt whose columns are separatedby tabs? Please provide the command(s).
Answer: awk -v OFS='\t' 'NR==1' /mnt/test/test.txt

## Question 8: How can we print every third line of a text file? Please provide the command(s), and discuss what they do.
Answer: awk 'NR % 3==0' text_file_name

## Question 9: How can we transform FASTQ into FASTA files using standard Unix tools (sed, awk, etc)? Please provide the command(s), and discuss what they do.
awk 'NR % 4==1 {print ">"$1}; NR % 4==2' SP1.fq > SP1.fa # command takes rows whose number divided by 4 produces remainder of 1 and adds ">" sign in front of the first element in that row. Then, rows \
with number producing remainder of 2 when dividing by 4 are appended to the newly created file. 

