##Lab 5##
##My name is Zhongyi Zhang.##

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

less 7657.23andme.6002 -> original file
grep -v "^#" 7657.23andme.6002 | wc -l
There are 638,469 lines in total.

less 7657.23andme.6002.vcf
grep -v "^#" 7657.23andme.6002.vcf | wc -l
There are 615,555 lines in total

638,469 - 615,555 = 22,914 lines
There were 22,914 line excluded.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

##fileformat=VCFv4.2
##fileDate=20190219
##source=23andme2vcf.pl https://github.com/arrogantrobot/23andme2vcf
##reference=file://23andme_v5_hg19_ref.txt.gz
##FORMAT=<ID=GT,Number=1,Type=String,Description="Genotype">

/stop
------------------------
The result I got:

chr1    11906068        rs5065  A       G       .       .       ANN=G|stop_lost|HIGH|NPPA|NPPA|transcript|NM_006172.3|protein_coding|3/3|c.454T>C|p.Ter152Argext*?|553/854|454/456|152/151||,G|downstream_gene_variant|MODIFIER|CLCN6|CLCN6|transcript|NM_001286.3|protein_coding||c.*5788A>G|||||2867|,G|intron_variant|MODIFIER|NPPA-AS1|NPPA-AS1|transcript|NR_037806.1|pseudogene|3/3|n.1479+245A>G||||||   GT      0/1
chr1    11906981        rs198370        T       .       .       .       .       GT      0/0
chr1    11907648        rs5063  C       .       .       .       .       GT      0/0
chr1    11907740        i707013 A       .       .       .       .       GT      0/0
chr1    11909514        rs198372        G       A       .       .       ANN=A|upstream_gene_variant|MODIFIER|NPPA|NPPA|transcript|NM_006172.3|protein_coding||c.-1773C>T|||||1674|,A|downstream_gene_variant|MODIFIER|NPPA-AS1|NPPA-AS1|transcript|NR_037806.1|pseudogene||n.*1841G>A|||||1841|,A|intergenic_region|MODIFIER|NPPA-NPPB|NPPA-NPPB|intergenic_region|NPPA-NPPB|||n.11909514G>A||||||      GT      0/1
chr1    11918303        rs191451400     C       .       .       .       .       GT      0/0
chr1    11918519        rs5229  C       .       .       .       .       GT      0/0
chr1    11919271        rs198389        A       G       .       .       ANN=G|upstream_gene_variant|MODIFIER|NPPB|NPPB|transcript|NM_002521.2|protein_coding||c.-381T>C|||||279|,G|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11919271A>G|||||| GT      0/1
chr1    11924030        rs79712000      T       .       .       .       .       GT      0/0
chr1    11925300        rs6676300       A       G       .       .       ANN=G|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11925300A>G||||||      GT      0/1
chr1    11926350        rs4846061       C       A       .       .       ANN=A|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11926350C>A||||||      GT      0/1
chr1    11926758        rs74714707      C       .       .       .       .       GT      0/0
chr1    11927056        rs12562952      T       C       .       .       ANN=C|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11927056T>C||||||      GT      0/1
chr1    11936324        rs9661078       A       C       .       .       ANN=C|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11936324A>C||||||      GT      0/1
chr1    11936514        rs11804222      G       A       .       .       ANN=A|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11936514G>A||||||      GT      0/1
chr1    11936644        rs79593079      C       .       .       .       .       GT      0/0
chr1    11937404        rs7554327       T       C       .       .       ANN=C|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11937404T>C||||||      GT      1/1
chr1    11938050        rs4846066       G       A       .       .       ANN=A|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-KIAA2013|intergenic_region|NPPB-KIAA2013|||n.11938050G>A||||||      GT      0/1
chr1    11938399        rs72864766      G       A       .       .       ANN=A|intergenic_region|MODIFIER|NPPB-KIAA2013|NPPB-


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

snpEff Summary Files:

By opening the snpEff_summary.html file, I found that there were 7 counts (0.004%) were classified as "stop_lost" and 14 counts (0.008%) were counted as "stop_gained."
7 counts - stop_lost
14 counts - stop_gained

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


search for lines containing CLNSIG=Pathogenic

