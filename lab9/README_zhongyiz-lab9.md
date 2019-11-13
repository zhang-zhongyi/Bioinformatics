###Lab 9###
##My name is Zhongyi Zhang.##

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

[student@msbi32400lab5 ~]$ sqlite3 practice.db
SQLite version 3.7.17 2013-05-20 00:56:22
Enter ".help" for instructions
Enter SQL statements terminated with a ";"
sqlite> CREATE TABLE variants(id integer primary key,chrom text,start integer,end integer,strand text,
   ...>
   ...> name text);
sqlite>
sqlite> .tables
variants
sqlite> .schema variants
CREATE TABLE variants(id integer primary key,chrom text,start integer,end integer, strand text,

name text);

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

sqlite> .schema variants
CREATE TABLE variants(id integer primary key,chrom text,start integer,end integer,strand text,

name text);
sqlite> INSERT INTO variants(id, chrom, start, end, strand, name) VALUES(NULL, "16", 48224287, 48224287, "+", "rs17822931");
sqlite> SELECT COUNT(*) FROM variants;
1
sqlite> SELECT * FROM variants;
1|16|48224287|48224287|+|rs17822931
sqlite> .quit
[student@msbi32400lab5 ~]$ sudo su postgres
[sudo] password for student: 
bash-4.2$ whoami
postgres
bash-4.2$ psql
could not change directory to "/home/student"
psql (9.2.24)
Type "help" for help.

postgres=# \l
                                  List of databases
   Name    |  Owner   | Encoding |   Collate   |    Ctype    |   Access privileges   
-----------+----------+----------+-------------+-------------+-----------------------
 oncokb    | student  | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 postgres  | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 template0 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
(4 rows)

postgres=# \h
Available help:
  ABORT                            CREATE FUNCTION                  DROP TABLE
  ALTER AGGREGATE                  CREATE GROUP                     DROP TABLESPACE
  ALTER COLLATION                  CREATE INDEX                     DROP TEXT SEARCH CONFIGURATION
  ALTER CONVERSION                 CREATE LANGUAGE                  DROP TEXT SEARCH DICTIONARY
  ALTER DATABASE                   CREATE OPERATOR                  DROP TEXT SEARCH PARSER
  ALTER DEFAULT PRIVILEGES         CREATE OPERATOR CLASS            DROP TEXT SEARCH TEMPLATE
  ALTER DOMAIN                     CREATE OPERATOR FAMILY           DROP TRIGGER
  ALTER EXTENSION                  CREATE ROLE                      DROP TYPE
  ALTER FOREIGN DATA WRAPPER       CREATE RULE                      DROP USER
  ALTER FOREIGN TABLE              CREATE SCHEMA                    DROP USER MAPPING
  ALTER FUNCTION                   CREATE SEQUENCE                  DROP VIEW
  ALTER GROUP                      CREATE SERVER                    END
  ALTER INDEX                      CREATE TABLE                     EXECUTE
  ALTER LANGUAGE                   CREATE TABLE AS                  EXPLAIN
  ALTER LARGE OBJECT               CREATE TABLESPACE                FETCH
  ALTER OPERATOR                   CREATE TEXT SEARCH CONFIGURATION GRANT
  ALTER OPERATOR CLASS             CREATE TEXT SEARCH DICTIONARY    INSERT
  ALTER OPERATOR FAMILY            CREATE TEXT SEARCH PARSER        LISTEN
  ALTER ROLE                       CREATE TEXT SEARCH TEMPLATE      LOAD
  ALTER SCHEMA                     CREATE TRIGGER                   LOCK
  ALTER SEQUENCE                   CREATE TYPE                      MOVE
  ALTER SERVER                     CREATE USER                      NOTIFY
  ALTER TABLE                      CREATE USER MAPPING              PREPARE
  ALTER TABLESPACE                 CREATE VIEW                      PREPARE TRANSACTION
  ALTER TEXT SEARCH CONFIGURATION  DEALLOCATE                       REASSIGN OWNED
  ALTER TEXT SEARCH DICTIONARY     DECLARE                          REINDEX
  ALTER TEXT SEARCH PARSER         DELETE                           RELEASE SAVEPOINT
  ALTER TEXT SEARCH TEMPLATE       DISCARD                          RESET
  ALTER TRIGGER                    DO                               REVOKE
  ALTER TYPE                       DROP AGGREGATE                   ROLLBACK
  ALTER USER                       DROP CAST                        ROLLBACK PREPARED
  ALTER USER MAPPING               DROP COLLATION                   ROLLBACK TO SAVEPOINT
  ALTER VIEW                       DROP CONVERSION                  SAVEPOINT
  ANALYZE                          DROP DATABASE                    SECURITY LABEL
  BEGIN                            DROP DOMAIN                      SELECT
  CHECKPOINT                       DROP EXTENSION                   SELECT INTO
  CLOSE                            DROP FOREIGN DATA WRAPPER        SET
  CLUSTER                          DROP FOREIGN TABLE               SET CONSTRAINTS
  COMMENT                          DROP FUNCTION                    SET ROLE
  COMMIT                           DROP GROUP                       SET SESSION AUTHORIZATION
  COMMIT PREPARED                  DROP INDEX                       SET TRANSACTION
  COPY                             DROP LANGUAGE                    SHOW
  CREATE AGGREGATE                 DROP OPERATOR                    START TRANSACTION
