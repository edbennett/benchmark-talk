## Benchmarking

Wiktionary: **benchmark** (plural **benchmarks**)

1. A standard by which something is evaluated or measured.
2. A surveyor's mark made on some stationary object and  
   shown on a map; used as a reference point.
3. (computing) A computer program that is executed to  
   assess the performance of the runtime environment.

-

## How to benchmark

* Pick a task
* Time how long it takes
  * Less time is better
* (Optionally) invert the time to get a rate
  * Multiply by operation count to get an operation rate
* Run time should be consistent between runs<!-- .element: class="fragment fade-in" data-fragment-index="1" -->
  * On the same machine<!-- .element: class="fragment fade-in" data-fragment-index="2" -->
  * On equivalent machines<!-- .element: class="fragment fade-in" data-fragment-index="3" -->
* Ideally want a test that benchmark has been executed correctly<!-- .element: class="fragment fade-in" data-fragment-index="4" -->
  * Otherwise vendors can optimise by deleting the loop body<!-- .element: class="fragment fade-in" data-fragment-index="5" -->

-

## Types of benchmark

At opposite ends of the spectrum:

* Microbenchmarks:
  * Constructed to stress one performance characteristic (e.g. CPU FLOP/s,
    disk I/O)
  * Good to show absolute limit of one component of a system
  * Examples: STREAM
* Application benchmarks:
  * Time an entire application running end-to-end
  * Good to show how well the component mix works for one specific problem
  * Examples: Gromacs, VASP

-

## More types of benchmark

In between microbenchmarks and application benchmarks:

* Synthetic benchmarks
  * Use multiple microbenchmarks arranged to emulate a particular class of 
	problem
* Component benchmarks
* Kernel benchmarks
