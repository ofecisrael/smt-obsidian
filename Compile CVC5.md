Compile CVC5
```sh
./configure.sh debug --auto-download
    # use --prefix to specify an install prefix (default: /usr/local)
    # use --name=<PATH> for custom build directory
    # use --auto-download to download and build missing, required or
    #   enabled, dependencies
cd build   
make -j11             # use -jN for parallel build with N threads
#make check       # to run default set of tests
#make install     # to install into the prefix specified above
```
or take from here: https://github.com/cvc5/cvc5/releases

# Compile Ethos
```sh
mkdir build
cd build
cmake ..
make
```
# 
# Proofs Check
```
#/home/cs/israeloh/bin/submit-job.sh projects/ethos/build/src/ethos -t 60 -b qf_60s_cvc5-2025-04-29_re-eval -o --include=/home/cs/israeloh/git/cvc5/proofs/eo/cpc/Cpc.eo -d checks/qf_60s-cvc5-2025-04-29_re-eval/test7
```