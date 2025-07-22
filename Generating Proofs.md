# Dataset
Note - snia is not needed to re-eval
set CVC5=cvc5-2025-04-29
```sh
submit-job.sh bin/cvc5/$CVC5 -t 60 -d proofs/qf_snia/60s/$CVC5 -b qf_snia -o "--dump-proofs --proof-granularity=dsl-rewrite"

submit-job.sh bin/cvc5/$CVC5 -t 60 -d proofs/qf_s/60s/$CVC5 -b qf_s -o "--dump-proofs --proof-granularity=dsl-rewrite"

submit-job.sh bin/cvc5/$CVC5 -t 60 -d proofs/qf_slia/60s/$CVC5 -b qf_slia -o "--dump-proofs --proof-granularity=dsl-rewrite"
```

```sh
python scripts/extract_proofs.py proofs/qf_s*/60s/$CVC5
```

```sh
python scripts/create_benchmark_set.py proofs/qf_s*/60s/$CVC5 > benchmarks/benchmark_set_qf_60s_${CVC5}_re-eval
```
