My name is Zhongyi Zhang.
    1  java -version
    2  python --version
    3  cat /etc/redhat-release 
    4  clear
    5  ls -ltr Downloads/
    6  unzip Downloads/IGV_2.4.15.zip 
    7  ls -ltr
    8  ls IGV_2.4.15/   REALLY USEFUL! by Troy
    9  cd Desktop/  NICE CODE!
   10  ln -s ../IGV_2.4.15/igv.sh     This one is super awesome!
   11  ls -la This line is very important by Zhongyi Zhang. COOL!
   12  ls -la ../IGV_2.4.15/
   13  ls -la ../IGV_2.4.15/igv.command 
   14  cat ../IGV_2.4.15/igv.command 
   15  exit
   16  ls -s IGV_2.4.15/igv.sh ~/Desktop/
   17  cd Desktop/
   18  ls -s /home/student/IGV_2.4.15/igv.sh 
   19  ls -la
   20  ln -sv /home/student/IGV_2.4.15/igv.sh ~/Desktop/
   21  mkdir bin
   22  ls -ltr
   23  ./igv.command 
   24  bash igv.sh
   25  clear
   26  ls -ltr
   27  ls -sv /home/student/IGV_2.4.15/igv.sh ~/Desktop/
   28  ls -la ~/Desktop/
   29  ls -s /home/student/IGV_2.4.15/igv.sh ~/Desktop/
   30  cd /
   31  ls -ltr
   32  mkdir data
   33  su
   34  cd data
   35  ls -la
   36  clear
   37  git clone https://github.com/vsbuffalo/bds-files
   38  ls -la
   39  cd ~
   40  ls -ltr Downloads/
   41  su -f
   42  su
   43  clear
   44  pwd
   45  samtools index /data/bds-files/chapter-11-alignment/NA12891_CEU_sample.bam
   46  ls -la /data/bds-files/chapter-11-alignment/NA12891_CEU_sample.bam
   47  ls -la /data/bds-files/chapter-11-alignment/NA12891_CEU_sample.bam*
   48  xpdf
   49  su
   50  exit
   51  ping -c3 www.google.com
   52  cd /data
   53  ls -ltr
   54  exit
   55  cd /data
   56  ls -la
   57  su
   58  exit
   59  ls -la /media/sf_Desktop/
   60  exit
   61  ls -ltr /data
   62  ls -ltr /data/ncbi-blast-2.7.1+/
   63  ls -ltr /data/ncbi-blast-2.7.1+/bin
   64  export PATH=$PATH:/data/ncbi-blast-2.7.1+/bin
   65  clear
   66  echo $PATH
   67  clear
   68  createdb oncokb
   69  psql oncokb
   70  cd Downloads/
   71  wget https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
   72  ls -ltr
   73  exit
   74  ls -la /media/sf_Desktop/
   75  clear
   76  ls -ltr Downloads/
   77  ls -ltrh Downloads/
   78  cd /data
   79  unzip -h
   80  unzip -l ~/Downloads/snpEff_v4_3t_core.zip 
   81  unzip ~/Downloads/snpEff_v4_3t_core.zip
   82  cd snpEff/
   83  clear
   84  ls -la
   85  java -jar snpEff.jar
   86  java -jar snpEff.jar -download hg19
   87  ls -la
   88  ls -la data
   89  ls -la data/hg19/
   90  df -h
   91  clear
   92  ls -ltr
   93  ls -ltr examples/
   94  java -Xmx1G -jar snpEff.jar
   95  java -Xmx1G -jar snpEff.jar -canon hg19 examples/test.chr22.vcf
   96  java -Xmx1G -jar snpEff.jar ann -canon hg19 examples/test.chr22.vcf
   97  vi examples/test.chr22.vcf 
   98  java -Xmx1G -jar snpEff.jar
   99  java -Xmx1G -jar SnpSift.jar 
  100  java -Xmx1G -jar snpEff.jar ann -canon -noLog hg19 examples/test.chr22.vcf
  101  java -Xmx2G -jar snpEff.jar ann -canon -noLog hg19 examples/test.chr22.vcf
  102  ls -ltr
  103  rm snpEff_summary.html 
  104  rm snpEff_genes.txt 
  105  ls -ltr
  106  ls -ltr data
  107  clear
  108  cd ..
  109  tar -zxvf ~/Downloads/ncbi-blast-2.7.1+-x64-linux.tar.gz 
  110  ls -la
  111  cd ncbi-blast-2.7.1+/
  112  ls -la
  113  ls -la bin
  114  bin/blastn
  115  cd ..
  116  clear
  117  df -h
  118  ls -lah ~/Downloads/
  119  rm ~/Downloads/*.tar
  120  rm ~/Downloads/*.tar.gz
  121  ls -ltr ~/Downloads/
  122  su
  123  exit
  124  ls -la /root
  125  sudo la -la /root
  126  exit
  127  mysql -u student -p oncokb
  128  ls -ltr Downloads/
  129  ls -ltr Downloads/oncokb_v1.17.sql.zip 
  130  unzip -l Downloads/oncokb_v1.17.sql.zip 
  131  unzip Downloads/oncokb_v1.17.sql.zip 
  132  ls -ltr Downloads
  133  ls -ltr
  134  clear
  135  ls *.sql
  136  mysql -u student -p oncokb < oncokb_v1.17.sql
  137  mysql -u student -p oncokb
  138  exit
  139  ls -la /root
  140  sudo la -la /root
  141  sudo ls -la /root
  142  clear
  143  su
  144  clear
  145  pwd
  146  clear
  147  mysqladmin -u root -p version
  148  mysql -u root -p
  149  mysql -u student -p oncokb
  150  mysql -u root -p
  151  exit
  152  ls -ltr
  153  vi test.md
  154  pandoc -r markdown -w html test.md > test.html
  155  firefox test.html
  156  rm -fR test.*
  157  ls -ltr
  158  rm -fR oncokb_v1.17.sql 
  159  ls -ltr Downloads/
  160  sudo mv Downloads/mysql57-community-release-el7-9.noarch.rpm /root
  161  sudo mv Downloads/snpEff_v4_3t_core.zip /root
  162  sudo mv Downloads/oncokb_v1.17.sql.zip /root
  163  sudo ls -ltr /root
  164  clear
  165  mysql --version
  166  psql --version
  167  sqlite3
  168  exit
  169  passwd
  170  cd /data
  171  clear
  172  ls -ltr
  173  cp -pR /media/sf_Desktop/variantCaller_out.170/ .
  174  ls -ltr
  175  ls -ltr variantCaller_out.170/
  176  ls -ltr variantCaller_out.170/IonXpress_003/
  177  ls -ltra variantCaller_out.170/
  178  rm variantCaller_out.170/.DS_Store 
  179  ls -ltra variantCaller_out.170/
  180  ls -ltra variantCaller_out.170/IonXpress_003/
  181  chmod -x variantCaller_out.170/IonXpress_003/*.*
  182  ls -ltra variantCaller_out.170/IonXpress_003/
  183  exit
  184  df -h
  185  exit
  186  tree myproject/
  187  exit
  188  ls /media/
  189  ls /
  190  ls /media/sf_Desktop
  191  ls /media/sf_Desktop_update_perl.sh
  192  ls /media/sf_Desktop/update_perl.sh
  193  cp /media/sf_Desktop/update_perl.sh .
  194  ls -ltr
  195  vi update_perl.sh
  196  tree myproject/
  197  pandoc -r markdown -w html README
  198  clear
  199  ls data
  200  ls data/
  201  ls mkdir -p /data
  202  cd /data
  203  clear
  204  tree myproject/
  205  cd doc/
  206  clear
  207  tree myproject/
  208  cd /doc
  209  pandoc -r markdown -w html README_zhongyiz.md
  210  tree myproject/
  211  clear
  212  tree myproject/
  213  firefox /home/student/README_install_notes.html
  214  tree myproject/
  215  tree media/sf_Desktop
  216  tree -p/media
  217  tree cp -p /media
  218  clear
  219  echo 'mkdir myproject/doc' >> README_zhongyiz.md
  220  history >> README_larry.md
  221  history >> README_zhongyiz.md
  222  tree myproject/
  223  clear
  224  tree myproject/
  225  echo 'mkdir myproject/doc' >> README_zhongyiz.md
  226  tree myproject/
  227  pandoc -r markdown -w html README_zhongyiz.md
  228  firefox README_zhongyiz.html
  229  tree myproject/
  230  clear
  231  cd /data
  232  mkdir myproject
  233  mkdir myproject/
  234  mkdir myproject/data
  235  clear
  236  mkdir myproject/
  237  mkdir myproject/data
  238  mkdir myproject/doc
  239  mkdir myproject/results
  240  mkdir myproject/src
  241  mkdir myproject/bin
  242  touch myproject/doc/README_zhongyiz.md
  243  tree myproject/
  244  cd /data/myproject/doc
  245  vim README_zhongyiz.md
  246  history >>README_zhongyiz.md
    1  java -version
    2  python --version
    3  cat /etc/redhat-release 
    4  clear
    5  ls -ltr Downloads/
    6  unzip Downloads/IGV_2.4.15.zip 
    7  ls -ltr
    8  ls IGV_2.4.15/
    9  cd Desktop/
   10  ln -s ../IGV_2.4.15/igv.sh
   11  ls -la
   12  ls -la ../IGV_2.4.15/
   13  ls -la ../IGV_2.4.15/igv.command 
   14  cat ../IGV_2.4.15/igv.command 
   15  exit
   16  ls -s IGV_2.4.15/igv.sh ~/Desktop/
   17  cd Desktop/
   18  ls -s /home/student/IGV_2.4.15/igv.sh 
   19  ls -la
   20  ln -sv /home/student/IGV_2.4.15/igv.sh ~/Desktop/
   21  mkdir bin
   22  ls -ltr
   23  ./igv.command 
   24  bash igv.sh
   25  clear
   26  ls -ltr
   27  ls -sv /home/student/IGV_2.4.15/igv.sh ~/Desktop/
   28  ls -la ~/Desktop/
   29  ls -s /home/student/IGV_2.4.15/igv.sh ~/Desktop/
   30  cd /
   31  ls -ltr
   32  mkdir data
   33  su
   34  cd data
   35  ls -la
   36  clear
   37  git clone https://github.com/vsbuffalo/bds-files
   38  ls -la
   39  cd ~
   40  ls -ltr Downloads/
   41  su -f
   42  su
   43  clear
   44  pwd
   45  samtools index /data/bds-files/chapter-11-alignment/NA12891_CEU_sample.bam
   46  ls -la /data/bds-files/chapter-11-alignment/NA12891_CEU_sample.bam
   47  ls -la /data/bds-files/chapter-11-alignment/NA12891_CEU_sample.bam*
   48  xpdf
   49  su
   50  exit
   51  ping -c3 www.google.com
   52  cd /data
   53  ls -ltr
   54  exit
   55  cd /data
   56  ls -la
   57  su
   58  exit
   59  ls -la /media/sf_Desktop/
   60  exit
   61  ls -ltr /data
   62  ls -ltr /data/ncbi-blast-2.7.1+/
   63  ls -ltr /data/ncbi-blast-2.7.1+/bin
   64  export PATH=$PATH:/data/ncbi-blast-2.7.1+/bin
   65  clear
   66  echo $PATH
   67  clear
   68  createdb oncokb
   69  psql oncokb
   70  cd Downloads/
   71  wget https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
   72  ls -ltr
   73  exit
   74  ls -la /media/sf_Desktop/
   75  clear
   76  ls -ltr Downloads/
   77  ls -ltrh Downloads/
   78  cd /data
   79  unzip -h
   80  unzip -l ~/Downloads/snpEff_v4_3t_core.zip 
   81  unzip ~/Downloads/snpEff_v4_3t_core.zip
   82  cd snpEff/
   83  clear
   84  ls -la
   85  java -jar snpEff.jar
   86  java -jar snpEff.jar -download hg19
   87  ls -la
   88  ls -la data
   89  ls -la data/hg19/
   90  df -h
   91  clear
   92  ls -ltr
   93  ls -ltr examples/
   94  java -Xmx1G -jar snpEff.jar
   95  java -Xmx1G -jar snpEff.jar -canon hg19 examples/test.chr22.vcf
   96  java -Xmx1G -jar snpEff.jar ann -canon hg19 examples/test.chr22.vcf
   97  vi examples/test.chr22.vcf 
   98  java -Xmx1G -jar snpEff.jar
   99  java -Xmx1G -jar SnpSift.jar 
  100  java -Xmx1G -jar snpEff.jar ann -canon -noLog hg19 examples/test.chr22.vcf
  101  java -Xmx2G -jar snpEff.jar ann -canon -noLog hg19 examples/test.chr22.vcf
  102  ls -ltr
  103  rm snpEff_summary.html 
  104  rm snpEff_genes.txt 
  105  ls -ltr
  106  ls -ltr data
  107  clear
  108  cd ..
  109  tar -zxvf ~/Downloads/ncbi-blast-2.7.1+-x64-linux.tar.gz 
  110  ls -la
  111  cd ncbi-blast-2.7.1+/
  112  ls -la
  113  ls -la bin
  114  bin/blastn
  115  cd ..
  116  clear
  117  df -h
  118  ls -lah ~/Downloads/
  119  rm ~/Downloads/*.tar
  120  rm ~/Downloads/*.tar.gz
  121  ls -ltr ~/Downloads/
  122  su
  123  exit
  124  ls -la /root
  125  sudo la -la /root
  126  exit
  127  mysql -u student -p oncokb
  128  ls -ltr Downloads/
  129  ls -ltr Downloads/oncokb_v1.17.sql.zip 
  130  unzip -l Downloads/oncokb_v1.17.sql.zip 
  131  unzip Downloads/oncokb_v1.17.sql.zip 
  132  ls -ltr Downloads
  133  ls -ltr
  134  clear
  135  ls *.sql
  136  mysql -u student -p oncokb < oncokb_v1.17.sql
  137  mysql -u student -p oncokb
  138  exit
  139  ls -la /root
  140  sudo la -la /root
  141  sudo ls -la /root
  142  clear
  143  su
  144  clear
  145  pwd
  146  clear
  147  mysqladmin -u root -p version
  148  mysql -u root -p
  149  mysql -u student -p oncokb
  150  mysql -u root -p
  151  exit
  152  ls -ltr
  153  vi test.md
  154  pandoc -r markdown -w html test.md > test.html
  155  firefox test.html
  156  rm -fR test.*
  157  ls -ltr
  158  rm -fR oncokb_v1.17.sql 
  159  ls -ltr Downloads/
  160  sudo mv Downloads/mysql57-community-release-el7-9.noarch.rpm /root
  161  sudo mv Downloads/snpEff_v4_3t_core.zip /root
  162  sudo mv Downloads/oncokb_v1.17.sql.zip /root
  163  sudo ls -ltr /root
  164  clear
  165  mysql --version
  166  psql --version
  167  sqlite3
  168  exit
  169  passwd
  170  cd /data
  171  clear
  172  ls -ltr
  173  cp -pR /media/sf_Desktop/variantCaller_out.170/ .
  174  ls -ltr
  175  ls -ltr variantCaller_out.170/
  176  ls -ltr variantCaller_out.170/IonXpress_003/
  177  ls -ltra variantCaller_out.170/
  178  rm variantCaller_out.170/.DS_Store 
  179  ls -ltra variantCaller_out.170/
  180  ls -ltra variantCaller_out.170/IonXpress_003/
  181  chmod -x variantCaller_out.170/IonXpress_003/*.*
  182  ls -ltra variantCaller_out.170/IonXpress_003/
  183  exit
  184  df -h
  185  exit
  186  tree myproject/
  187  exit
  188  ls /media/
  189  ls /
  190  ls /media/sf_Desktop
  191  ls /media/sf_Desktop_update_perl.sh
  192  ls /media/sf_Desktop/update_perl.sh
  193  cp /media/sf_Desktop/update_perl.sh .
  194  ls -ltr
  195  vi update_perl.sh
  196  tree myproject/
  197  pandoc -r markdown -w html README
  198  clear
  199  ls data
  200  ls data/
  201  ls mkdir -p /data
  202  cd /data
  203  clear
  204  tree myproject/
  205  cd doc/
  206  clear
  207  tree myproject/
  208  cd /doc
  209  pandoc -r markdown -w html README_zhongyiz.md
  210  tree myproject/
  211  clear
  212  tree myproject/
  213  firefox /home/student/README_install_notes.html
  214  tree myproject/
  215  tree media/sf_Desktop
  216  tree -p/media
  217  tree cp -p /media
  218  clear
  219  echo 'mkdir myproject/doc' >> README_zhongyiz.md
  220  history >> README_larry.md
  221  history >> README_zhongyiz.md
  222  tree myproject/
  223  clear
  224  tree myproject/
  225  echo 'mkdir myproject/doc' >> README_zhongyiz.md
  226  tree myproject/
  227  pandoc -r markdown -w html README_zhongyiz.md
  228  firefox README_zhongyiz.html
  229  tree myproject/
  230  clear
  231  cd /data
  232  mkdir myproject
  233  mkdir myproject/
  234  mkdir myproject/data
  235  clear
  236  mkdir myproject/
  237  mkdir myproject/data
  238  mkdir myproject/doc
  239  mkdir myproject/results
  240  mkdir myproject/src
  241  mkdir myproject/bin
  242  touch myproject/doc/README_zhongyiz.md
  243  tree myproject/
  244  cd /data/myproject/doc
  245  vim README_zhongyiz.md
  246  history >>README_zhongyiz.md
  247  vim README_zhongyiz.md
  248  history >> README_zhongyiz.md\
  249 esearch -db pubmed -query "helseth dl AND collagen" | efetch -format pubmed > doc/example1.txt
  250 esearch -db pubmed -query "bioinformatics [MAJR] AND software [TIAB]" | efetch -format xml | xtract -pattern PubmedArticle -block Author -sep " " -tab "\n" -element LastName,Initials | sort-uniq-count-rank > doc/bioinformatics_authors.txt
  251 esearch -db protein -query 'NP_000509.1' | efetch -format fasta > doc/hbb.fasta
  