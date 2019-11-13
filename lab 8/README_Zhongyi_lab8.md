##Lab 8##
##My name is Zhongyi Zhang.##

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Demo - Create my own genelist:

Open IGV; click "Regions", and then click "Gene Lists...". 
In the "KEGG canonical cancer pathways", we can find a list of genes in "KEGG_PANCREATIC_CANCER".
In "My lists", I created a list called "KEGG Pancreatic Chr1". I put "CDC42", "E2F2", "JAK1", "PIK3CD", PIK3R3", and "TGFB2" into my new created list. I click the "View" button at the bottom.
I can zoom in and out.

Right click "TGFB2" -> Switch to standard view
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Changing IGV:

control+click the head track. "Set allele frequency threshold" default = 0.2. We will use 0.05 since the number should usually be very small. We then do the same thing for the tumor, 0.05. 
we open IGV in the Virtual Machine. I Load from the files "IonXpress_003_rawlib_processed.bam", "TSVC_varlants.bed", and "TSVC_variants.vcf" files from the directory "data -> variantCaller_out.170 -> IonXpress_003".

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Annotate to find interesting regions:

Make he directory of lab8 folders with bin, data, doc, reults, and src subfolders.
From the results folder, 
java -Xmx2G -jar /data/snpEff/snpEff.jar eff -canon -noLog hg19 /data/variantCaller_out.170/IonXpress_003/TSVC_variants.vcf > TSVC_variants.snpEff.vcf
java -Xmx2G -jar /data/snpEff/SnpSift.jar annotate -noLog /data/snpEff/data/hg19/clinvar/clinvar_20190211.vcf.gz TSVC_variants.snpEff.vcf > TSVC_variants.snpEff.clinvar.vcf

grep stop 1033.chr1.cancer.ann.vcf | grep ’0/1’ | grep '0/0’
grep stop 1033.chr1.cancer.ann.vcf | grep ’1/1’ | grep '0/0’
grep ‘<each of KEGG genes on chr1>’ 1033.chr1.cancer.ann.vcf | grep ‘0/1’ | grep ‘0/0’
 - Nothing

Do some quick filtering:

grep -v "^#" TSVC_variants.snpEff.clinvar.vcf | grep -v '0/0'

