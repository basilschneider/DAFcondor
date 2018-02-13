Repository to submit jobs from the DAnalysis Framework to HTCondor.

Note that only directories are suported in the DAnalysis Framework configs.

1. First you need to create a tarball that includes your implementation of the
   DAnalysis Framework and the DAnalysis Framework server (usually on /afs).
   You can use `./make_tarball` for that, but you will first need to update the
   path's in that script.

1. Now you need to define your sample groups in `condor_submit`. For each
   sample, an array with two entries is needed. The first entry is the name of
   the config file (in the config subdirectory) and the second entry is the part
   of the name that matches all samples. For example in `condor_submit`, there
   is an array defined as `Bj=(configSkimmer_v342pre05.txt Bj-4p)` The sample is
   defined in config/configSkimmer_v342pre05.txt and all samples that start with
   `Bj-4p` are matched. The samples need to be commented out initially.

1. In `condor_submit`, define all samples you want to run over, by putting them
   into one single array.

1.  Run `./condor_submit`.
