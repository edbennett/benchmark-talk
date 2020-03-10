## HiRep

A set of tools and libraries for performing computations in lattice gauge
theories in $SU(N)$, $SO(N)$, and $Sp(2N)$ gauge theories with arbitrary
$N$, arbitrary number of flavours of matter, and matter in any two-index
representation.

* Under development since 2007
  * First public release in 2019: https://github.com/claudiopica/HiRep
* Written in C99, with a C++/Perl code generator
  * MPI for spacetime decomposition
  * Limited OpenMP support

-

## Code generator

* Work almost exclusively with $N \times N$ and $M \times M$ matrices
* Matrix-matrix and matrix-vector multiplications in very tight loops
* General linear algebra libraries have overhead of working for any size
* Having branches in MM and MVM for different representations is inefficient
* Instead, generate code for the specific $N$ and $M$ under study
* Perform group theoretical calculations in C++
* Do dirty work of string manipulation and gluing files together in Perl

-

## Parallelisation

MPI:

* Partition volume into equal sized pieces
* Add a 1-site halo around the edge
  * Allows nearest neighbour access without communication
  * Can grow to 2 or 3 sites if necessary
* Abstract away most MPI calls
* Not all tools support MPI
  * Particularly very fast/trivially parallel tools

OpenMP:

* Loops over local volume are abstracted as macros
* Loop macros include relevant OpenMP pragmas

-

## Performance considerations

Design decisions based on mid-2000s compilers

* Heavy use of preprocessor macros to avoid function calls in tight loops
  * Deep nests of macros defining and calling macros
* Loops in macros are partially or completely hand-unrolled
* Custom `complex.h` due to poor C99 complex support
  * Current (2020) HiRep branch has switched to C99 `complex.h`