chr2	29443617	239827	C	G	2568.66	PASS	AF=0.243077;AO=391;DP=1626;FAO=395;FDP=1625;FR=.,REALIGNEDx0.2608;FRO=1230;FSAF=191;FSAR=204;FSRF=599;FSRR=631;FWDB=0.0880781;FXX=0.000615002;HRUN=6;LEN=1;MLLD=55.7332;OALT=G;OID=.;OMAPALT=G;OPOS=29443617;OREF=C;QD=6.32285;RBI=0.154393;REFB=-0.0107859;REVB=0.126805;RO=1052;SAF=188;SAR=203;SRF=476;SRR=576;SSEN=0;SSEP=0;SSSB=0.0354559;STB=0.502612;STBP=0.906;TYPE=snp;VARB=0.0349679;ANN=G|structural_interaction_variant|HIGH|ALK|ALK|interaction|2XB7:A_1200-A_1258:NM_004304.4|protein_coding|23/29|c.3600G>C||||||,G|structural_interaction_variant|HIGH|ALK|ALK|interaction|2XBA:A_1200-A_1258:NM_004304.4|protein_coding|23/29|c.3600G>C||||||,G|structural_interaction_variant|HIGH|ALK|ALK|interaction|3LCT:A_1200-A_1258:NM_004304.4|protein_coding|23/29|c.3600G>C||||||,G|structural_interaction_variant|HIGH|ALK|ALK|interaction|4DCE:A_1200-A_1258:NM_004304.4|protein_coding|23/29|c.3600G>C||||||,G|structural_interaction_variant|HIGH|ALK|ALK|interaction|4FNZ:A_1200-A_1258:NM_004304.4|protein_coding|23/29|c.3600G>C||||||,G|structural_interaction_variant|HIGH|ALK|ALK|interaction|4JOA:A_1200-A_1258:NM_004304.4|protein_coding|23/29|c.3600G>C||||||,G|synonymous_variant|LOW|ALK|ALK|transcript|NM_004304.4|protein_coding|23/29|c.3600G>C|p.Ala1200Ala|4552/6265|3600/4863|1200/1620||;AF_TGP=0.01078;ALLELEID=238721;CLNDISDB=MedGen:C0027672,SNOMED_CT:699346009|MedGen:C2751681,OMIM:613014|MedGen:CN239480;CLNDN=Hereditary_cancer-predisposing_syndrome|Neuroblastoma_3|Neuroblastoma_Susceptibility;CLNHGVS=NC_000002.11:g.29443617C>G;CLNREVSTAT=criteria_provided,_multiple_submitters,_no_conflicts;CLNSIG=Benign/Likely_benign;CLNVC=single_nucleotide_variant;CLNVCSO=SO:0001483;CLNVI=Illumina_Clinical_Services_Laboratory,Illumina:267928;GENEINFO=ALK:238;MC=SO:0001819|synonymous_variant;ORIGIN=1;RS=56247462	GT:GQ:DP:FDP:RO:FRO:AO:FAO:AF:SAR:SAF:SRF:SRR:FSAR:FSAF:FSRF:FSRR	0/1:2568:1626:1625:1052:1230:391:395:0.243077:203:188:476:576:204:191:599:631
chr2	212576821	.	T	C	533.071	PASS	AF=0.0945;AO=767;DP=8360;FAO=189;FDP=2000;FR=.;FRO=1811;FSAF=97;FSAR=92;FSRF=855;FSRR=956;FWDB=0.00902711;FXX=0;HRUN=1;LEN=1;MLLD=330.124;OALT=C;OID=.;OMAPALT=C;OPOS=212576821;OREF=T;QD=1.06614;RBI=0.00938524;REFB=-0.000708078;REVB=-0.00256789;RO=7560;SAF=360;SAR=407;SRF=3579;SRR=3981;SSEN=0;SSEP=0;SSSB=-0.00493803;STB=0.537176;STBP=0.255;TYPE=snp;VARB=0.00713072;ANN=C|missense_variant|MODERATE|ERBB4|ERBB4|transcript|NM_005235.2|protein_coding|9/28|c.1078A>G|p.Thr360Ala|1176/11923|1078/3927|360/1308||,C|sequence_feature|LOW|ERBB4|ERBB4|beta-strand:combinatorial_evidence_used_in_manual_assertion|NM_005235.2|protein_coding|9/28|c.1078A>G||||||	GT:GQ:DP:FDP:RO:FRO:AO:FAO:AF:SAR:SAF:SRF:SRR:FSAR:FSAF:FSRF:FSRR	0/1:533:8360:2000:7560:1811:767:189:0.0945:407:360:3579:3981:92:97:855:956
chr2	212812097	.	T	C	3999.01	PASS	AF=0.279279;AO=999;DP=3461;FAO=558;FDP=1998;FR=.;FRO=1440;FSAF=311;FSAR=247;FSRF=796;FSRR=644;FWDB=-0.0084227;FXX=0.000999995;HRUN=1;LEN=1;MLLD=308.354;OALT=C;OID=.;OMAPALT=C;OPOS=212812097;OREF=T;QD=8.00603;RBI=0.0168837;REFB=-0.00564599;REVB=0.0146327;RO=2433;SAF=579;SAR=420;SRF=1318;SRR=1115;SSEN=0;SSEP=0;SSSB=0.047153;STB=0.503335;STBP=0.847;TYPE=snp;VARB=0.0148668;ANN=C|intron_variant|MODIFIER|ERBB4|ERBB4|transcript|NM_005235.2|protein_coding|3/27|c.421+58A>G||||||	GT:GQ:DP:FDP:RO:FRO:AO:FAO:AF:SAR:SAF:SRF:SRR:FSAR:FSAF:FSRF:FSRR0/1:3999:3461:1998:2433:1440:999:558:0.279279:420:579:1318:1115:247:311:796:644
...


grep -v "^#" TSVC_variants.snpEff.clinvar.vcf | grep -v '0/0' | grep stop

 - stop_lost|HIGH|PIK3CA|PIK3CA|transcript|NM_006218.3
 - stop_gained|HIGH|TP53|TP53|transcript|NM_000546.5|protein_coding|5/11|c.511G

