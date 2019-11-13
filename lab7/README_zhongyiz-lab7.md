##Lab 7##
##My name is Zhongyi Zhang.##




---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

less hgvs_test_cases.vcf

##fileformat=VCFv4.1                                                                    
##FILTER=<ID=PASS,Description="All filters passed">
##fileDate=20150126                                                                     
##reference=hs37d5                                                                      
##pipeline_version=DVDS_v1.4.7.2
##resource_version=v1.0.8
##phasing=partial                                                                       
##source=JenniferYen                                                                    
##source=SteveChervitz - replaced RefSeq accessions w/ Genbank seq names, sorted using 'bedtools sort -i file.vcf'
##source=DeannaChurch - updated some entries and adding more non-coding variation, added IDs for easier tracking
##FILTER=<ID=INDEL_SPECIFIC_FILTERS,Description="QD < 2.0 || ReadPosRankSum < -20.0 || InbreedingCoeff < -0.8 || FS > 200.0">
##FILTER=<ID=LowQual,Description="Low quality">
##FILTER=<ID=VQSRTrancheSNP99.00to99.90,Description="Truth sensitivity tranche level for SNP model at VQS Lod: -6.6778 <= x < -0.6832">
##FILTER=<ID=VQSRTrancheSNP99.90to100.00+,Description="Truth sensitivity tranche level for SNP model at VQS Lod < -36469.5723">
##FILTER=<ID=VQSRTrancheSNP99.90to100.00,Description="Truth sensitivity tranche level for SNP model at VQS Lod: -36469.5723 <= x < -6.6778">
##FORMAT=<ID=AD,Number=.,Type=Integer,Description="Allelic depths for the ref and alt alleles in the order listed">
##FORMAT=<ID=DP,Number=1,Type=Integer,Description="Approximate read depth (reads with MQ=255 or with bad mates are filtered)">
##FORMAT=<ID=GQ,Number=1,Type=Integer,Description="Genotype Quality">
##FORMAT=<ID=GATK,Number=1,Type=String,Description="Genotype as called by GATK. Always a diploid call. All other genotype stats based on this genotype.">
##FORMAT=<ID=GT,Number=1,Type=String,Description="Genotype after Personalis post-processing to match detected chromosome counts.">
##INFO=<ID=OLD_VARIANT,Number=.,Type=String,Description="Original chr:pos:ref:alt encoding">
#CHROM  POS     ID      REF     ALT     QUAL    FILTER  INFO    FORMAT  NA00001
1       5935162 PTV001  A       T       88      PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:56
1       12065948        PTV002  C       T       .       PASS    .       GT:GATK:AD:DP:GQ        1/.:1/1:0,20:20:.
1       46655121        PTV003  GTCAC   G       .       PASS    OLD_VARIANT=1:46655125:CTCAC/C  GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:42
1       68912523        PTV004  TGAGCCAGAG      T       109     PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:109
1       68912523        PTV005  TGAGCCA T       80      PASS    OLD_VARIANT=1:68912526:GCCAGAG/G        GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:101
1       109817590       PTV006  G       T       77      PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:20
1       145597475       PTV007  GAAGT   G       .       PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:10,15:20:.
1       153791300       PTV008  CTG     C       81      PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:21
1       156104667       PTV009  TGAGAGCCGGCTGGCGGATGCGCT        CCCC    30      PASS    OLD_VARIANT=1:156104666:TTGAGAGCCGGCTGGCGGATGCGCT/TCCCC GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:22
1       156108540       PTV010  C       CG      31      PASS    OLD_VARIANT=1:156108541:G/GG    GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:23
1       161279695       PTV011  T       A       32      PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:24
1       169519049       PTV012  T       .       99      PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:109
1       226125468       PTV013  G       A       83      PASS    .       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:105
...

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

java -Xmx2G -jar /data/snpEff/snpEff.jar eff -canon -noLog hg19 hgvs_test_cases.vcf > /data/lab7/results/hgvs_test_cases_snpEff.clinvar.vcf 

time java -Xmx2G -jar /data/snpEff/SnpSift.jar annotate -noLog /data/snpEff/data/hg19/clinvar/clinvar_20190211.vcf.gz /data/lab7/results/hgvs_test_cases_snpEff.vcf > /data/lab7/results/hgvs_test_cases_snpEff.clinvar.vcf 

real	0m0.741s
user	0m1.749s
sys	0m0.112s

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
less /data/lab7/results/hgvs_test_cases_snpEff.clinvar.vcf

