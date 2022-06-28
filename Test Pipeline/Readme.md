Contains final code used for different tools. 

Abricate code

```
abricate "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/SaureusUSA300.fasta" --minid=80.0 --mincov=80.0 --db=resfinder > "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/abricate_results/output.tsv"
```

Hamronize Abricate

```
hamronize abricate "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/abricate_results/output.tsv" --format tsv --analysis_software_version 0.5 --reference_database_version 1 > "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/hamronize_results/hamr_abricate.tsv"
```

StarAMR code

```
staramr search "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/SaureusUSA300.fasta" --genome-size-lower-bound 4000000 --genome-size-upper-bound 6000000 --minimum-N50-value 10000 --minimum-contig-length 300 --unacceptable-number-contigs 1000  --pid-threshold 98.0 --percent-length-overlap-resfinder 60.0 --percent-length-overlap-plasmidfinder 60.0 --percent-length-overlap-pointfinder 95.0 --output-resfinder "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/staramr_results/outputstar.tsv" --output-detailed-summary "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/staramr_results/star_summ.tsv"
```

Hamronize StarAMR

```
hamronize staramr "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/staramr_results/outputstar.tsv" --format tsv --analysis_software_version 0.5 --reference_database_version 1 > "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/hamronize_results/hamr_staramr.tsv"
```

Hamronization of results

```
hamronize summarize "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/hamronize_results/hamr_abricate.tsv" "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/hamronize_results/hamr_staramr.tsv" -t json -o "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/hamronize_results/summarized1.json"
```

Activation of the python script for converting the .json file into the right format

```
python3 convertjson.py
```

AntiSMASH

```
antismash --cb-general "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/SaureusUSA300.fasta" --genefinding-tool prodigal --output-dir "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/antismash_results/antismash69" --sideload "/mnt/studentfiles/2022/2022MBI_07/Project/Benchmark/hamronize_results/summarizednew.json"
```

Server to view results

```
python3 -m http.server
```