chr3	178952152	COSM17449	A	G	60.867	NOCALL	AF=0.000500751;AO=8;DP=6167;FAO=1;FDP=1997;FR=.;FRO=1996;FSAF=0;FSAR=1;FSRF=921;FSRR=1075;FWDB=-0.0123818;FXX=0.00149999;HRUN=4;LEN=1;MLLD=71.8518;OALT=G;OID=COSM17449;OMAPALT=G;OPOS=178952152;OREF=A;QD=0.121917;RBI=0.0131356;REFB=-0.000142767;REVB=0.00438559;RO=6158;SAF=3;SAR=5;SRF=2876;SRR=3282;SSEN=0;SSEP=0;SSSB=-0.0051111;STB=0.989452;STBP=0.464;TYPE=snp;VARB=0.128787;HS;ANN=G|stop_lost|HIGH|PIK3CA|PIK3CA|transcript|NM_006218.3|protein_coding|21/21|c.3207A>G|p.Ter1069Trpext*?|3364/9093|3207/3207|1069/1068||	GT:GQ:DP:FDP:RO:FRO:AO:FAO:AF:SAR:SAF:SRF:SRR:FSAR:FSAF:FSRF:FSRR	./.:60:6167:1997:6158:1996:8:1:0.000500751:5:3:2876:3282:1:0:921:1075
chr17	7578419	COSM10996;COSM45751;COSM44312;141566	C	A,G,T	360.702	PASS	AF=0,0,0.0611716;AO=1,0,119;DP=1933;FAO=0,0,118;FDP=1929;FR=.,REALIGNEDx0.07668;FRO=1811;FSAF=0,0,79;FSAR=0,0,39;FSRF=1127;FSRR=684;FWDB=-0.00179485,-0.00537647,0.0657739;FXX=0.0025853;HRUN=2,2,2;LEN=1,1,1;MLLD=390.305,340.513,79.5351;OALT=A,G,T;OID=COSM10996,COSM45751,COSM44312;OMAPALT=A,G,T;OPOS=7578419,7578419,7578419;OREF=C,C,C;QD=0.747956;RBI=0.00605742,0.0172139,0.0756808;REFB=0.000346961,0.000551718,0.00535277;REVB=-0.0057854,-0.0163527,0.037435;RO=1813;SAF=1,0,79;SAR=0,0,40;SRF=1126;SRR=687;SSEN=0,0,0;SSEP=0,0,0;SSSB=0.00957119,0,0.0496341;STB=0.5,0.5,0.548397;STBP=1,1,0.3;TYPE=snp,snp,snp;VARB=0,0,-0.0914473;HS;ANN=A|stop_gained|HIGH|TP53|TP53|transcript|NM_000546.5|protein_coding|5/11|c.511G>T|p.Glu171*|713/2591|511/1182|171/393||,A|structural_interaction_variant|HIGH|TP53|TP53|interaction|1TSR:A_171-A_249:NM_000546.5|protein_coding|5/11|c.511G>T||||||,G|structural_interaction_variant|HIGH|TP53|TP53|interaction|1TSR:A_171-A_249:NM_000546.5|protein_coding|5/11|c.511G>C||||||,T|structural_interaction_variant|HIGH|TP53|TP53
...



----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

View Hotspot files in stop region
It has total count of 1,934
chr17: 7,578,419
copy to COSMIC ID
COSMIC -> Mutation -> Overview:
Mutation ID
    COSM46095
Gene name
    TP53 
AA mutation
    p.E171fs*3 (Deletion - Frameshift) 
CDS mutation
    c.511delG (Deletion) 
Nucleotides inserted
    n/a 



----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
EGFR hotspot sample:
I will just put the four at the two ends. I also attached the screenshots for these four (two for each end).

Then I load the "EGFR_19_DEL_EGFR_20_INS.143", "CHP2.20131001.hotspots.bed", "EGFR_19_DEL_EGFR_20_INS.143.rawlib_processed.bam", and "EGFR_19_DEL_EGFR_20_INS.143.vcf.gz" files from the EGFR_19_DEL_EGFR_20_INS.143 folder on the IGV. We zoom in to find the right alleles. chr7:55,242,464, Total count: 2804, A:2804
chr7:55,242,465, Total count:1267, G:1267
...
chr7:55,242,479, Total count: 1269, A:5, C:1260, G:2, T:2
CHR7:55,242,480, Total count: 2814, A: 2812, G: 2

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Pevsner example -Chapter 20 #3:

[student@msbi32400lab5 ~]$ for chr in {1..22} X Y MT
> do
>   esearch -db gene -query "Homo sapiens [ORGN] AND $chr [CHR]" |
>   efilter -query "alive [PROP] AND genetype protein coding [PROP]" |
>   efetch -format docsum |
>   xtract -pattern DocumentSummary -NAME Name -block GenomicInfoType -match "ChrLoc:$chr" -tab "\n" -element ChrLoc,"&NAME" |
>   grep '.' | sort | uniq | cut -f 1 |
>   sort-uniq-count-rank
> done > how_many_genes_030619

Open a new terminal:
[student@msbi32400lab5 ~]$ tail -fv how_many_genes_030619 
==> how_many_genes_030619 <==
2043	1
1256	2
1071	3
754	4
876	5
1041	6
901	7
684	8
789	9
727	10
1292	11
1017	12
328	13
612	14
600	15
856	16
1174	17
274	18
1406	19
547	20
246	21
442	22
857	X
66	Y
13	MT

Script outputs a list of counts by chr:

[student@msbi32400lab5 ~]$ cut -f1 how_many_genes_030619 | paste -sd+ | bc
19872

[student@msbi32400lab5 ~]$ cut -f1 genes_by_chr.txt | paste -sd+ | bc
19877

we lost five genes.







----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