chr8    11606312        rs3735819;433016        T       C       .       .       ANN=C|intron_variant|MODIFIER|GATA4|GATA4|transcript|NM_001308093.1|protein_coding|1/5|c.617-113T>C||||||;AF_TGP=0.87161;ALLELEID=426523;CLNDISDB=MedGen:C0152021,SNOMED_CT:13213009;CLNDN=Congenital_heart_disease;CLNHGVS=NC_000008.10:g.11606312T>C;CLNREVSTAT=no_assertion_criteria_provided;CLNSIG=Pathogenic;CLNVC=single_nucleotide_variant;CLNVCSO=SO:0001483;GENEINFO=GATA4:2626;MC=SO:0001627|intron_variant;ORIGIN=0;RS=3735819      GT      0/1
chr8    11607396        rs3735814       G       A       .       .       ANN=A|intron_variant|MODIFIER|GATA4|GATA4|transcript|NM_001308093.1|protein_coding|2/5|c.787-224G>A||||||       GT      0/1
chr8    11610674        rs11784693      C       T       .       .       ANN=T|intron_variant|MODIFIER|GATA4|GATA4|transcript|NM_001308093.1|protein_coding|3/5|c.913-1881C>T||||||      GT      0/1
chr8    11612381        rs13273672      T       C       .       .       ANN=C|intron_variant|MODIFIER|GATA4|GATA4|transcript|NM_001308093.1|protein_coding|3/5|c.913-174T>C||||||       GT      0/1
chr8    11612698        rs804280;139596 C       A       .       .       ANN=A|intron_variant|MODIFIER|GATA4|GATA4|transcript|NM_001308093.1|protein_coding|4/5|c.1000+56C>A||||||;AF_ESP=0.59396;AF_TGP=0.73443;ALLELEID=143221;CLNDISDB=MedGen:C0152021,SNOMED_CT:13213009|MedGen:CN517202;CLNDN=Congenital_heart_disease|not_provided;CLNHGVS=NC_000008.10:g.11612698C>A;CLNREVSTAT=no_assertion_criteria_provided;CLNSIG=Conflicting_interpretations_of_pathogenicity;CLNSIGCONF=Pathogenic(1)%3BUncertain_significance(1);CLNVC=single_nucleotide_variant;CLNVCSO=SO:0001483;GENEINFO=GATA4:2626;MC=SO:0001627|intron_variant;ORIGIN=0;RS=804280    GT      0/1
chr8    11614225        rs4841588       G       T       .       .       ANN=T|upstream_gene_variant|MODIFIER|C8orf49|C8orf49|transcript|NR_103552.1|pseudogene||n.-4540G>T|||||4540|,T|intron_variant|MODIFIER|GATA4|GATA4|transcript|NM_001308093.1|protein_coding|4/5|c.1001-219G>T||||||     GT      0/1
chr8    11614575        rs3729856       A       .       .       .       .       GT      0/0
chr8    11615875        rs115099192     C       .       .       .       .       GT      0/0
chr8    11615928        rs56208331      G       .       .       .       .       GT      0/0
chr8    11617365        rs3735812       A       .       .       .       .       GT      0/0
chr8    11618107        rs9329248       C       A       .       .       ANN=A|upstream_gene_variant|M


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Pharmacogenomics: 
*1 – Normal Status
*2, *3A, *3B, *3C, *4 – No function

rs1800462: *1-C / *2-G
By looking at the 23andme file, "rs1800462" has 6 chromosomes with position 18143955, and the genotype is CC. By looking at the TPMT allele definition table, it has star allele at *1-C / *2-G.

rs1142345: *1-T / *3A-C/ *3C-C / *41-G
By looking at the 23andme file, "rs1142345" has 6 chromosomes with position 18130918, and the genotype is TT. 
By looking at the TPMT allele definition table, it has star allele at *1-T / *3A-C/ *3C-C / *41-G.

rs1800460: *1-C / *3A-T/ *3B-T
By looking at the 23andme file, "rs1800460" has 6 chromosomes with position 18139228, and the genotype is CC. 
By looking at the TPMT allele definition table, it has star allele at *1-C / *3A-T/ *3B-T.