postgres=# \?
General
  \copyright             show PostgreSQL usage and distribution terms
  \g [FILE] or ;         execute query (and send results to file or |pipe)
  \h [NAME]              help on syntax of SQL commands, * for all commands
  \q                     quit psql

Query Buffer
  \e [FILE] [LINE]       edit the query buffer (or file) with external editor
  \ef [FUNCNAME [LINE]]  edit function definition with external editor
  \p                     show the contents of the query buffer
  \r                     reset (clear) the query buffer
  \s [FILE]              display history or save it to file
  \w FILE                write query buffer to file

Input/Output
  \copy ...              perform SQL COPY with data stream to the client host
  \echo [STRING]         write string to standard output
  \i FILE                execute commands from file
  \ir FILE               as \i, but relative to location of current script
  \o [FILE]              send all query results to file or |pipe
  \qecho [STRING]        write string to query output stream (see \o)

Informational
  (options: S = show system objects, + = additional detail)
  \d[S+]                 list tables, views, and sequences
  \d[S+]  NAME           describe table, view, sequence, or index
  \da[S]  [PATTERN]      list aggregates
  \db[+]  [PATTERN]      list tablespaces
  \dc[S+] [PATTERN]      list conversions
  \dC[+]  [PATTERN]      list casts
  \dd[S]  [PATTERN]      show object descriptions not displayed elsewhere
  \ddp    [PATTERN]      list default privileges
  \dD[S+] [PATTERN]      list domains
  \det[+] [PATTERN]      list foreign tables
  \des[+] [PATTERN]      list foreign servers
  \deu[+] [PATTERN]      list user mappings
  \dew[+] [PATTERN]      list foreign-data wrappers
  \df[antw][S+] [PATRN]  list [only agg/normal/trigger/window] functions
  \dF[+]  [PATTERN]      list text search configurations
  \dFd[+] [PATTERN]      list text search dictionaries
  \dFp[+] [PATTERN]      list text search parsers
  \dFt[+] [PATTERN]      list text search templates
  \dg[+]  [PATTERN]      list roles
  \di[S+] [PATTERN]      list indexes
  \dl                    list large objects, same as \lo_list
  \dL[S+] [PATTERN]      list procedural languages
  \dn[S+] [PATTERN]      list schemas
  \do[S]  [PATTERN]      list operators
  \dO[S+] [PATTERN]      list collations
  \dp     [PATTERN]      list table, view, and sequence access privileges
  \drds [PATRN1 [PATRN2]] list per-database role settings
  \ds[S+] [PATTERN]      list sequences
  \dt[S+] [PATTERN]      list tables
  \dT[S+] [PATTERN]      list data types
  \du[+]  [PATTERN]      list roles
  \dv[S+] [PATTERN]      list views
  \dE[S+] [PATTERN]      list foreign tables
  \dx[+]  [PATTERN]      list extensions
  \l[+]                  list all databases
  \sf[+] FUNCNAME        show a function's definition
  \z      [PATTERN]      same as \dp

Formatting
  \a                     toggle between unaligned and aligned output mode
  \C [STRING]            set table title, or unset if none
  \f [STRING]            show or set field separator for unaligned query output
  \H                     toggle HTML output mode (currently off)
  \pset NAME [VALUE]     set table output option
                         (NAME := {format|border|expanded|fieldsep|fieldsep_zero|footer|null|
                         numericlocale|recordsep|recordsep_zero|tuples_only|title|tableattr|pager})
  \t [on|off]            show only rows (currently off)
  \T [STRING]            set HTML <table> tag attributes, or unset if none
  \x [on|off|auto]       toggle expanded output (currently off)

Connection
  \c[onnect] {[DBNAME|- USER|- HOST|- PORT|-] | conninfo}
                         connect to new database (currently "postgres")
  \encoding [ENCODING]   show or set client encoding
  \password [USERNAME]   securely change the password for a user
  \conninfo              display information about current connection

Operating System
  \cd [DIR]              change the current working directory
  \setenv NAME [VALUE]   set or unset environment variable
  \timing [on|off]       toggle timing of commands (currently off)
  \! [COMMAND]           execute command in shell or start interactive shell

Variables
  \prompt [TEXT] NAME    prompt user to set internal variable
  \set [NAME [VALUE]]    set internal variable, or list all if no parameters
  \unset NAME            unset (delete) internal variable

