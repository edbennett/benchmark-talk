## ![SOMBRERO](images/sombrero-logo.svg)

A kernel benchmark based on HiRep (as of 2018)

* Strategy based on lessons learned from BSMBench
* Tests a fixed number of CG iterations
* Tests six theories:
  * $SU(2)$ fundamental
  * $SU(2)$ adjoint
  * $SU(3)$ fundamental
  * $Sp(4)$ fundamental
  * $SU(3)$ antisymmetric
  * $Sp(4)$ adjoint

-

## SOMBRERO Technicalities

* Streamlined build with only Make
* Removed dependence on input files
  * Automated determination of parallelisation
  * Additional flags to choose lattice volume, including presets
* Full CG from HiRep used, so communication pattern is representative
  * Targets a fixed iteration number, so takes less time on faster machines
* Removes code generator in favour of specific headers for theories of interest

-

## SOMBRERO on Skylake and KNL

![A scatter plot of results for SOMBRERO on Skylake and KNL](images/sombrero-knl-skylake.svg)<!-- .element width="1000px" -->

-

## AVX2 vs AVX-512 on Skylake

![A barchart of results for SOMBRERO on Skylake](images/sombrero-skylake-avx.svg)<!-- .element width="1000px" -->