rs1800584: *1-C / *4-T
By looking at the 23andme file, "rs1800584" has 6 chromosomes with 18131012 positions, and the genotype is CC. By looking at the TPMT allele definition table, it has star allele at *1-C / *4-T.

By looking at the allele *1
The first is CTCC, and the second is CTCC.
Compared with the TPMT Translation Table, it will be *1/*1.
Final Answer: CTCC - (*1/*1)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Interpretation for TPMT status

dbSNP: 1800460	Genotype: CC	      Evidence Level: 1	Gene: TPMT	
Interpretation: Patients with the CC genotype may have a decreased risk for toxicity with thiopurine drugs and purine analogues as compared to patients with the CT or TT genotype. Patients with the CC genotype may still be at risk for toxicity when taking thiopurine drugs and purine analogues based on their genotype. Other genetic and clinical factors may also influence a patient's risk for toxicity.

dbSNP: 1800462	Genotype: CC	Evidence Level: 1	Gene: TPMT	
Interpretation: Patients with the CC genotype: 1) may have decreased metabolism of thiopurines 2) may have a decreased risk for toxicity with thiopurine drugs as compared to patients with the CG or GG genotype. Patients with the CC genotype may still be at risk for toxicity when taking thiopurine drugs based on their genotype. Other genetic and clinical factors may also influence a patient's risk for toxicity.


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Describe the Clinical/Lung Function results:

Here are my lung function results:

Lung Function
Lung function is assessed by how much air your lungs can store and how fast your lungs can expel. These are measured by forced expiratory volume in one second (FEV1), forced vital capacity (FVC) and the FEV1 to FVC ratio (FEV1/FVC). Lung function is important for assessing conditions such as asthma,pulmonary fibrosis, cystic fibrosis, and COPD.
Forced vital capacity is the maximal amount of air you can expel from your lungs. A normal adult has a vital capacity between 3 and 5 litres, but this amount depends on your size, sex, age and ethnicity. Forced vital capacity shows an annual rate of decline ranging from 12 to 47 ml in the general population. For people with lung disease, forced vital capacity can be reduced. For athletes, forced vital capacity is a measure of your aerobic capacity. Twin studies indicate that the heritability of FVC is very high - 91%.
Forced expiratory volume in 1 second (FEV1) is the amount of air you can expel in 1 second. Twin studies indicate that the heritability of FVC is very high -85%.
FEV1/FVC is the ratio of FEV1 to FVC. In healthy adults this should be approximately 70–85%. In obstructive diseases (asthma, COPD, chronic bronchitis, emphysema), this ratio is lower than normal because your ability to exhale is affected more than the total volume in your lungs. In restrictive disease (pulmonary fibrosis), this ratio is either not affected or is higher because the total volume of air in your lungs is diminished. Twin studies indicate that the heritability of FVC is very high – 45%.

Show my lung function SNPs:

 
Disease	Measurement	Genes	dbSNP	Genotype	Risk Allele	OR or beta	P-Value	Link
Pulmonary function		HHIP	13147758	AA	G	0.1	8.00E-11	19300500

Pulmonary function	(FEV1/FVC)	AGER	2070600	CC	T	0.09	3.00E-15	20010834

Pulmonary function	(FEV1)	HTR4	3995090	AC	C	0.07	4.00E-09	20010834

Pulmonary function	(FEV1)	GSTCD	10516526	AA	G	0.14	2.00E-23	20010834

Pulmonary function	(FEV1/FVC)	HHIP	12504628	TT	T	0.27	6.00E-13	20010834

Pulmonary function	(FEV1/FVC)	THSD4	12899618	AG	G	0.09	7.00E-15	20010834

Pulmonary function	(FEV1/FVC)	HHIP	1980057	CC	T	0.52	3.00E-20	20010835

Pulmonary function	(FEV1/FVC)	AGER, PPT2	2070600	CC	T	1	3.00E-14	20010835

Pulmonary function	(FEV1/FVC)	ADAM19	2277027	AA	A	0.38	1.00E-10	20010835

Pulmonary function	(FEV1/FVC)	GPR126	3817928	AA	A	-0.42	1.00E-09	20010835

Pulmonary function	(FEV1/FVC)	HTR4	11168048	CT	T	-0.4	1.00E-11	20010835

Pulmonary function	(FEV1/FVC)	SPATA9	153916	CT	T	-0.03	2.00E-08	21946350

Pulmonary function	(FEV1/FVC)	TGFB2	993925	CT	T	0.03	1.00E-08	21946350

Pulmonary function	(FEV1/FVC)	RARB	1529672	CC	C	-0.05	4.00E-14	21946350

Pulmonary function	(FEV1/FVC)	MFAP2	2284746	CC	G	-0.04	8.00E-16	21946350

Pulmonary function	(FEV1/FVC)	ARMC2	2798641	CC	T	-0.04	8.00E-09	21946350

Pulmonary function	(FEV1/FVC)	NCR3	2857595	AA	G	0.04	2.00E-10	21946350

Pulmonary function	(FEV1/FVC)	CDC123	7068966	TT	T	0.03	6.00E-13	21946350

Pulmonary function	(FEV1/FVC)	KCNE2	9978142	AA	T	-0.04	3.00E-08	21946350

Pulmonary function	(FEV1/FVC)	LRP1	11172113	CC	T	-0.03	1.00E-08	21946350

Pulmonary function	(FEV1/FVC)	MMP15	12447804	CT	T	-0.04	4.00E-08	21946350

Pulmonary function	(FEV1/FVC)	HDAC4	12477314	CT	T	0.04	2.00E-12	21946350

Pulmonary function	(FEV1)	ZKSCAN3, ZNF323	6903823	AG	G	-0.04	2.00E-10	21946350

Pulmonary function	(FEV1)	CDC123	7068966	TT	T	0.03	3.00E-12	21946350

Pulmonary function	(FEV1)	C10orf11	11001819	GG	G	-0.03	3.00E-12	21946350

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	RARB	1529672	CC	?	NR	7.00E-11	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	HHIP	1980057	CC	?	NR	5.00E-18	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	AGER	2070600	CC	?	NR	1.00E-21	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	ADAM19	2277027	AA	?	NR	2.00E-11	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	MFAP2	2284746	CC	?	NR	2.00E-11	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	FAM13A	2869967	CT	?	NR	5.00E-11	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	GPR126	3817928	AA	?	NR	3.00E-12	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	CDC123	7068966	TT	?	NR	2.00E-11	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	DNER	7594321	CC	T	0	5.00E-11	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	DNER	7594321	CC	T	-0.02	3.00E-09	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	HLA-DQB1, HLA-DQA2	7764819	TT	T	0	4.00E-09	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	HLA-DQB1, HLA-DQA2	7764819	TT	T	0	4.00E-09	23284291

Pulmonary function (interaction)	"""(FEV1, Ever-smoking)"""	C10orf11	11001819	GG	?	NR	5.00E-08	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	HTR4	11168048	CT	?	NR	5.00E-17	23284291

Pulmonary function (interaction)	"""(FEV1, Ever-smoking)"""	KCNJ2, SOX9	11654749	GG	T	-0.02	1.00E-08	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	MMP15	12447804	CT	?	NR	4.00E-08	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	THSD4	12899618	AG	?	NR	4.00E-21	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	PTCH1	16909898	AA	?	NR	8.00E-12	23284291

Pulmonary function (interaction)	"""(FEV1, Ever-smoking)"""	INTS12, GSTCD, NPNT	17331332	GG	?	NR	1.00E-16	23284291

Pulmonary function decline	(FEV1/FVC decline in asthmatics)	TUSC3	4831760	CT	?	0.22	5.00E-08	22424883

Pulmonary function	(FEV1)	TNS1	2571445*	??	G	0.07	1.00E-12	20010834

Pulmonary function	(FEV1)	INTS12, NPNT, FLJ20184, GSTCD	11727189*	??	T	64.7	5.00E-17	20010835

Pulmonary function	(FEV1/FVC)	CCDC38	1036429*	??	T	0.04	2.00E-11	21946350

Pulmonary function	(FEV1/FVC)	CFDP1	2865531*	??	T	0.03	2.00E-11	21946350

Pulmonary function	(FEV1)	MECOM	1344555*	??	T	-0.03	3.00E-08	21946350

Pulmonary function (interaction)	"""(FEV1/FVC, Ever-smoking)"""	PID1	1435867*	??	?	NR	2.00E-09	23284291

Pulmonary function (interaction)	"""(FEV1, Ever-smoking)"""	TNS1	2571445*	??	?	NR	8.00E-09	23284291

Pulmonary function (interaction)	"""(FEV1/FVC, Pack-years)"""	CFDP1	2865531*	??	?	NR	2.00E-08	23284291

 
The beta scores for the SNPs reported by Artigas et al., 2011 (PMID 21946350) denote FEV1 (ml) or FEV1/FVC (%). So for rs2284746 associated with FEV1/FVC, the beta score of .04 means each G allele raises the ratio by .04%. For rs7068966 associated with FEV1, the beta score of .03 means that each T allele raises the FEV1 volume by .03 mls.
 

 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 
The genotypes for CYP2C19 are CC and GG.
dbSNP: 12248560	Genotype: CC	      Evidence Level: 1	Gene: CYP2C19	
Interpretation: Patients with the CC genotype: 1) may have decreased activation of clopidogrel 2) may have a decreased risk for bleeding with clopidogrel as compared to patients with the CT or TT genotype 3) may have an increased risk for adverse cardiovascular events as compared to patients with a CT or TT genotype. Patients with the CC genotype may still be at risk for bleeding when taking clopidogrel based on their genotype. Other genetic and clinical factors may also influence a patient's risk for bleeding.

dbSNP: 4244285	Genotype: GG	      Evidence Level: 1	Gene: CYP2C19	
Interpretation: Patients with the GG genotype: 1) may have sufficient metabolism of clopidogrel and increased formation of active drug metabolite 2) may have a decreased risk for secondary cardiovascular events with clopidogrel as compared to patients with the AA or AG genotype. Patients with the GG genotype may still be at risk for secondary cardiovascular events when taking clopidogrel based on their genotype. Other genetic and clinical factors may also influence a patient's risk for secondary cardiovascular events..

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Does your genotype have any risk alleles associated with Caffeine consumption?

- Yes I have CC, CT, AT, CT, AG, and CC genotypes that have risk alleles associated with Caffeine consumption.

Coffee SNPs:
These are the genotype that has risk alleles associated with caffeine consumption.
Disease	Genes	dbSNP	Genotype	Risk Allele	OR or beta	P-Value	Link	Score
Coffee consumption	CYP1A1, CYP1A2	2470893	CC	T	0.2	5.00E-19	25288136
0.000e+0
Coffee consumption (cups per day)	AHR	4410790	CC	T	-0.1	3.00E-17	25288136
0.000e+0
Coffee consumption (cups per day)	MLXIPL, TBL2, VPS37D	7800944	CT	T	-0.05	3.00E-11	25288136
-5.000e-2
Coffee consumption (cups per day)	EFCAB5, SSH2, CCDC55	9902453	AG	A	-0.03	3.00E-08	25288136
-8.000e-2
Coffee consumption (cups per day)	GCKR, FNDC4	1260326	CT	T	-0.04	7.00E-08	25288136
-1.200e-1
Coffee consumption (cups per day)	ABCG2, PKD2, PPM1K	1481012	AG	A	0.06	9.00E-08	25288136
-6.000e-2
Coffee consumption (cups per day)	BDNF	6265	CC	T	-0.04	6.00E-07	25288136
-6.000e-2
Coffee consumption (cups per day)	POR, SNORA14A, TMEM120A	17685*	??	A	0.07	4.00E-11	25288136
-2.094e-2


Chasman and others have done a large study on SNPs associated with amount of coffee consumed per day. The eight SNPs can be added together in a genetic risk score indicating the effect of these snps on coffee consumption.
 
Caffeine has been shown to improve athletic performance during high intensity and endurance exercise when taken 60-90 minutes before, and during exercise (Graham and Spriet, 1995; Jenkins et al., 2008; Desbrow et al., 2012; Doherty and Smith, 2004). The improvement in performance is through caffeine's direct antagonism of adenosine receptors (A1 and A2A) on the skeletal muscle membrane to induce effects on the central and peripheral nervous system to reduce pain and exertion perception (Doherty and Smith, 2005), improve motor recruitment, and excitation-contraction coupling (Mohr et al., 2011).

The heritability of coffee consumption is in the range of 0.39 to 0.56.

Caffeine is metabolized primarily by CYP1A2 in the liver. This enzyme accounts for approximately 95% of caffeine metabolism and demonstrates a wide variability in activity between individuals (Gu et al., 1992; Rasmussen et al., 2002). This is one of the reasons that you might be able to drink two cups of coffee in the afternoon and still fall asleep as usual, but your friend can’t drink a single cup past 10am without disturbing their normal sleep pattern. Rs2470893 lies within the CYP1A2 gene. Those with the TC or  CC genotypes are “slow” caffeine metabolizers, whereas individuals with the TT genotype are “fast” caffeine metabolizers (Sachse et al., 1999).

AHR is a transcription factor that turns on expression of CYP1A2. When you drink coffee, AHR becomes activated to turn on CYP1A2 expression, which inactivates the caffeine. Genetic variation in AHR leads to different levels of CYP1A2, resulting in diferent rates of clearance of caffeine from your system. Rs4410790 lies in the AHR gene, and the T allele is associated with a slower rate of caffeine clearance than the C allele.
 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Does your genotype have any risk for motion sickness?

- Yes, I have genotypes that have risk for motion sickness.

Motion Sickness score:
Gene	dbSNP	      Genotype	  Risk Allele	      β   	    Score
PVRL3	66800491 	  AG	                 G	         -0.078	-7.800e-2
ACO1	10970305	          CC	                 C	         -0.057	-1.920e-1
NLGN1	11713169	           AA            	C	         -0.052	-1.920e-1
GPR26	705145	           CC	                 C	          -0.051	-2.940e-1
TLE4	149951341	   AA	                 C	          -0.05	 -2.940e-1
CNTN1	7957589	           TT               	T	         -0.047	-3.880e-1
POU6F2	60464047	           TT	                 T	        -0.043	-4.740e-1
CPNE4	9834560	          CC              	C         	-0.041	-5.560e-1
RWDD3	1858111	          AG	                G	        -0.039	-5.950e-1
SDK1	34912216	          GG	                G	         -0.035	-6.650e-1
MAP2K5	 997295	          GT	                 T	        -0.033	-6.980e-1
AGA	        1378552	           CT                	T	         -0.032	-7.300e-1
TUSC1	1782032	          AA	                G	         -0.031	-7.300e-1
GXYLT2	1847202	          CC	                T	          0.031	-7.300e-1
AUTS2	6946969          	AG	               G	         0.033	-6.970e-1
RGS5	4076764	         CT	                T	         0.033	-6.640e-1
SDK1	4343996	         AG	               G	         0.034	-6.300e-1
CELF2	10752212	         AG	               G	         0.034	-5.960e-1
NR2F2	7170668	         TT                   T	         0.035	-5.260e-1
COPS8	2318131	         AA	               C	         0.038	-5.260e-1
LINGO2	2150864	         AG	               G	          0.042	-4.840e-1
MUTED	2153535         	CC	               G	         0.046	-4.840e-1
ARAP2	6833641	         CC	               G	          0.046	-4.840e-1
PRDM16	61759167	        CC                	T	         0.047	-4.840e-1
ST18	2360806	         AC	                C	          0.047	-4.370e-1
GPD2	56051278	         AG	               G	          0.066	-3.710e-1
HOXB	9906289	        CC	                T	          0.083	-3.710e-1
AUTS2	1195218	        GG	                G	          0.095	-1.810e-1
LRP1B	34311235*	??	                T	          0.032	-1.810e-1
TSHZ1	10514168*	??	                C	         -0.047	-2.540e-1
LRP1B	17515225*	??	               T	          0.032	-2.265e-1
HOXD	2551802*	         ??	               G	           0.04	-2.265e-1
MCTP2	62018380*	??	               C	         0.047	-2.265e-1
UBE2E2	11129078*	??	               G	         0.057	-2.265e-1
CBLN4	6069325*	        ??	               T	         0.069	-2.265e-1