##fileformat=VCFv4.1                                                                    
##FILTER=<ID=PASS,Description="All filters passed">
##fileDate=20150126                                                                     
##reference=hs37d5                                                                      
##pipeline_version=DVDS_v1.4.7.2
##resource_version=v1.0.8
##phasing=partial                                                                       
##source=JenniferYen                                                                    
##source=SteveChervitz - replaced RefSeq accessions w/ Genbank seq names, sorted using 'bedtools sort -i file.vcf'
##source=DeannaChurch - updated some entries and adding more non-coding variation, added IDs for easier tracking
##FILTER=<ID=INDEL_SPECIFIC_FILTERS,Description="QD < 2.0 || ReadPosRankSum < -20.0 || InbreedingCoeff < -0.8 || FS > 200.0">
##FILTER=<ID=LowQual,Description="Low quality">
##FILTER=<ID=VQSRTrancheSNP99.00to99.90,Description="Truth sensitivity tranche level for SNP model at VQS Lod: -6.6778 <= x < -0.6832">
##FILTER=<ID=VQSRTrancheSNP99.90to100.00+,Description="Truth sensitivity tranche level for SNP model at VQS Lod < -36469.5723">
##FILTER=<ID=VQSRTrancheSNP99.90to100.00,Description="Truth sensitivity tranche level for SNP model at VQS Lod: -36469.5723 <= x < -6.6778">
##FORMAT=<ID=AD,Number=.,Type=Integer,Description="Allelic depths for the ref and alt alleles in the order listed">
##FORMAT=<ID=DP,Number=1,Type=Integer,Description="Approximate read depth (reads with MQ=255 or with bad mates are filtered)">
##FORMAT=<ID=GQ,Number=1,Type=Integer,Description="Genotype Quality">
##FORMAT=<ID=GATK,Number=1,Type=String,Description="Genotype as called by GATK. Always a diploid call. All other genotype stats based on this genotype.">
##FORMAT=<ID=GT,Number=1,Type=String,Description="Genotype after Personalis post-processing to match detecte
d chromosome counts.">
##INFO=<ID=OLD_VARIANT,Number=.,Type=String,Description="Original chr:pos:ref:alt encoding">
##SnpEffVersion="4.3t (build 2017-11-24 10:18), by Pablo Cingolani"
##SnpEffCmd="SnpEff  hg19 hgvs_test_cases.vcf "
##INFO=<ID=ANN,Number=.,Type=String,Description="Functional annotations: 'Allele | Annotation | Annotation_I
mpact | Gene_Name | Gene_ID | Feature_Type | Feature_ID | Transcript_BioType | Rank | HGVS.c | HGVS.p | cDNA
.pos / cDNA.length | CDS.pos / CDS.length | AA.pos / AA.length | Distance | ERRORS / WARNINGS / INFO' ">
##INFO=<ID=LOF,Number=.,Type=String,Description="Predicted loss of function effects for this variant. Format
: 'Gene_Name | Gene_ID | Number_of_transcripts_in_gene | Percent_of_transcripts_affected'">
##INFO=<ID=NMD,Number=.,Type=String,Description="Predicted nonsense mediated decay effects for this variant.
 Format: 'Gene_Name | Gene_ID | Number_of_transcripts_in_gene | Percent_of_transcripts_affected'">
#CHROM  POS     ID      REF     ALT     QUAL    FILTER  INFO    FORMAT  NA00001
1       5935162 PTV001  A       T       88.0    PASS    ANN=T|splice_acceptor_variant&intron_variant|HIGH|NP
HP4|NPHP4|transcript|NM_015102.4|protein_coding|20/29|c.2818-2T>A||||||;LOF=(NPHP4|NPHP4|1|1.00)    GT:GATK:
AD:DP:GQ        0/1:0/1:3,2:5:56
1       12065948        PTV002  C       T       .       PASS    ANN=T|missense_variant|MODERATE|MFN2|MFN2|tr
anscript|NM_001127660.1|protein_coding|14/18|c.1676C>T|p.Pro559Leu|1984/4532|1676/2274|559/757||    GT:GATK:AD:DP:GQ        1/.:1/1:0,20:20:.
1       46655121        PTV003  GTCAC   G       .       PASS    OLD_VARIANT=1:46655125:CTCAC/C;ANN=G|downstream_gene_variant|MODIFIER|TSPAN1|TSPAN1|transcript|NM_005727.3|protein_coding||c.*3917_*3920delTCAC|||||3488|,G|intron_variant|MODIFIER|POMGNT1|POMGNT1|transcript|NM_001243766.1|protein_coding|21/22|c.1869+31_1869+34delGTGA||||||       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:42
1       68912523        PTV004  TGAGCCAGAG      T       109.0   PASS    ANN=T|conservative_inframe_deletion|MODERATE|RPE65|RPE65|transcript|NM_000329.2|protein_coding|3/14|c.106_114delCTCTGGCTC|p.Leu36_Leu38del|168/2608|106/1602|36/533||   GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:109
1       68912523        PTV005  TGAGCCA T       80.0    PASS    OLD_VARIANT=1:68912526:GCCAGAG/G;ANN=T|conservative_inframe_deletion|MODERATE|RPE65|RPE65|transcript|NM_000329.2|protein_coding|3/14|c.109_114delTGGCTC|p.Trp37_Leu38del|168/2608|109/1602|37/533||     GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:101


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

