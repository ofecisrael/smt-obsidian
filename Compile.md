Compile CVC5
```sh
./configure.sh <debug> --auto-download
    # use --prefix to specify an install prefix (default: /usr/local)
    # use --name=<PATH> for custom build directory
    # use --auto-download to download and build missing, required or
    #   enabled, dependencies
cd <build_dir>   # default is ./build
make             # use -jN for parallel build with N threads
make check       # to run default set of tests
make install     # to install into the prefix specified above
```
or take from here: https://github.com/cvc5/cvc5/releases

# Dataset
Note - snia is not needed to re-eval
```sh
submit-job.sh bin/cvc5/cvc5-2025-04-29 -t 60 -d proofs/qf_snia/60s/cvc5-2025-04-29 -b qf_snia -o "--dump-proofs --proof-granularity=dsl-rewrite"

submit-job.sh bin/cvc5/cvc5-2025-04-29 -t 60 -d proofs/qf_s/60s/cvc5-2025-04-29 -b qf_s -o "--dump-proofs --proof-granularity=dsl-rewrite"

submit-job.sh bin/cvc5/cvc5-2025-04-29 -t 60 -d proofs/qf_slia/60s/cvc5-2025-04-29 -b qf_slia -o "--dump-proofs --proof-granularity=dsl-rewrite"
```

```sh
python scripts/extract_proofs.py proofs/qf_s*/60s/cvc5-2025-04-29
```

```sh
python scripts/create_benchmark_set.py proofs/qf_s*/60s/cvc5-2025-04-29 > benchmarks/benchmark_set_qf_60s_cvc5-2025-04-29_re-eval
```

# Proofs Check
```
#/home/cs/israeloh/bin/submit-job.sh projects/ethos/build/src/ethos -t 60 -b qf_60s_cvc5-2025-04-29_re-eval -o --include=/home/cs/israeloh/git/cvc5/proofs/eo/cpc/Cpc.eo -d checks/qf_60s-cvc5-2025-04-29_re-eval/test7
```