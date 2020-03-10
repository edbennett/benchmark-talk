## BSMBench

A component benchmark based on HiRep (as of 2010)

* Strategy based on Lüscher<sup>1</sup>
* Tests three components:
  * Matter field square norm
  * Gauge-matter field multiply-add
  * Application of Dirac operator to matter field
  * Separate test of inverter convergence (optional, not benchmarked)
* Tests three theories
  * "Comms"&mdash;$SU(2)$, adjoint matter
  * "Balance"&mdash;$SU(3)$, fundamental matter
  * "Compute"&mdash;$SU(6)$, fundamental matter

<sub>1: [https://doi.org/10.1016/S0920-5632(01)01639-5](https://doi.org/10.1016/S0920-5632(01)01639-5)</sub>

-

## BSMBench technicalities

* Targets a particular run time (default: ~10 minutes)
  * Doubles the iteration count after each time check to avoid overhead
* Uses HiRep input file syntax, with set of input files included
  * Sets lattice volume, parallelisation grid, FLOP counts, etc.
* Removes code generator in favour of specific headers for theories of interest
* Removes GPL-licensed RANLUX random number generator
* OpenMP support backported from trunk branch in 2015
* Synchronisation between iterations simulated synthetically via `MPI_Barrier`
* Uses a shell script to massage `Makefile`s and repeatedly call `make`
* Calculates a FLOP/s estimate via reference values counted by IBM utilities
* Outputs both FLOP/s and relative performance to an IBM Blue Gene/P machine

-

## BSMBench limitations

* Excessively complicated build system
* Artificial synchronisation makes for more difficult optimisation
* Limited number of input files; difficult to expand to machines with
  interesting geometries
* Tests a single lattice volume for consistency
  * Hard to fit problem size on small machines
  * Insufficient parallelisation on massively parallel machines

-

## BSMBench strengths

* Has identified a number of platform, MPI, compiler issues/bugs
* Gives a reasonable proxy to application performance on most machines
* Has been used by various vendors to demonstrate their hardware's superiority

-

## BSMBench on HPC Wales

![A scatter plot of BSMBench results on HPC Wales](images/bsmbench-hpcw.svg)<!-- .element width="1200px" -->

-

## BSMBench on massively parallel machines

![A scatter plot of BSMBench results on Blue Gene and Fujitsu FX10 machines](images/bsmbench-bg.svg)<!-- .element width="1200px" -->