less /data/lab7/results/hgvs_test_cases_snpEff.vcf

##fileformat=VCFv4.1                                                                    
##FILTER=<ID=PASS,Description="All filters passed">
##fileDate=20150126                                                                     
##reference=hs37d5                                                                      
##pipeline_version=DVDS_v1.4.7.2
##resource_version=v1.0.8
##phasing=partial                                                                       
##source=JenniferYen                                                                    
##source=SteveChervitz - replaced RefSeq accessions w/ Genbank seq names, sorted using 'bedtools sort -i file.vcf'
##source=DeannaChurch - updated some entries and adding more non-coding variation, added IDs for easier tracking
##FILTER=<ID=INDEL_SPECIFIC_FILTERS,Description="QD < 2.0 || ReadPosRankSum < -20.0 || InbreedingCoeff < -0.8 || FS > 200.0">
##FILTER=<ID=LowQual,Description="Low quality">
##FILTER=<ID=VQSRTrancheSNP99.00to99.90,Description="Truth sensitivity tranche level for SNP model at VQS Lod: -6.6778 <= x < -0.6832">
##FILTER=<ID=VQSRTrancheSNP99.90to100.00+,Description="Truth sensitivity tranche level for SNP model at VQS Lod < -36469.5723">
##FILTER=<ID=VQSRTrancheSNP99.90to100.00,Description="Truth sensitivity tranche level for SNP model at VQS Lod: -36469.5723 <= x < -6.6778">
##FORMAT=<ID=AD,Number=.,Type=Integer,Description="Allelic depths for the ref and alt alleles in the order listed">
##FORMAT=<ID=DP,Number=1,Type=Integer,Description="Approximate read depth (reads with MQ=255 or with bad mates are filtered)">
##FORMAT=<ID=GQ,Number=1,Type=Integer,Description="Genotype Quality">
##FORMAT=<ID=GATK,Number=1,Type=String,Description="Genotype as called by GATK. Always a diploid call. All other genotype stats based on this genotype.">
##FORMAT=<ID=GT,Number=1,Type=String,Description="Genotype after Personalis post-processing to match detected chromosome counts.">
##INFO=<ID=OLD_VARIANT,Number=.,Type=String,Description="Original chr:pos:ref:alt encoding">
##SnpEffVersion="4.3t (build 2017-11-24 10:18), by Pablo Cingolani"
##SnpEffCmd="SnpEff  hg19 hgvs_test_cases.vcf "
##INFO=<ID=ANN,Number=.,Type=String,Description="Functional annotations: 'Allele | Annotation | Annotation_Impact | Gene_Name | Gene_ID | Feature_Type | Feature_ID | Transcript_BioType | Rank | HGVS.c | HGVS.p | cDNA.pos / cDNA.length | CDS.pos / CDS.length | AA.pos / AA.length | Distance | ERRORS / WARNINGS / INFO' ">
##INFO=<ID=LOF,Number=.,Type=String,Description="Predicted loss of function effects for this variant. Format: 'Gene_Name | Gene_ID | Number_of_transcripts_in_gene | Percent_of_transcripts_affected'">
##INFO=<ID=NMD,Number=.,Type=String,Description="Predicted nonsense mediated decay effects for this variant. Format: 'Gene_Name | Gene_ID | Number_of_transcripts_in_gene | Percent_of_transcripts_affected'">
#CHROM  POS     ID      REF     ALT     QUAL    FILTER  INFO    FORMAT  NA00001
1       5935162 PTV001  A       T       88.0    PASS    ANN=T|splice_acceptor_variant&intron_variant|HIGH|NPHP4|NPHP4|transcript|NM_015102.4|protein_coding|20/29|c.2818-2T>A||||||;LOF=(NPHP4|NPHP4|1|1.00)    GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:56
1       12065948        PTV002  C       T       .       PASS    ANN=T|missense_variant|MODERATE|MFN2|MFN2|transcript|NM_001127660.1|protein_coding|14/18|c.1676C>T|p.Pro559Leu|1984/4532|1676/2274|559/757||    GT:GATK:AD:DP:GQ        1/.:1/1:0,20:20:.
1       46655121        PTV003  GTCAC   G       .       PASS    OLD_VARIANT=1:46655125:CTCAC/C;ANN=G|downstream_gene_variant|MODIFIER|TSPAN1|TSPAN1|transcript|NM_005727.3|protein_coding||c.*3917_*3920delTCAC|||||3488|,G|intron_variant|MODIFIER|POMGNT1|POMGNT1|transcript|NM_001243766.1|protein_coding|21/22|c.1869+31_1869+34delGTGA||||||       GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:42
1       68912523        PTV004  TGAGCCAGAG      T       109.0   PASS    ANN=T|conservative_inframe_deletion|MODERATE|RPE65|RPE65|transcript|NM_000329.2|protein_coding|3/14|c.106_114delCTCTGGCTC|p.Leu36_Leu38del|168/2608|106/1602|36/533||   GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:109
1       68912523        PTV005  TGAGCCA T       80.0    PASS    OLD_VARIANT=1:68912526:GCCAGAG/G;ANN=T|conservative_inframe_deletion|MODERATE|RPE65|RPE65|transcript|NM_000329.2|protein_coding|3/14|c.109_114delTGGCTC|p.Trp37_Leu38del|168/2608|109/1602|37/533||     GT:GATK:AD:DP:GQ        0/1:0/1:3,2:5:101




