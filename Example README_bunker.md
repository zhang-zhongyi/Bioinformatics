###Lab 2 - MSBI 32400
####Brian Bunker
####January 18, 2019

This lab has several topics:

- working with markdown and setting up a project
- NCBI command line tools
- investiging SNP for sickle cell disease

###Working with markdown and setting up a project.

In the project directory lab_2, I set up the directories: `data`, `results`, `src`, `bin` and `doc`.

Note: for sharing, I set up the project directory in:

    /media/sfDesktop/bmi/MSBI_32400/lab_2


###NCBI command line tools

From https://dataguide/nlm/nih.gov:

"EDirect is a software package, developed by NCBI, which allows you to use the E-utilities API in a Unix environment. It helps you quickly and easily use the E-utilities API, and has built-in tools to extract specific data from XML files and create tables of data that can be more easily analyzed or visualized."

Use this command to set up `edirect`:

    wget http://ftp.ncbi.nlm.nih.gov/entrez/entrezdirect/edirect.zip && unzip -u -q edirect.zip && export PATH=$PATH:$HOME/edirect && ./edirect/setup.sh

These commands execute searches. When run from the lab_2 directory, they publish the query results to the results directory. (Note that in the lab Dr. Helseth published them to the `doc` directory, but `results` seems more correct.)

    esearch -db pubmed -query "helseth dl AND collagen" | efetch -format pubmed > results/example1.txt

    esearch -db pubmed -query "bioinformatics [MAJR] AND software [TIAB]" | efetch -format xml | xtract -pattern PubmedArticle -block Author -sep " " -tab "\n" -element LastName,Initials | sort-uniq-count-rank > results/bioinformatics_authors.txt

    esearch -db protein -query 'NP_000509.1' | efetch -format fasta > results/hbb.fasta

###Sickle Cell Investigations

The final part of the lab was to investiget the SNP rs334, which is responsible for sickle cell disease. We used a number of source to obtain information about rs334. First, we examine the mutation, from Wikipedia:


![](https://www.dropbox.com/s/imenu2szqowh09t/Screen%20Shot%20Sickle%20Cell%20Mutation.png?dl=1)

The normal variant for the exon is 'CTC' (producing GLU or glutamic acid) and the pathogenic variant is 'CAC' (producing VAL or valine).

We used three genomes from the 1000 Genomes Project to investigate further. The alignments are known as the YRI Trio because it consists of two parents and one daughter. Displayed below is a screenshot from the 1000 Genomes Project indicating the relationship:

    N19238 - mother
    N19239 - father
    N19240 - daughter

![](https://www.dropbox.com/s/j1ghlom6fthyyx4/Screenshot%201000%20genomes%20YRI%20Trio.png?dl=1)

We loaded the alignments into IGV along with annotations from dbSNP. A screenshot of IGV shows the SNP at location CH11:5248232. 

dbSNP lists the location as CH11:5227002, probably because this location is relative to a different reference genome.

IGV view

![](https://www.dropbox.com/s/i8ue53hh5i22q0g/Screenshot_IGV_view.png?dl=1)

Although the screenshot doesn't show it, the location of the SNP is in location E7 (Exon 7) in the HBB gene.

From IGV, we see the following

    N19238 (mother) is homozygous normal (T)
    N19239 (father) is heterozygous for pathogenic variant (A)
    N19240 (daughter) is heterozygous for pathogenic variant (A)

The lab asks for other rsID's associated with the same position. Refer to the NCBI dbSNP view:

![](https://www.dropbox.com/s/2ypgf4pr8cwerv3/Screenshot_NCBI_dbSNP_view.png?dl=1)

We can see that at the same position there are variations:

    rs193922552 (AT/TC)
    rs63749819 (this is a deletion at the same location (T/-))


