##Lab 4##
##My name is Zhongyi Zhang.##

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

hbb.fasta:

Query=
Length=147
                                                                                                                                       Score                   E
Sequences producing significant alignments:                                                                (Bits)                Value

P68871  Hemoglobin subunit beta OS=Homo sapiens OX=9606 GN=HBB PE...          301               4e-107
P02042  Hemoglobin subunit delta OS=Homo sapiens OX=9606 GN=HBD P...            284               1e-100
P02100  Hemoglobin subunit epsilon OS=Homo sapiens OX=9606 GN=HBE...           240                3e-83 
P69892  Hemoglobin subunit gamma-2 OS=Homo sapiens OX=9606 GN=HBG...       235               4e-81 
P69891  Hemoglobin subunit gamma-1 OS=Homo sapiens OX=9606 GN=HBG...       233               2e-80 
A0A2R8Y7X9  Uncharacterized protein OS=Homo sapiens OX=9606 PE=3 ...             220               5e-75 
P69905  Hemoglobin subunit alpha OS=Homo sapiens OX=9606 GN=HBA1 ...           114               1e-33 
P02008  Hemoglobin subunit zeta OS=Homo sapiens OX=9606 GN=HBZ PE...          100                6e-28 
P09105  Hemoglobin subunit theta-1 OS=Homo sapiens OX=9606 GN=HBQ...           97.1              1e-26 
Q6B0K9  Hemoglobin subunit mu OS=Homo sapiens OX=9606 GN=HBM PE=1...      88.6              2e-23 
Q8WWM9  Cytoglobin OS=Homo sapiens OX=9606 GN=CYGB PE=1 SV=1               72.8             1e-16 
Q9Y4B5  Microtubule cross-linking factor 1 OS=Homo sapiens OX=960...                    28.9               1.4   
P85298  Rho GTPase-activating protein 8 OS=Homo sapiens OX=9606 G...                27.7               2.5   
Q9Y5U5  Tumor necrosis factor receptor superfamily member 18 OS=H...                    26.2               8.4   
Q8IY21  Probable ATP-dependent RNA helicase DDX60 OS=Homo sapiens...             26.2               8.7   
Q9H1H9  Kinesin-like protein KIF13A OS=Homo sapiens OX=9606 GN=KI...               26.2               8.9   
Q5S007  Leucine-rich repeat serine/threonine-protein kinase 2 OS=...                          26.2               9.7   
Q9ULL5  Proline-rich protein 12 OS=Homo sapiens OX=9606 GN=PRR12 ...              26.2              10.0  


Unknown.fasta:

Query= 
Length=142
                                                                                                                                           Score                 E
Sequences producing significant alignments:                                                                    (Bits)             Value

P69905  Hemoglobin subunit alpha OS=Homo sapiens OX=9606 GN=HBA1 ...              286              1e-101
P09105  Hemoglobin subunit theta-1 OS=Homo sapiens OX=9606 GN=HBQ...              182              4e-60 
P02008  Hemoglobin subunit zeta OS=Homo sapiens OX=9606 GN=HBZ PE...             176              7e-58 
Q6B0K9  Hemoglobin subunit mu OS=Homo sapiens OX=9606 GN=HBM PE=1...         135              e-42 
P02042  Hemoglobin subunit delta OS=Homo sapiens OX=9606 GN=HBD P...              114              1e-33 
P68871  Hemoglobin subunit beta OS=Homo sapiens OX=9606 GN=HBB PE...            114              1e-33 
P69891  Hemoglobin subunit gamma-1 OS=Homo sapiens OX=9606 GN=HBG...         113               4e-33 
P69892  Hemoglobin subunit gamma-2 OS=Homo sapiens OX=9606 GN=HBG...         113               5e-33 
P02100  Hemoglobin subunit epsilon OS=Homo sapiens OX=9606 GN=HBE...             101               2e-28 
A0A2R8Y7X9  Uncharacterized protein OS=Homo sapiens OX=9606 PE=3 ...              101               4e-28 
Q8WWM9  Cytoglobin OS=Homo sapiens OX=9606 GN=CYGB PE=1 SV=1                68.9              2e-15 
P02144  Myoglobin OS=Homo sapiens OX=9606 GN=MB PE=1 SV=2                          51.2              6e-09 
Q6ZS30  Neurobeachin-like protein 1 OS=Homo sapiens OX=9606 GN=NB...              27.7                 2.5   
Q9P2P6  StAR-related lipid transfer protein 9 OS=Homo sapiens OX=...                       26.6                 6.2   
Q96RY7  Intraflagellar transport protein 140 homolog OS=Homo sapi...                        26.6                 6.7   
Q70CQ2  Ubiquitin carboxyl-terminal hydrolase 34 OS=Homo sapiens ...                      26.2                 8.3

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Lab3 starts here:

---What is the E-value for the top hit?  (record in README)
Ans: The E-value for the top hit of hbb.fasta is "4e-107".

---Assuming it’s human, run blastp with unknown.fasta as your query against the UniProt database.
Ans: The top hit in the Unknown.fasta is 
                                                                                                                                           Score                 E
                                                                                                                                           (Bits)              Value