-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

java -Xmx2G -jar /data/snpEff/SnpSift.jar extractFields -s ',' -e '.' /data/lab7/results/hgvs_test_cases_snpEff.clinvar.vcf CHROM POS REF ALT ID "ANN[*].ALLELE" "ANN[*].EFFECT" "ANN[*].IMPACT" "ANN[*].GENE" "ANN[*].FEATURE" "ANN[*].FEATUREID" "ANN[*].BIOTYPE" "ANN[*].RANK" "ANN[*].HGVS_C" "ANN[*].HGVS_P" "ANN[*].CDNA_POS" "ANN[*].CDNA_LEN" "ANN[*].AA_LEN" "ANN[*].DISTANCE" "LOF[*].GENE" "LOF[*].NUMTR" "LOF[*].PERC" CLNREVSTAT RS CLNDNINCL ORIGIN MC CLNDN CLNVC CLNVI AF_EXAC AF_ESP CLNSIG CLNSIGINCL CLNDISDB GENEINFO CLNDISDBINCL AF_TGP CLNHGVS SSR > /data/lab7/results/hgvs_test_cases_snpEff.clinvar.Extracted


CHROM   POS     REF     ALT     ID      ANN[*].ALLELE   ANN[*].EFFECT   ANN[*].IMPACT   ANN[*].GENE     ANN[*].FEATURE  ANN[*].FEATUREID        ANN[*].BIOTYPE  ANN[*].RANK     ANN[*].HGVS_C   ANN[*].HGVS_P   ANN[*].CDNA_POS ANN[*].CDNA_LEN ANN[*].AA_LEN   ANN[*].DISTANCE LOF[*].GENE     LOF[*].NUMTR    LOF[*].PERC     CLNREVSTAT      RS      CLNDNINCL       ORIGIN  MC      CLNDN   CLNVC   CLNVI   AF_EXAC AF_ESP  CLNSIG  CLNSIGINCL      CLNDISDB        GENEINFO        CLNDISDBINCL    AF_TGP  CLNHGVS SSR
1       5935162 A       T       PTV001;167375   T       splice_acceptor_variant&intron_variant  HIGH    NPHP4   transcript      NM_015102.4     protein_coding  20      c.2818-2T>A     .       -1      -1      -1
      0       NPHP4   1       1.0     criteria_provided,_single_submitter     1217117155|1287637      .
       1       SO:0001574|splice_acceptor_variant      not_specified   single_nucleotide_variant       HGMD:CS057899   0.83625 0.84313 Benign  .       MedGen:CN169374 NPHP4:261734    .       0.84325 NC_000001.10:g.5935162A>T       .
