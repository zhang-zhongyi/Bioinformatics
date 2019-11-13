##Lab 6##
##My name is Zhongyi Zhang.##

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Generate mpileup & run bcftools
How many variants are called in the final VCF?
How many variants are called with "PASS"?

less NA12891_CEU_sample_sorted_var.flt.vcf
/PASS
grep -v "^#" NA12891_CEU_sample_sorted_var.flt.vcf | grep "PASS" | wc -l
We have 699 variants are called with "PASS".

grep -v "^#" NA12891_CEU_sample_sorted_var.flt.vcf | wc -l
We have 756 variants are called in the final VCF.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Open BAM & VCF inIGV:

USH2A
chr1: 215796236-216596738
id = NM_206933
---------
Exon number: 64
Amino acid coding number: 4692
chr1: 215844314-215844635

T-location: chr1: 215,844,373

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

samtools mpileup with BED file
check the samtools man page to see what -B and -C50 mean for mpileup

For mpileup:
-B: Disable probabilistic realignment for the computation of base alignment quality (BAQ). BAQ is the Phred-scaled probability of a read base being misaligned. Applying this option greatly helps to reduce false SNPs caused by misalignments.

-C50: The bcftools filter command marks low quality sites and sites with the read depth exceeding a limit, which should be adjusted to about twice the average read depth (bigger read depths usually indicate problematic regions which are often enriched for artefacts). One may consider to add -C50 to mpileup if mapping quality is overestimated for reads containing excessive mismatches. Applying this option usually helps BWA-short but may not other mappers.
