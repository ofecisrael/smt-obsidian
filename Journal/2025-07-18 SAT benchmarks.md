```
/home/cs/israeloh/bin/submit-job.sh bin/ethos/ethos-2025-07-12 -t 60 -b 2025_07_18_qf_60s_sat_re-eval -o --include=/home/cs/israeloh/projects/cvc5/proofs/eo/cpc/Cpc.eo -d checks/2025-07-18-sat-str-in-re-eval/nfa
```

```sh
/home/cs/israeloh/bin/submit-job.sh bin/cvc5/cvc5-`today`-tag-regexp-str-in-re-eval -t 60 -d solutions/`today`-tag-regexp-str-in-re-eval/qf_s -b qf_s -o -t\ regexp-str-in-re-eval\ --dag-thresh=0

/home/cs/israeloh/bin/submit-job.sh bin/cvc5/cvc5-`today`-tag-regexp-str-in-re-eval -t 60 -d solutions/`today`-tag-regexp-str-in-re-eval/qf_slia -b qf_slia -o -t\ regexp-str-in-re-eval\ --dag-thresh=0
```

```
python scripts/sat/extract_str_in_re_eval.py solutions/`today`
[israeloh@skittles ~]$ python scripts/create_benchmark_set.py solutions/2025-07-22-tag-regexp-str-in-re-eval/ > benchmarks/benchmark_set_2025-07-22_sat_re_eval
```