1       12065948        C       T       PTV002  T       missense_variant        MODERATE        MFN2    transcript      NM_001127660.1  protein_coding  14      c.1676C>T       p.Pro559Leu     1984    4532    757
     0       .       .       .       .       .       .       .       .       .       .       .       .
       .       .       .       .       .       .       .       .       .
1       46655121        GTCAC   G       PTV003;56594    G,G     downstream_gene_variant,intron_variant  MODIFIER,MODIFIER       TSPAN1,POMGNT1  transcript,transcript   NM_005727.3,NM_001243766.1      protein_coding,protein_coding   -1,21   c.*3917_*3920delTCAC,c.1869+31_1869+34delGTGA   .,.     -1,-1   -1,-1   -1,-1   3488,0  .       .       .       no_assertion_criteria_provided  386834023       .       .       SO:0001575|splice_donor_variant,SO:0001627|intron_variant       Muscle_eye_brain_disease        Deletion        .
       .       .       Likely_pathogenic       .       MedGen:C0457133,OMIM:253280,Orphanet:ORPHA588,SNOMED_CT:277950001       TSPAN1:10103|POMGNT1:55624      .       .       NC_000001.10:g.46655126_46655129delTCAC .
1       68912523        TGAGCCAGAG      T       PTV004;98822    T       conservative_inframe_deletion   MODERATE        RPE65   transcript      NM_000329.2     protein_coding  3       c.106_114delCTCTGGCTC   p.Leu36_Leu38del        168     2608    533     0       .       .       .       no_assertion_provided   61751280
        .       .       .       not_provided    Deletion        .       .       .       not_provided    .
       MedGen:CN517202 RPE65:6121      .       .       NC_000001.10:g.68912524_68912532delGAGCCAGAG    .
1       68912523        TGAGCCA T       PTV005  T       conservative_inframe_deletion   MODERATE        RPE65   transcript      NM_000329.2     protein_coding  3       c.109_114delTGGCTC      p.Trp37_Leu38del        168     2608    533     0       .       .       .       .       .       .       .       .       .       .
       .       .       .       .       .       .       .       .       .       .       .
1       109817590       G       T       PTV006;7081     T,T     3_prime_UTR_variant,downstream_gene_variant
     MODIFIER,MODIFIER       CELSR2,PSRC1    transcript,transcript   NM_001408.2,NM_001032291.2      protein_coding,protein_coding   34,-1   c.*919G>T,c.*5185C>A    .,.     -1,-1   -1,-1   -1,-1   919,4586        .
       .       .       no_assertion_criteria_provided  12740374        .       1       .       Low_density_lipoprotein_cholesterol_level_quantitative_trait_locus_6    single_nucleotide_variant       OMIM_Allelic_Variant:602458.0001        .       .       association     .       MedGen:C3150834,OMIM:613589     CELSR2:1952|SORT1:6272|LOC110121285:110121285   .       0.19549 NC_000001.10:g.109817590G>T     .
1       145597475       GAAGT   G       PTV007  G,G,G   intron_variant,intron_variant,intron_variant    MODIFIER,MODIFIER,MODIFIER      NBPF20,NBPF10,POLR3C    transcript,transcript,transcript        NM_001278267.1,NM_001302371.1,NM_001303456.1    protein_coding,protein_coding,protein_coding    99,68,10        c.10988+232803_10988+232806delAGTA,c.8614+232018_8614+232021delAGTA,c.1109+35_1109+38delACTT    .,.,.   -1,-1,-1        -1,-1,-1        -1,-1,-1        0,0,0   .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .
1       153791300       CTG     C       PTV008  C       frameshift_variant      HIGH    GATAD2B transcript
      NM_020699.3     protein_coding  4       c.562_563delCA  p.Gln188fs      807     7296    593     0
       GATAD2B 1       1.0     .       .       .       .       .       .       .       .       .       .
       .       .       .       .       .       .       .       .
1       156104667       TGAGAGCCGGCTGGCGGATGCGCT        CCCC    PTV009  CCCC,CCCC       frameshift_variant&missense_variant,sequence_feature    HIGH,LOW        LMNA,LMNA       transcript,miscellaneous-region:Coil_2  NM_170707.3,NM_170707.3 protein_coding,protein_coding   4,4     c.711_734delTGAGAGCCGGCTGGCGGATGCGCTinsCCCC,c.711_734delTGAGAGCCGGCTGGCGGATGCGCTinsCCCC p.Glu238fs,.    960,-1  3227,-1 664,-1  0,0     LMNA    1       1.0
     .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .
