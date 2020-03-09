## Lattice Gauge Theory

Three words need defining:

* Lattice
* Gauge
* Theory

---

## Theory

A set of laws of physics.

* Hopefully, but not necessarily, consistent
* Hopefully, but not necessarily, applicable to reality
* Frequently motivated by symmetry or other "aesthetic" arguments
* Most often defined in terms of a action and/or a Lagrangian function

---

## Gauge

An arbitrary, but necessary choice.

![A diagram of railway track gauges used around the world.](images/gauge.svg)

-

## Gauge Theory

A theory having a gauge symmetry.

An arbitrary transformation can be made at each point in space
independently, and the resulting physics is not changed.

![A cylinder, divided into slices](images/cylinder.svg) <!-- .element: class="fragment vanish" data-fragment-index="1" -->
![A cylinder, divided into slices](images/cylinder.svg) <!-- .element: class="fragment vanish" data-fragment-index="1" -->

![A cylinder, divided into slices, with a red horizontal line along it from end to end](images/cylinder-straight.svg) <!-- .element: class="fragment appear" data-fragment-index="1" -->
![A cylinder, divided into slices, with a red squiggle along it from end to end](images/cylinder-curvy.svg) <!-- .element: class="fragment appear" data-fragment-index="1" -->

Quantity defined at each point in space = a (gauge) field

Examples: classical electromagnetism, quantum chromodynamics

-

## Aside: Spontaneous Symmetry Breaking

Physics can drive a system to break a symmetry.

![A 3-dimensional plot of (x^2)^2, showing a single minimum bucket shape](images/bucket.svg) <!-- .element: class="fragment vanish" data-fragment-index="1" -->
![A 3-dimensional plot of (x^2 - 1)^2, showing a continuum of minima, in the classic "Mexican hat" shape](images/hat.svg) <!-- .element: class="fragment appear" data-fragment-index="1" -->

Higgs tells us that this gives mass to otherwise massless states.

-

## Gauge Symmetries

* Described by Lie (continuous) groups
* Abelian groups (e.g. Quantum ElectroDynamics, $e^{\alpha(x)}$)
  * Group elements commute with each other: `$AB=BA$`
  * Can be solved analytically
* Non-Abelian groups (e.g. QCD)
  * Group elements do not commute: `$AB \ne BA$`
  * Cannot be solved analytically
  * Groups elements are usually $N\times N$ matrices
    * `$SO(N)$`: real, `$O^\mathrm{T} O=1$`, `$\det O=1$`
	* `$SU(N)$`: complex, `$U^\dagger U=1$`, `$\det U=1$`
	* `$Sp(N)$`: complex, `$U^\dagger U=1$`, `$\det U=1$`, `$U^{\mathrm{T}} \Omega U=\Omega$`, where `$\Omega=\left(\begin{array}{cc}0 & 1 \\ 1 & 0\end{array}\right)$`

-

## Group Representations

Fields can transform in various ways under gauge symmetries:

* Trivial representation
  * Field doesn't change
  * Field has one element
* Fundamental representation
  * Field multiplied by $N \times N$ matrices
  * Field has $N$ elements
* Higher representations
  * Field multiplied by $M \times M$ matrices, $M>N$
  * Field has $M$ elements

-

## Quantum ChromoDynamics (QCD)

The gauge theory where:

* Gauge symmetry $SU(3)$
* Matter (quarks) transforms under the fundamental representation of $SU(3)$

-

## The Standard Model (SM)

* Gauge symmetry $SU(3) \times SU(2) \times U(1)$
  * With some definitions of how matter transforms
  * And a Higgs boson
* The best description we have of reality

-

## Beyond the Standard Model (BSM)

* Other theories, studied to resolve perceived problems in the SM

---

## Lattice

By analogy with crystallography: A regular array of points

![A diagram showing a three-dimensional array of white circles](images/lattice-white.svg)

-

## Lattice Gauge Theory

The set of techniques for studying gauge theories discretised on a lattice.

* Developed in the 1970s
  * Developed from techniques in computational condensed matter physics
* The only first-principles, non-perbative method for non-Abelian gauge theories

-

## Lattice Gauge Theory

<div id="left">

* Gauge fields: $N \times N$ matrices, one per link
  * 4 per lattice site (in 4D)
* Matter fields: 4 $M$-element vectors, per site
* Derivatives in continuum Lagrangian become nearest-neighbour interactions
  * Action is local
  * Lattice can be partitioned in space, and partitions worked on independently
* Observables are path integrals
  * Use Monte Carlo integration
* Action is (usually) real
  * Use importance sampling
  * Generate configurations of the gauge field representative of distribution dictated by the action
* Characterise interaction between gauge field and matter by Dirac operator $D$
  * Nearest-neighbour interaction
  * Inversion of $D$ is >90% of execution time
</div>

<div id="right">

![A diagram showing a three-dimensional array of white circles. Some of the circles are labeled "sites". Some immediately adjacent circles have lines between them which are labeled "links". Some groups of four immediately adjacent circles have lines forming a closed loop between them, which are labeled "plaquettes".](images/lattice-labeled.svg)

</div>

-

## Lattice practicalities

* Typical volumes: $24\times12^3$ is small, $256\times128^3$ is largest
  * BSM stays on the small end
* Physical lattice spacing is emergent, not directly set
* Boundary conditions are chosen to suit observable, but typically periodic
