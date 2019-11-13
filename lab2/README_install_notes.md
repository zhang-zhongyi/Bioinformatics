###Installing bioinformatics software for Virtual Machine
####November 26, 2017

As ***student***:

- Installed IGV_2.3.98 in /home/student directory, and added a Launcher on /home/student/Desktop pointing to igv.sh
    - Note- This is the last version that supports Java 1.7

As ***root***:

- Installed samtools 1.6   
   - yum install ncurses-devel
   - yum install zlib-devel
   - ./configure
   - make
   - make install
   
- Installed htslib 1.6
   - bunzip2 htslib-1.6.tar.bz2 
   - tar -xvf htslib-1.6.tar 
   - cd htslib-1.6
   - ./configure
   - make
   - make install
   
- Installing bcftools 1.6
   - tar -xvf bcftools-1.6.tar 
   - cd bcftools-1.6
   - less INSTALL (no configure needed)
   - make install
   
- Installing bwa 0.7.17
   - bunzip2 bwa-0.7.17.tar.bz2 
   - tar -xvf bwa-0.7.17.tar 
   - cd bwa-0.7.17
   - less README.md
   - make
   - cp bwa /usr/local/bin

- Installing Pandoc
   - yum -y install epel-release
   - yum install pandoc
   - vi README.md
   - `pandoc -r markdown -w html README.md > README.html`
   - firefox README.html

- Installing R 3.4.2-2
   - yum install R --nogpgcheck (from epel)
  
####Documenting everything

   - history > README_install_notes.md

---

####Installing Bioinformatics Data Skills files

- As ***root***, created /data folder and grant rights to student user

- As ***student***, `cd /data`

- Download all files for each chapter from GitHub:  `git clone https://github.com/vsbuffalo/bds-files.git`

   - Noticed the sample BAM file was missing an index file, so `samtools index bds-files/chapter-11-alignment/NA12891_CEU_sample.bam`

- Opened sample BAM and VCF file in IGV and save as XML file as /home/student/igv_session.xml

   - Launch IGV from Desktop, then Open Session and choose igv_session.xml to view preselected area

---

####Installing custom annotation tools

As ***student***

- Download snpEff_v4_3p_core.zip from https://sourceforge.net/projects/snpeff/ (Current is 4.3t but requires Java 1.8 so install 4.3p)

- Install in /data/snpEff by running `unzip ~/Downloads/snpEff_v4_3p_core.zip`

- Use `java -jar snpEff.jar download hg19` to download RefSeq annotation.

- Install BLAST+ from NCBI via `ftp ftp.ncbi.nlm.nih.gov` and following instructions at https://www.ncbi.nlm.nih.gov/books/NBK52640/#_chapter1_Installation_

   - From /data `tar -zxvf ~/Downloads/ncbi-blast-2.7.1+-x64-linux.tar.gz`

####Installing Python 3.6.3 in /usr/local/bin

As ***root***

- Followed instructions from http://toomuchdata.com/2014/02/16/how-to-install-python-on-centos/

   - wget https://bootstrap.pypa.io/ez_setup.py

- Install as ***student*** in /data/BioPython virtualenv

- Installed ez_setup.py, then installed pip.  Used pip to install biopython, numpy, matplot lib etc. as ***student***:

~~~
biopython (1.70)
cycler (0.10.0)
matplotlib (2.1.0)
numpy (1.11.3)
pip (9.0.1)
pyparsing (2.2.0)
pysam (0.13)
python-dateutil (2.6.1)
pytz (2017.3)
PyVCF (0.6.8)
setuptools (28.8.0)
six (1.11.0)
~~~

---

__Larry Helseth, November 28, 2017__