1       156108540       C       CG      PTV010;66878    CG      frameshift_variant      HIGH    LMNA    transcript      NM_170707.3     protein_coding  11      c.1961dupG      p.Thr655fs      2211    3227    664     0
       .       .       .       criteria_provided,_single_submitter     863225024       .       1       SO:000

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------



---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

cp -p snpEff_summary.html /media/sf_Desktop/
copy and paste the summary html file onto the sf_Desktop and open it.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------



hgvs_test_cases_snpEff.clinvar.vcf --- 124.3 kB (124,269 bytes)
hgvs_test_cases_snpEff.vcf --- 92.5 kB (92,525 bytes)
hgvs_test_cases_snpEff.clinvar.Extracted --- 105.0 kB (104,991 bytes)
hgvs_test_cases.vcf --- 11.0 kB (11,005 bytes) 
snpEff_genes.txt --- 9.9 kB (9,853 bytes)
hgvs_test_cases_snpEff.clinvar.ORIG --- 92.5 kB (92,525 bytes)


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
cut -f9 hgvs_test_cases_snpEff.clinvar.Extracted

ANN[*].GENE
NPHP4
MFN2
TSPAN1,POMGNT1
RPE65
RPE65
CELSR2,PSRC1
NBPF20,NBPF10,POLR3C
GATAD2B
LMNA,LMNA
LMNA
MPZ,SDHC
.
LEFTY2
KLLN,PTEN
BSCL2,LRRN4CL,HNRNPUL2-BSCL2
ATM
ALG9
PRH1-PRR4
ABCC9
KRT5
PAH,PAH,PAH,PAH,PAH,PAH
PAH,PAH,PAH,PAH,PAH,PAH
PAH
TCTN1
C12orf65
B3GLCT
HIF1A
HIF1A
KCNH5
CAPN3
CAPN3
CAPN3,CAPN3,CAPN3,CAPN3,ZNF106
CAPN3,CAPN3,CAPN3,CAPN3,ZNF106
FBN1
NR2E3
POLG,MIR6766
TSC2
CREBBP
ALG1
FA2H
SPG7
SPG7,SPG7
SPG7
SPG7
SPG7
SPG7,SPG7
SPG7
SPG7
SPG7,SPG7
SPG7,SPG7,SPG7,SPG7,SPG7,SPG7
SPG7,SPG7,SPG7
SPG7,SPG7
TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53
TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53,TP53
FLCN
BRCA1
BRCA1
GFAP
SGCA,SGCA,HILS1
SCN4A
SCN4A
SCN4A
SCN4A
SCN4A
KCTD1
NOTCH3,MIR6795
NOTCH3,NOTCH3-EPHX3
RYR1,MAP4K1
LTBP4
NRXN1
NRXN1
DYSF
SCN2A,SCN2A
SCN2A
SCN1A
SCN1A
TTN,MIR548N,TTN-AS1
ZNF804A
NDUFB3
COL6A3
RSPH1
NF2
SHANK3
VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL,VHL
CACNA2D2,CYB561D2
CACNA2D2,CYB561D2
SLMAP
CASR
FBXW7
TERT,TERT-MIR4457
AP3B1
HSD17B4
SLC22A5,MIR3936,LOC553103
SH3TC2
FIG4
FIG4
SYNE1
SYNE1,SYNE1
PMS2
EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR,EGFR-AS1
EGFR,EGFR,EGFR,EGFR,EGFR-AS1
HSPB1
AKAP9
CFTR
BRAF
BRAF
BRAF
CLCN1
CLCN1,CLCN1
CLCN1,FAM131B
ARHGEF10
MPDZ
CDKN2A,CDKN2A-AS1
CA9,TPM2
TSC1
.
.
.
.
.
.
.
GJB1,BCYRN1
COL4A5,COL4A5
MECP2

cut -f14-16 hgvs_test_cases_snpEff.clinvar.Extracted