Large Objects
  \lo_export LOBOID FILE
  \lo_import FILE [COMMENT]
  \lo_list
postgres=# \password
Enter new password: 
Enter it again: 
postgres=# \q
bash-4.2$ whoami
postgres
bash-4.2$ exit
exit
[student@msbi32400lab5 ~]$ whoami
student
[student@msbi32400lab5 ~]$ 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

sudo yum install pgadmin3
and then we type in the password.

Transaction Summary
=========================================================================================================================
Install  1 Package (+3 Dependent packages)

Total download size: 8.5 M
Installed size: 29 M
Is this ok [y/d/N]: y
Downloading packages:
(1/4): SDL-1.2.15-14.el7.x86_64.rpm                                                               | 204 kB  00:00:00     
(2/4): pgadmin3-1.22.1-1.el7.x86_64.rpm                                                           | 4.8 MB  00:00:01     
(3/4): wxBase-2.8.12-20.el7.x86_64.rpm                                                            | 588 kB  00:00:00     
(4/4): wxGTK-2.8.12-20.el7.x86_64.rpm                                                             | 2.9 MB  00:00:01     
-------------------------------------------------------------------------------------------------------------------------
Total                                                                                    2.4 MB/s | 8.5 MB  00:00:03     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : wxBase-2.8.12-20.el7.x86_64                                                                           1/4 
  Installing : SDL-1.2.15-14.el7.x86_64                                                                              2/4 
  Installing : wxGTK-2.8.12-20.el7.x86_64                                                                            3/4 
  Installing : pgadmin3-1.22.1-1.el7.x86_64                                                                          4/4 
  Verifying  : SDL-1.2.15-14.el7.x86_64                                                                              1/4 
  Verifying  : pgadmin3-1.22.1-1.el7.x86_64                                                                          2/4 
  Verifying  : wxBase-2.8.12-20.el7.x86_64                                                                           3/4 
  Verifying  : wxGTK-2.8.12-20.el7.x86_64                                                                            4/4 

Installed:
  pgadmin3.x86_64 0:1.22.1-1.el7                                                                                         

Dependency Installed:
  SDL.x86_64 0:1.2.15-14.el7            wxBase.x86_64 0:2.8.12-20.el7            wxGTK.x86_64 0:2.8.12-20.el7           

Complete!


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

[student@msbi32400lab5 data]$ ls *.dump
oncokb.dump


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

[student@msbi32400lab5 ~]$ ls *.dump
oncokb.dump
[student@msbi32400lab5 ~]$ dropdb oncokb
dropdb: database removal failed: ERROR:  database "oncokb" is being accessed by other users
DETAIL:  There is 1 other session using the database.
[student@msbi32400lab5 ~]$ dropdb oncokb
[student@msbi32400lab5 ~]$ psql oncokb
psql: FATAL:  database "oncokb" does not exist
[student@msbi32400lab5 ~]$ createdb oncokb
[student@msbi32400lab5 ~]$ psql oncokb
psql (9.2.24)
Type "help" for help.

oncokb=# \d
No relations found.
oncokb=# \q

[student@msbi32400lab5 ~]$ less oncokb.dump

--
-- PostgreSQL database dump
--

SET statement_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = off;
SET check_function_bodies = false;
SET client_min_messages = warning;
SET escape_string_warning = off;

SET search_path = public, pg_catalog;

SET default_tablespace = '';

SET default_with_oids = false;

--
-- Name: alteration; Type: TABLE; Schema: public; Owner: student; Tablespace: 
--

CREATE TABLE alteration (
    id integer NOT NULL,
    uuid character varying(80) DEFAULT NULL::character varying,
    entrez_gene_id integer NOT NULL,
    alteration text NOT NULL,
    name text NOT NULL,
    alteration_type character varying(510) DEFAULT NULL::character varying,
    consequence character varying(200) DEFAULT NULL::character varying,
    ref_residues character varying(510) DEFAULT NULL::character varying,
    protein_start integer,
    protein_end integer,
    variant_residues character varying(510) DEFAULT NULL::character varying
);

[student@msbi32400lab5 ~]$ wc -l oncokb.dump 
195413 oncokb.dump
[student@msbi32400lab5 ~]$ psql oncokb < oncokb.dump
SET
SET
SET
SET
SET
SET
SET
SET
SET
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
CREATE TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
ALTER TABLE
REVOKE
REVOKE
GRANT
GRANT

oncokb=# \d
                     List of relations
 Schema |              Name              | Type  |  Owner  