P69905  Hemoglobin subunit alpha OS=Homo sapiens OX=9606 GN=HBA1 ...              286              1e-101

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
unknown2.fasta:

---BLAST shows mismatches

>P68871 Hemoglobin subunit beta OS=Homo sapiens OX=9606 GN=HBB PE=1 SV=2
Length=147

 Score = 298 bits (764),  Expect = 3e-106, Method: Compositional matrix adjust.
 Identities = 146/147 (99%), Positives = 146/147 (99%), Gaps = 0/147 (0%)

Query  1    MVHLTPVEKSAVTALWGKVNVDEVGGEALGRLLVVYPWTQRFFESFGDLSTPDAVMGNPK  60
                 MVHLTP EKSAVTALWGKVNVDEVGGEALGRLLVVYPWTQRFFESFGDLSTPDAVMGNPK
Sbjct  1     MVHLTPEEKSAVTALWGKVNVDEVGGEALGRLLVVYPWTQRFFESFGDLSTPDAVMGNPK  60

Query  61   VKAHGKKVLGAFSDGLAHLDNLKGTFATLSELHCDKLHVDPENFRLLGNVLVCVLAHHFG  120
                  VKAHGKKVLGAFSDGLAHLDNLKGTFATLSELHCDKLHVDPENFRLLGNVLVCVLAHHFG
Sbjct  61    VKAHGKKVLGAFSDGLAHLDNLKGTFATLSELHCDKLHVDPENFRLLGNVLVCVLAHHFG  120

Query  121  KEFTPPVQAAYQKVVAGVANALAHKYH  147
                    KEFTPPVQAAYQKVVAGVANALAHKYH
Sbjct  121    KEFTPPVQAAYQKVVAGVANALAHKYH  147

This is the first hit of my HSP alignment by the "unknown2.fasta".
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--- Look at the first hit in the HSP alignment.  Did it match all amino acids?  What is the base in the query and what is the base in the reference sequence?  Ignoring the first M in the sequence, what position is any potential mismatch?  

146/147 matches. That means there is only one mismatch between the query sequence and the reference sequence.

Ans:
The top hit E-value is 3e-106. The score (Bits) is 298.
It doesn't match the amino acids exactly. The middle line shows where they match or where a mismatch occurs.
Look at the first line (1-60) of these sequences, the seventh code is "V" for our query, but the seventh code for reference sequence is the "E". That is why the second line leaves the seventh code as a blank.

The base in the query sequence:
MVHLTPVEKSAVTALWGKVNVDEVGGEALGRLLVVYPWTQRFFESFGDLSTPDAVMGNPKVKAHGKKVLGAFSDGLAHLDNLKGTFATLSELHCDKLHVDPENFRLLGNVLVCVLAHHFGKEFTPPVQAAYQKVVAGVANALAHKYH 

The base in the reference sequence:
MVHLTPEEKSAVTALWGKVNVDEVGGEALGRLLVVYPWTQRFFESFGDLSTPDAVMGNPKVKAHGKKVLGAFSDGLAHLDNLKGTFATLSELHCDKLHVDPENFRLLGNVLVCVLAHHFGKEFTPPVQAAYQKVVAGVANALAHKYH 

 Ignoring the first M in the sequence, what position is any potential mismatch?
 Ignoring the first M, the potential mismatch is the sixth code. The sixth code for my query sequence is "V", but the sixth code for my reference sequence is "E".

Conclusion and Notes: 
We ignore the first M because every protein will have this "M". We are looking at the sequence for hemoglobin subunit in a patient with Sickle Cell Anemia. This patient's glutamic acid (E) has been substituted with a Valine (V) due to the misfolding of the protein

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Download andBLAST unknown_fragment.fasta
¤Look at the file by head to see if it’s protein/nucleotide and use appropriate search engine
¤Assume it’s human(9606)
¤What gene/protein is this from?  What is the E-value?

Ans:
This is the result I got by blastp the unknown_fragment.fasta with the data base P000005640_9606.fasta.

Query= 
Length=1126
                                                                                                                                            Score            E
Sequences producing significant alignments:                                                                     (Bits)          Value

P38398  Breast cancer type 1 susceptibility protein OS=Homo sapie...                             2307           0.0  
Q5T5X7  BEN domain-containing protein 3 OS=Homo sapiens OX=9606 G...                  33.5           0.75 
P35556  Fibrillin-2 OS=Homo sapiens OX=9606 GN=FBN2 PE=1 SV=3                           32.7           1.6  
Q8NBU5  ATPase family AAA domain-containing protein 1 OS=Homo sap...                    30.8             4.0  
Q02928  Cytochrome P450 4A11 OS=Homo sapiens OX=9606 GN=CYP4A11 P...          30.4             6.4  
Q7Z7A1  Centriolin OS=Homo sapiens OX=9606 GN=CNTRL PE=1 SV=2                       30.0            9.3  
P0CAP2  DNA-directed RNA polymerase II subunit GRINL1A OS=Homo sa...                  29.6            9.9 

By looking at the top hit, I would say it is protein instead of nucleotide.

It is breast cancer type 1 susceptibility protein. The E-value is 0.0 for this one.







