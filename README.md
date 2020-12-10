# PGC sumstats
by Lu Yi, 2020.11.24

## Instructions to run 01checkGWASsumstats.Rmd, 02sumstats2vcf.Rmd

### step1 checkGWASsumstats

INPUT:
1. original sumstats
2. hash file
3. reference files to check genome build and imputation

Parameters required: 
1. path of the sumstats directory, eg /Users/luyi/Downloads/pgc3_bip_summarystats
2. sumstats file name, eg daner_bip_pgc3_nm.gz.test.gz
3. hash file for the above sumstats, eg md5sum.chk
4. name of the pgc working group, eg BIP
5. year of the sumstats, eg 2019

#### Sample code to run in command line: 

Rscript -e "rmarkdown::render('01checkGWASsumstats.Rmd',params=list(arg1='/Users/luyi/Downloads/pgc3_bip_summarystats',arg2='daner_bip_pgc3_nm.gz.test.gz',arg3='md5sum.chk',arg4='BIP',arg5='2019'))"

Rscript -e "rmarkdown::render('01checkGWASsumstats.Rmd',params=list(arg1='/Users/luyi/Downloads/pgc3_bip_summarystats',arg2='daner_bip_pgc3_nm.gz',arg3='md5sum.chk',arg4='BIP',arg5='2019'))"

N.B. 
1) ~10mins to generate the report on the full sumstats file and output the fixed sumstats
2) the parameters provided as above will overide the default ones at the beginning of the Rmd file. 

#### View the sample html here: [01checkGWASsumstats](http://htmlpreview.github.io/?https://github.com/luyi0629/pgc-sumstats/blob/master/01checkGWASsumstats.html)

--- 

### step2 sumstats2vcf

INPUT:

1. cleand daner format sumstats
2. a special Excel file (2 worksheets)
3. reference file with chromosome sizes

Parameters required: 
1. path of the sumstats directory, eg /Users/luyi/Downloads/pgc3_bip_summarystats
2. cleaned sumstats file name, eg daner_bip_pgc3_nm.gz.test.gz.fixed.txt.gz
3. Excel file for GWAS info, eg pgc-bip2021-all-cases.xlsx
4. Excel sheet name with study info, eg metadata
5. Excel sheet name with cohort info, eg cohortData
6. path and filename for the chr sizes, eg /Users/luyi/Downloads/vcf.sumstats/00reference/chrom.sizes.tsv
7. output vcf file, eg 02sumstats2vcf/pgc-bip2021-test.vcf.tsv

#### Sample code to run in command line: 

Rscript -e "rmarkdown::render('02sumstats2vcf.Rmd',params=list(arg1='/Users/luyi/Downloads/pgc3_bip_summarystats',arg2='01sumstatsFixed/daner.test.txt.gz',arg3='pgc-bip2021-all-cases.xlsx',arg4='metaData',arg5='cohortData',arg6='/Users/luyi/Downloads/vcf.sumstats/00reference/chrom.sizes.tsv',arg7='02sumstats2vcf/pgc-bip2021-test.vcf.tsv'))"


#### View the sample html here: [02sumstats2vcf](http://htmlpreview.github.io/?https://github.com/luyi0629/pgc-sumstats/blob/master/02sumstats2vcf.html)