--------+--------------------------------+-------+---------
 public | alteration                     | table | student
 public | article                        | table | student
 public | clinical_trial                 | table | student
 public | clinical_trial_country         | table | student
 public | clinical_trial_drug            | table | student
 public | drug                           | table | student
 public | drug_synonym                   | table | student
 public | evidence                       | table | student
 public | evidence_alteration            | table | student
 public | evidence_article               | table | student
 public | evidence_clinical_trial        | table | student
 public | evidence_nccn_guideline        | table | student
 public | gene                           | table | student
 public | gene_alias                     | table | student
 public | nccn_guideline                 | table | student
 public | portalAlt_oncoKBAlt            | table | student
 public | portal_alteration              | table | student
 public | treatment                      | table | student
 public | treatment_approved_indications | table | student
 public | treatment_drug                 | table | student
 public | variant_consequence            | table | student
(21 rows)

oncokb=# SELECT COUNT(*) FROM alteration ;
 count 
-------
 13347
(1 row)

oncokb=# \q




---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

[student@msbi32400lab5 ~]$ psql oncokb
psql (9.2.24)
Type "help" for help.

oncokb=# SELECT id, uuid, entrez_gene_id, alteration, name, alteration_type, consequence, ref_residues, protein_start, protein_end, variant_residues FROM alteration WHERE entrez_gene_id = 3845;
  id  | uuid | entrez_gene_id |     alteration      |        name         | alteration_type |      consequence      | ref
_residues | protein_start | protein_end | variant_residues 
------+------+----------------+---------------------+---------------------+-----------------+-----------------------+----
----------+---------------+-------------+------------------
 1855 |      |           3845 | Wildtype            | Wildtype            | MUTATION        | NA                    |    
          |            -1 |      100000 | 
 1856 |      |           3845 | K5N                 | K5N                 | MUTATION        | missense_variant      | K  
          |             5 |           5 | N
 1857 |      |           3845 | G10dup              | G10dup              | MUTATION        | inframe_insertion     | G  
          |            10 |          10 | 
 1858 |      |           3845 | G12A                | G12A                | MUTATION        | missense_variant      | G  
          |            12 |          12 | A
 1859 |      |           3845 | G12C                | G12C                | MUTATION        | missense_variant      | G  
          |            12 |          12 | C
 1860 |      |           3845 | G12D                | G12D                | MUTATION        | missense_variant      | G  
          |            12 |          12 | D
 1861 |      |           3845 | G12F                | G12F                | MUTATION        | missense_variant      | G  
          |            12 |          12 | F
 1862 |      |           3845 | G12R                | G12R                | MUTATION        | missense_variant      | G  
          |            12 |          12 | R
 1863 |      |           3845 | G12S                | G12S                | MUTATION        | missense_variant      | G  
          |            12 |          12 | S
 1864 |      |           3845 | G12V                | G12V                | MUTATION        | missense_variant      | G  
          |            12 |          12 | V
 1865 |      |           3845 | G13C                | G13C                | MUTATION        | missense_variant      | G  
          |            13 |          13 | C
 1866 |      |           3845 | G13D                | G13D                | MUTATION        | missense_variant      | G  
          |            13 |          13 | D
 1867 |      |           3845 | G13E                | G13E                | MUTATION        | missense_variant      | G  
          |            13 |          13 | E
 1868 |      |           3845 | V14I                | V14I                | MUTATION        | missense_variant      | V  
          |            14 |          14 | I
 1869 |      |           3845 | L19F                | L19F                | MUTATION        | missense_variant      | L  
          |            19 |          19 | F

...(Press ENTER Key all way to the end)

 2005 |      |           3845 | P110L               | P110L               | MUTATION        | missense_variant      | P  
          |           110 |         110 | L
 2006 |      |           3845 | P110S               | P110S               | MUTATION        | missense_variant      | P  
          |           110 |         110 | S
 2007 |      |           3845 | M111Rfs*3           | M111Rfs*3           | MUTATION        | frameshift_variant    | M  
          |           111 |         111 | 
 2008 |      |           3845 | R123*               | R123*               | MUTATION        | stop_gained           | R  
          |           123 |         123 | *
 2009 |      |           3845 | R135T               | R135T               | MUTATION        | missense_variant      | R  
          |           135 |         135 | T
 2010 |      |           3845 | P140S               | P140S               | MUTATION        | missense_variant      | P  
          |           140 |         140 | S
 2011 |      |           3845 | T158A               | T158A               | MUTATION        | missense_variant      | T  
          |           158 |         158 | A
 2012 |      |           3845 | R161G               | R161G               | MUTATION        | missense_variant      | R  
          |           161 |         161 | G
 2013 |      |           3845 | R167T               | R167T               | MUTATION        | missense_variant      | R  
          |           167 |         167 | T
 2014 |      |           3845 | K170Q               | K170Q               | MUTATION        | missense_variant      | K  
          |           170 |         170 | Q
 2015 |      |           3845 | K176Q               | K176Q               | MUTATION        | missense_variant      | K  
          |           176 |         176 | Q
 2016 |      |           3845 | I187V               | I187V               | MUTATION        | missense_variant      | I  
          |           187 |         187 | V
 2017 |      |           3845 | I36L                | I36L                | MUTATION        | missense_variant      | I  
          |            36 |          36 | L
 2018 |      |           3845 | T50_E63dup          | T50_E63dup          | MUTATION        | inframe_insertion     |    
          |            50 |          63 | 
 2019 |      |           3845 | R68M                | R68M                | MUTATION        | missense_variant      | R  
          |            68 |          68 | M
 2020 |      |           3845 | D92Y                | D92Y                | MUTATION        | missense_variant      | D  
          |            92 |          92 | Y
