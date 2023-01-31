# snp_rsID_chr-bp
convert from CHR:POS to RSID in batch using ANNOVAR 



https://zhuanlan.zhihu.com/p/389602337  
### 0) download ANNOVAR and annotation database <br>
https://annovar.openbioinformatics.org/en/latest/user-guide/download/ <br>
```perl annotate_variation.pl -downdb -webfrom annovar -buildver hg19 avsnp150 humandb/```

### 1) from RSID to chr:pos<br>
``` perl convert2annovar.pl -format rsid example/snplist.txt -dbsnpfile humandb/hg19_snp138.txt > snplist.avinput``` <br>
### 2) from chr:pos to RSID<br> 
``` perl annotate_variation.pl ex1.avinput humandb/ -filter -build hg19 -dbtype avsnp150``` <br>
the result will be stored in **ex1.avinput.hg19_avsnp150_dropped (matched)** and **ex1.avinput.hg19_avsnp150_filtered (not matched)** <br>
 Output file with variants matching filtering criteria is written to **ex1.avinput.hg19_avsnp150_dropped **, and output file with other variants is written to **ex1.avinput.hg19_avsnp150_filtered**
 