ANN[*].HGVS_C	ANN[*].HGVS_P	ANN[*].CDNA_POS
c.2818-2T>A	.	-1
c.1676C>T	p.Pro559Leu	1984
c.*3917_*3920delTCAC,c.1869+31_1869+34delGTGA	.,.	-1,-1
c.106_114delCTCTGGCTC	p.Leu36_Leu38del	168
c.109_114delTGGCTC	p.Trp37_Leu38del	168
c.*919G>T,c.*5185C>A	.,.	-1,-1
c.10988+232803_10988+232806delAGTA,c.8614+232018_8614+232021delAGTA,c.1109+35_1109+38delACTT	.,.,.	-1,-1,-1
c.562_563delCA	p.Gln188fs	807
c.711_734delTGAGAGCCGGCTGGCGGATGCGCTinsCCCC,c.711_734delTGAGAGCCGGCTGGCGGATGCGCTinsCCCC	p.Glu238fs,.960,-1
c.1961dupG	p.Thr655fs	2211
c.1A>T,c.-4501T>A	p.Met1?,.	68,-1
.	.	.
c.774C>T	p.Thr258Thr	1126
c.-794_-792delTGC,c.-671_-669delGCA	.,.	-1,-1
c.1376G>T,c.-1872G>T,n.3896G>T	p.Cys459Phe,.,.	1888,-1,-1
c.5761_5762insT	p.Arg1921fs	6147
c.406-7C>T	.	-1
n.1184+11736G>T	.	-1
c.2199-1302delG	.	-1
c.556-2A>G	.	-1
c.1200delG,c.1200delG,c.1200delG,c.1200delG,c.1200delG,c.1200delG	p.Asn401fs,.,.,.,.,.	1673,-1,-1,-1,-1,-1
c.1200delG,c.1200delG,c.1200delG,c.1200delG,c.1200delG,c.1200delG	p.Asn401fs,.,.,.,.,.	1673,-1,-1,-1,-1,-1
c.-216A>G	.	-1
c.342-1G>A	.	-1
c.210delA	p.Gly72fs	389
c.71-5delT	.	-1
c.295G>A	p.Ala99Thr	524
c.303_304delTTinsGA	p.AspLeu101GluMet	532
c.2366G>T	p.Gly789Val	2418
c.550delA	p.Thr184fs	856
c.550dupA	p.Thr184fs	857
c.2361_2362insTCA,c.2361_2362insTCA,c.2361_2362insTCA,c.2361_2362insTCA,c.*6322_*6323insTGA	.,.,.,p.Val787_Arg788insSer,.	-1,-1,-1,2668,-1
c.2362_2363delAGinsTCATCT,c.2362_2363delAGinsTCATCT,c.2362_2363delAGinsTCATCT,c.2362_2363delAGinsTCATCT,c.*6321_*6322delCTinsAGATGA	p.Arg788fs,.,.,.,.	2668,-1,-1,-1,-1
c.2927G>A	p.Arg976His	3322
c.951delC	p.Thr318fs	1147
c.752C>T,n.-3374C>T	p.Thr251Ile,.	1022,-1
c.277C>T	p.Arg93Trp	477
c.5748G>C	p.Met1916Ile	5952
c.826C>G	p.Arg276Gly	867
c.95G>A	p.Arg32His	171
c.-22C>A	.	-1
c.1A>C,c.1A>C	p.Met1?,.	31,-1
c.89_91dupGTC	p.Ser30_Pro31insArg	122
c.90dupT	p.Pro31fs	121
c.183+1G>A	.	-1
c.183+32C>A,c.183+32_183+33insA	.,.	-1,-1
c.184-2A>C	.	-1
c.216_217dupTG	p.Glu73fs	248
c.216_217insA,c.216dupT	p.Glu73fs,p.Glu73fs	247,247
c.1046_1071delGCCCCCCCGGCTGTGGGAAGACGCTG,c.1046_1071delGCCCCCCCGGCTGTGGGAAGACGCTG,c.1046_1071delGCCCCCCCGGCTGTGGGAAGACGCTG,c.1046_1071delGCCCCCCCGGCTGTGGGAAGACGCTG,c.1045_1070delGGCCCCCCCGGCTGTGGGAAGACGCT,c.1045_1070delGGCCCCCCCGGCTGTGGGAAGACGCT	p.Gly349fs,.,.,.,.,.	1076,-1,-1,-1,-1,-1
c.1450-1_1457delGGAGAGGCGinsT,c.1450-1_1457delGGAGAGGCGinsT,c.1450-1_1457delGGAGAGGCGinsT	p.Glu484fs,.,.	-1,-1,-1
c.1529C>T,c.1529C>T	.,p.Ala510Val	-1,1559
c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG,c.652_654delGTG.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,p.Val218del	-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,856
c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC,c.406dupC	p.Gln136fs,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.	608,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1
c.1300+2T>G	.	-1
c.*103_*106delTGTC	.	-1
c.301+1G>C	.	-1
c.490G>T	p.Glu164*	556
c.*11A>T,c.*11A>T,n.-2972T>A	.,.,.	-1,-1,-1
c.3720+9_3720+10dupGA	.	-1
c.3720+8_3720+9insA	.	-1
c.3442-8_3442-7insGC	.	-1
c.3442-8G>T	.	-1
c.2111C>T	p.Thr704Met	2188
c.234_239delGGAGGA	p.Glu78_Glu79del	239
c.2992C>T,n.-1613C>T	p.Gln998*,.	3068,-1
c.-78T>C,n.15311794A>G	.,.	-1,-1
c.14818G>A,c.*1858C>T	p.Ala4940Thr,.	14948,-1
c.3235dupG	p.Val1079fs	3236
c.4374A>G	p.Pro1458Pro	5851
c.1405C>T	p.Pro469Ser	2882
c.3678C>G	p.Ile1226Met	3819
c.1718G>C,c.1718G>C	p.Ser573Thr,.	2008,-1
c.2026A>G	p.Thr676Ala	2316
c.233_242delAGGACCTGGAinsGT	p.Glu78fs	260
c.233_240delAGGACCTG	p.Glu78fs	258
c.106974C>A,n.37-100011G>T,n.219+5141G>T	p.Ser35658Arg,.,.	107199,-1,-1
c.3324_3347delAGCTGCTGCAGCTGCAGCTGCAGC	p.Ala1109_Ala1116del	3918
c.208G>T	p.Gly70*	554
c.6282+1G>T	.	-1
c.727+5G>A	.	-1
c.924_925insCGACGC	p.Arg309_Arg310insArgArg	1368
c.1305-3_1305-1delGTT	.	-1
c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTC,c.341-7_343delCCGATAGGTCp.Gly114_His115delinsAsp,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.	-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1
c.3423A>C,n.50402127T>G	p.Gln1141His,.	3597,-1
c.3016C>T,n.50402890G>A	p.Pro1006Ser,.	3190,-1
c.1186+424delG	.	-1
c.3061G>C	p.Glu1021Gln	3499
c.45_46insCCT	p.Thr15_Gly16insPro	207
c.-79C>T,n.1295183G>A	.,.	-1,-1
c.2409_2411delGAA	p.Lys804del	2587
c.377+3_377+6delGAGT	.	-1
c.-75delG,n.-4297delC,n.21delC	.,.,.	-1,-1,-1
c.2813A>G	p.His938Arg	2965
c.124_126delGAT	p.Asp42del	339
c.123_124insCAG	p.Ile41_Asp42insGln	339
c.14018G>T	p.Arg4673Leu	14620
c.5929G>C,c.5929G>C	p.Ala1977Pro,.	6531,-1
c.1621A>G	p.Lys541Glu	1708
c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,c.2236_2250delGAATTAAGAGAAGCA,n.*4963_*4977delTGCTTCTCTTAATTC	.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,.,p.Glu746_Ala750del,.,.	-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,2482,-1,-1
c.2284-5_2290dupTCCAGGAAGCCT,c.2284-5_2290dupTCCAGGAAGCCT,c.2284-5_2290dupTCCAGGAAGCCT,c.2284-5_2290dupTCCAGGAAGCCT,n.1272_1283dupAGGCTTCCTGGA	.,.,.,p.Ala763_Tyr764insPheGlnGluAla,.	-1,-1,-1,2537,-1
c.82C>A	p.Leu28Ile	237
c.4004_4006dupAAC	p.Lys1335_Leu1336insGln	4232
c.1521_1523delCTT	p.Phe508del	1653
c.1798_1799delGTinsAG	p.Val600Arg	1860
c.1799T>G	p.Val600Gly	1860
c.1798G>A	p.Val600Met	1859
c.180+3A>T	.	-1
c.689G>A,c.689G>A	p.Gly230Glu,.	776,-1
c.2680C>T,c.*4872G>A	p.Arg894*,.	2767,-1
c.2471C>T	p.Pro824Leu	2673
c.5603dupC	p.Thr1869fs	5825
c.151-1G>T,n.*3455C>A	.,.	-1,-1
c.*2218_*2219insG,c.772+1002dupC	.,.	-1,-1
c.733C>T	p.Arg245*	967
.	.	-1
.	.	-1
.	.	-1
.	.	-1
.	.	-1
.	.	-1
.	.	-1
c.-101C>T,n.173-13048G>A	.,.	-1,-1
c.2130_2135delACCACC,c.2133_2135delACC	p.Pro711_Pro712del,p.Pro712del	2412,2415
c.538C>T	p.Arg180*	604