(166 rows)

I got 166 rows in total!

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

[student@msbi32400lab5 ~]$ mysql --user=genome --host=genome-mysql.cse.ucsc.edu -A -e "select chrom, size from hg19.chromInfo" > hg19.genome
[student@msbi32400lab5 ~]$ ls -ltr
-rw-rw-r--.  1 student student      1982 Mar 20 01:22 hg19.genome

[student@msbi32400lab5 ~]$ less hg19.genome
chrom   size
chr1    249250621
chr2    243199373
chr3    198022430
chr4    191154276
chr5    180915260
chr6    171115067
chr7    159138663
chrX    155270560
chr8    146364022
chr9    141213431
chr10   135534747
chr11   135006516
chr12   133851895
chr13   115169878
chr14   107349540
chr15   102531392
chr16   90354753
chr17   81195210
chr18   78077248
chr20   63025520
chrY    59373566
chr19   59128983
chr22   51304566
chr21   48129895
chr6_ssto_hap7  4928567
chr6_mcf_hap5   4833398
chr6_cox_hap2   4795371
chr6_mann_hap4  4683263
chr6_apd_hap1   4622290
chr6_qbl_hap6   4611984
chr6_dbb_hap3   4610396
chr17_ctg5_hap1 1680828
chr4_ctg9_hap1  590426
chr1_gl000192_random    547496
chrUn_gl000225  211173
chr4_gl000194_random    191469
chr4_gl000193_random    189789
chr9_gl000200_random    187035
chrUn_gl000222  186861
chrUn_gl000212  186858
chr7_gl000195_random    182896
chrUn_gl000223  180455
chrUn_gl000224  179693
chrUn_gl000219  179198
chr17_gl000205_random   174588
chrUn_gl000215  172545
chrUn_gl000216  172294
chrUn_gl000217  172149
chr9_gl000199_random    169874
chrUn_gl000211  166566
chrUn_gl000213  164239
chrUn_gl000220  161802
chrUn_gl000218  161147
chr19_gl000209_random   159169
chrUn_gl000221  155397
chrUn_gl000214  137718
chrUn_gl000228  129120
chrUn_gl000227  128374
chr1_gl000191_random    106433
chr19_gl000208_random   92689
chr9_gl000198_random    90085
chr17_gl000204_random   81310
chrUn_gl000233  45941
chrUn_gl000237  45867
chrUn_gl000230  43691
chrUn_gl000242  43523
chrUn_gl000243  43341
chrUn_gl000241  42152
chrUn_gl000236  41934
chrUn_gl000240  41933
chr17_gl000206_random   41001
chrUn_gl000232  40652
chrUn_gl000234  40531
chr11_gl000202_random   40103
chrUn_gl000238  39939
chrUn_gl000244  39929
chrUn_gl000248  39786
chr8_gl000196_random    38914
chrUn_gl000249  38502
chrUn_gl000246  38154
chr17_gl000203_random   37498
chr8_gl000197_random    37175
chrUn_gl000245  36651
chrUn_gl000247  36422
chr9_gl000201_random    36148
chrUn_gl000235  34474
chrUn_gl000239  33824
chr21_gl000210_random   27682
chrUn_gl000231  27386
chrUn_gl000229  19913
chrM    16571
chrUn_gl000226  15008
chr18_gl000207_random   4262
(END)

I got 94 rows in total!

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[student@msbi32400lab5 ~]$ createdb lab9db
[student@msbi32400lab5 ~]$ ls /media/sf_Desktop/*.sql
/media/sf_Desktop/create_variants.sql
[student@msbi32400lab5 ~]$ cp /media/sf_Desktop/create_variants.sql
cp: missing destination file operand after ‘/media/sf_Desktop/create_variants.sql’
Try 'cp --help' for more information.
[student@msbi32400lab5 ~]$ cp /media/sf_Desktop/create_variants.sql .
[student@msbi32400lab5 ~]$ less create_variants.sql 

--Create variants table for importing data from snpEff/clinvar annotated VCFs
CREATE TABLE variants (
chr text NULL,
pos INT NULL,
ref text NULL,
alt text NULL,
snp_id text NULL,
ann_allele text NULL,
ann_effect text NULL,
ann_impact text NULL,
ann_gene text NULL,
ann_feature text NULL,
ann_featureid text NULL,
ann_biotype text NULL,
ann_rank text NULL,
ann_hgvs_c text NULL,
ann_hgvs_p text NULL,
ann_cdna_pos text NULL,
ann_cdna_len text NULL,
ann_aa_len text NULL,
ann_distance text NULL,
lof_gene text NULL,
lof_numtr text NULL,
lof_perc text NULL,
clnrevstat text NULL,
rs text NULL,
clndninclorigin text NULL,
origin text NULL,
mc text NULL,
clndn text NULL,
clnvc text NULL,
clnvi text NULL,
af_exac text NULL,
af_esp text NULL,


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------


[student@msbi32400lab5 ~]$ java -Xmx2G -jar /data/snpEff/SnpSift.jar extractFields -s ',' -e '.' /data/lab7/results/hgvs_test_cases_snpEff.clinvar.vcf CHROM POS REF ALT ID "ANN[*].ALLELE" "ANN[*].EFFECT" "ANN[*].IMPACT" "ANN[*].GENE" "ANN[*].FEATURE" "ANN[*].FEATUREID" "ANN[*].BIOTYPE" "ANN[*].RANK" "ANN[*].HGVS_C" "ANN[*].HGVS_P" "ANN[*].CDNA_POS" "ANN[*].CDNA_LEN" "ANN[*].AA_LEN" "ANN[*].DISTANCE" "LOF[*].GENE" "LOF[*].NUMTR" "LOF[*].PERC" CLNREVSTAT RS CLNDNINCL ORIGIN MC CLNDN CLNVC CLNVI AF_EXAC AF_ESP CLNSIG CLNSIGINCL CLNDISDB GENEINFO CLNDISDBINCL AF_TGP CLNHGVS SSR > /data/lab7/results/hgvs_test_cases_snpEff.clinvar.Extracted

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

[student@msbi32400lab5 ~]$ psql lab9db < create_variants.sql 
CREATE TABLE
[student@msbi32400lab5 ~]$ psql lab9db
psql (9.2.24)
Type "help" for help.

lab9db=# \d
          List of relations
 Schema |   Name   | Type  |  Owner  
--------+----------+-------+---------
 public | variants | table | student
(1 row)

lab9db=# \d variants
        Table "public.variants"
     Column      |  Type   | Modifiers 
-----------------+---------+-----------
 chr             | text    | 
 pos             | integer | 
 ref             | text    | 
 alt             | text    | 
 snp_id          | text    | 
 ann_allele      | text    | 
 ann_effect      | text    | 
 ann_impact      | text    | 
 ann_gene        | text    | 
 ann_feature     | text    | 
 ann_featureid   | text    | 
 ann_biotype     | text    | 
 ann_rank        | text    | 
 ann_hgvs_c      | text    | 
 ann_hgvs_p      | text    | 
 ann_cdna_pos    | text    | 
 ann_cdna_len    | text    | 
 ann_aa_len      | text    | 
 ann_distance    | text    | 
 lof_gene        | text    | 
 lof_numtr       | text    | 
 lof_perc        | text    | 
 clnrevstat      | text    | 
 rs              | text    | 
 clndninclorigin | text    | 
 origin          | text    | 
 mc              | text    | 
 clndn           | text    | 
 clnvc           | text    | 
 clnvi           | text    | 
 af_exac         | text    | 
 af_esp          | text    | 
 clnsig          | text    | 
 clnsigincl      | text    | 
 clndisdb        | text    | 
 geneinfo        | text    | 
 clndisdbincl    | text    | 
 af_tgp          | text    | 
 clinhgvs        | text    | 
 ssr             | text    | 

[student@msbi32400lab5 data]$ vi hgvs_test_cases_snpEff.clinvar.Extracted 
CHROM   POS     REF     ALT     ID      ANN[*].ALLELE   ANN[*].EFFECT   ANN[*].IMPACT   ANN[*].GENE     ANN[*].FEATURE  ANN[*].FEATUREID        ANN[*].BIOTYPE  ANN[*].RANK     ANN[*].HGVS_C   ANN[*].HGVS_P   ANN[*].CDNA_POS ANN[*].CDNA_LEN ANN[*].AA_LEN   ANN[*].DISTANCE LOF[*].GENE     LOF[*].NUMTR    LOF[*].PERC     CLNREVSTAT      RS      CLNDNINCL       ORIGIN  MC      CLNDN   CLNVC   CLNVI   AF_EXAC AF_ESP  CLNSIG  CLNSIGINCL      CLNDISDB        GENEINFO        CLNDISDBINCL    AF_TGP  CLNHGVS SSR
1       5935162 A       T       PTV001;167375   T       splice_acceptor_variant&intron_variant  HIGH    NPHP4   transcript      NM_015102.4     protein_coding  20      c.2818-2T>A     .       -1      -1      -1      0       NPHP4   1       1.0     criteria_provided,_single_submitter     1287637 .       1       SO:0001574|splice_acceptor_variant      not_specified   single_nucleotide_variant       HGMD:CS057899   .       .       Benign  .       MedGen:CN169374 NPHP4:261734    .       .       NC_000001.10:g.5935162A>T       .
1       12065948        C       T       PTV002  T       missense_variant        MODERATE        MFN2    transcript      NM_001127660.1  protein_coding  14      c.1676C>T       p.Pro559Leu     1984    4532    757     0       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .
1       46655121        GTCAC   G       PTV003;56594    G,G     downstream_gene_variant,intron_variant  MODIFIER,MODIFIER       TSPAN1,POMGNT1  transcript,transcript   NM_005727.3,NM_001243766.1      protein_coding,protein_coding   -1,21   c.*3917_*3920delTCAC,c.1869+31_1869+34delGTGA   .,.     -1,-1   -1,-1   -1,-1   3488,0  .       .       .       no_assertion_criteria_provided  386834023       .       .       SO:0001575|splice_donor_variant,SO:0001627|intron_variant       Muscle_eye_brain_disease        Deletion        .       .       .       Likely_pathogenic       .       MedGen:C0457133,OMIM:253280,Orphanet:ORPHA588,SNOMED_CT:277950001       TSPAN1:10103|POMGNT1:55624      .       .       NC_000001.10:g.46655126_46655129delTCAC .
1       68912523        TGAGCCAGAG      T       PTV004;98822    T       conservative_inframe_deletion   MODERATE        RPE65   transcript      NM_000329.2     protein_coding  3       c.106_114delCTCTGGCTC   p.Leu36_Leu38del        168     2608    533     0       .       .       .       no_assertion_provided   61751280        .       .       .       not_provided    Deletion        .       .       .       not_provided    .       MedGen:CN517202 RPE65:6121      .       .       NC_000001.10:g.68912524_68912532delGAGCCAGAG    .
1       68912523        TGAGCCA T       PTV005  T       conservative_inframe_deletion   MODERATE        RPE65   transcript      NM_000329.2     protein_coding  3       c.109_114delTGGCTC      p.Trp37_Leu38del        168     2608    533     0       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .       .
@                                                                                                                        @                                                                                                                        @                                                                                                                        @                                                                                                                        
"hgvs_test_cases_snpEff.clinvar.Extracted" 126L, 104464C                                               1,1           Top

Then I use "dd" command to remove the headers. I use "ESCAPE:wq ENTER" keys to quit the vi.

[student@msbi32400lab5 data]$ psql lab9db
psql (9.2.24)
Type "help" for help.

lab9db=# \copy variants FROM 'hgvs_test_cases_snpEff.clinvar.Extracted' WITH DELIMITER E'\t'
lab9db=# SELECT COUNT(*) FROM variants;
 count 
-------
   125
(1 row)

lab9db=# \d variants
        Table "public.variants"
     Column      |  Type   | Modifiers 
-----------------+---------+-----------
 chr             | text    | 
 pos             | integer | 
 ref             | text    | 
 alt             | text    | 
 snp_id          | text    | 
 ann_allele      | text    | 
 ann_effect      | text    | 
 ann_impact      | text    | 
 ann_gene        | text    | 
 ann_feature     | text    | 
 ann_featureid   | text    | 
 ann_biotype     | text    | 
 ann_rank        | text    | 
 ann_hgvs_c      | text    | 
 ann_hgvs_p      | text    | 
 ann_cdna_pos    | text    | 
 ann_cdna_len    | text    | 
 ann_aa_len      | text    | 
 ann_distance    | text    | 
 lof_gene        | text    | 
 lof_numtr       | text    | 
 lof_perc        | text    | 
 clnrevstat      | text    | 
 rs              | text    | 
 clndninclorigin | text    | 
 origin          | text    | 
 mc              | text    | 
 clndn           | text    | 
 clnvc           | text    | 
 clnvi           | text    | 
 af_exac         | text    | 
 af_esp          | text    | 
 clnsig          | text    | 
 clnsigincl      | text    | 
 clndisdb        | text    | 
 geneinfo        | text    | 
 clndisdbincl    | text    | 
 af_tgp          | text    | 
 clinhgvs        | text    | 
 ssr             | text    | 

lab9db=# SELECT chr, pos, ref, alt FROM variants LIMIT 10;
 chr |    pos    |           ref            | alt  
-----+-----------+--------------------------+------
 1   |   5935162 | A                        | T
 1   |  12065948 | C                        | T
 1   |  46655121 | GTCAC                    | G
 1   |  68912523 | TGAGCCAGAG               | T
 1   |  68912523 | TGAGCCA                  | T
 1   | 109817590 | G                        | T
 1   | 145597475 | GAAGT                    | G
 1   | 153791300 | CTG                      | C
 1   | 156104667 | TGAGAGCCGGCTGGCGGATGCGCT | CCCC
 1   | 156108540 | C                        | CG
(10 rows)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------


lab9db=# SELECT chr, pos, snp_id, rs, af_exac, ann_gene, ann_effect, ann_impact, ann_feature, ann_hgvs_c, ann_hgvs_p FROM variants WHERE clnsig LIKE '%athogenic' AND ann_gene = 'BRCA1';
 chr |   pos    |    snp_id    |    rs     | af_exac | ann_gene |     ann_effect      | ann_impact | ann_feature |     an
n_hgvs_c     | ann_hgvs_p 
-----+----------+--------------+-----------+---------+----------+---------------------+------------+-------------+-------
-------------+------------
 17  | 41197588 | PTV056;96891 | 431825382 | .       | BRCA1    | 3_prime_UTR_variant | MODIFIER   | transcript  | c.*103
_*106delTGTC | .
(1 row)

lab9db=# SELECT chr, pos, rs, ann_gene, ann_effect, ann_impact, ann_feature, ann_hgvs_c, ann_hgvs_p FROM variants WHERE clnsig LIKE '%athogenic' AND ann_gene = 'BRCA1';
 chr |   pos    |    rs     | ann_gene |     ann_effect      | ann_impact | ann_feature |     ann_hgvs_c     | ann_hgvs_p
 
-----+----------+-----------+----------+---------------------+------------+-------------+--------------------+-----------
-
 17  | 41197588 | 431825382 | BRCA1    | 3_prime_UTR_variant | MODIFIER   | transcript  | c.*103_*106delTGTC | .
(1 row)

[student@msbi32400lab5 data]$ ls ~/.psql_history 
/home/student/.psql_history
[student@msbi32400lab5 data]$ vi ~/.psql_history
\q
\d
\q
\d
\q
\d
SELECT COUNT(*) FROM alteration ;
\q
SELECT id, uuid, entrez_gene_id, alteration, name, alteration_type, consequence, ref_residues, protein_start, protein_end, variant_residues FROM alteration WHERE entrez_gene_id = 3845;
\q
\d
\d variants
\q
\copy variants FROM 'hgvs_test_cases_snpEff.clinvar.Extracted' WITH DELIMITER E'\t'
\q
\copy variants FROM 'hgvs_test_cases_snpEff.clinvar.Extracted' WITH DELIMITER E'\t'
SELECT COUNT(*) FROM variants;
\i create_variants.sql
\copy variants FROM "hgvs_test_cases_snpEff.clinvar.Extracted" WITH DELIMITER E'\t'
\q
\i create_variants.sql
\copy variants FROM 'hgvs_test_cases_snpEff.clinvar.Extracted' WITH DELIMITER E'\t'
\q
\copy variants FROM 'hgvs_test_cases_snpEff.clinvar.Extracted' WITH DELIMITER E'\t'
SELECT COUNT(*) FROM variants;
\d variants
SELECT chr, pos, ref, alt FROM variants LIMIT 10;
SELECT chr, pos, snp_id, rs, af_exac, ann_gene, ann_effect, ann_impact, ann_feature, ann_hgvs_c, ann_hgvs_p FROM variants WHERE clnsig LIKE '%athogenic' AND ann_gene = 'BRCA1';
SELECT chr, pos, rs, ann_gene, ann_effect, ann_impact, ann_feature, ann_hgvs_c, ann_hgvs_p FROM variants WHERE clnsig LIKE '%athogenic' AND ann_gene = 'BRCA1';
\q
~ 


[student@msbi32400lab5 data]$ psql lab9db
psql (9.2.24)
Type "help" for help.

lab9db=# SELECT COUNT(*) FROM variants WHERE clnsig LIKE '%athogenic%';
 count 
-------
    29
(1 row)

lab9db=# SELECT COUNT(*) FROM variants WHERE clnsig LIKE 'Pathogenic%';
 count 
-------
    18
(1 row)

lab9db=# SELECT clnsig FROM variants WHERE clnsig LIKE 'Pathogenic%';
            clnsig            
------------------------------
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic/Likely_pathogenic
 Pathogenic/Likely_pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
(18 rows)

lab9db=# SELECT clnsig FROM variants WHERE clnsig LIKE '%athogenic%';
                    clnsig                    
----------------------------------------------
 Likely_pathogenic
 Pathogenic
 Conflicting_interpretations_of_pathogenicity
 Pathogenic
 Pathogenic
 Pathogenic
 Conflicting_interpretations_of_pathogenicity
 Pathogenic
 Conflicting_interpretations_of_pathogenicity
 Pathogenic
 Pathogenic
 Conflicting_interpretations_of_pathogenicity
 Pathogenic/Likely_pathogenic
 Conflicting_interpretations_of_pathogenicity
 Conflicting_interpretations_of_pathogenicity
 Pathogenic/Likely_pathogenic
 Likely_pathogenic
 Conflicting_interpretations_of_pathogenicity
 Pathogenic
 Likely_pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Likely_pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
 Pathogenic
(29 rows)
















