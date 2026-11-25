---
layout: page
title: Homogeneous black holes in 5D.
description: My Master's thesis in theoretical physics — black holes with exotic horizon geometries in five-dimensional gauged supergravity.
img:
importance: 2
category: work
related_publications: false
---

<div class="mb-4">
  <a class="btn btn-sm z-depth-0" role="button" href="{{ 'assets/pdf/Maisano_MSc_thesis.pdf' | relative_url }}" target="_blank" rel="noopener" style="border: 1px solid var(--global-theme-color); color: var(--global-theme-color);"><i class="fa-solid fa-file-pdf"></i> Read the full thesis (PDF)</a>
</div>

**Homogeneous Black Holes in 5D Gauged Supergravity** — Master's Degree in Theoretical Physics, University of Milano-Bicocca, November 2026.
Supervisors: Prof. Silke Klemm (external) and Prof. Silvia Penati (internal).

**The question.** In our four-dimensional world, Hawking proved that the horizon of a black hole must be a sphere. That theorem relies on a positive (or zero) cosmological constant. In _anti-de Sitter_ (AdS) space — the negatively curved universe at the heart of the AdS/CFT correspondence, which links gravity to quantum field theories — the rules are much looser: horizons can be flat, hyperbolic, or have far stranger shapes. In five dimensions the horizon is a three-dimensional space, and Thurston's classification gives eight possible "model geometries" for it. The familiar ones (sphere, flat, hyperbolic) are well studied; my thesis focuses on the more exotic _twisted_ ones, **Nil** and **Sol**, and asks: can a black hole have such a horizon, and what does the spacetime around it look like?

I studied four families of black holes in five-dimensional gauged supergravity, combining analytic techniques for the first three and a numerical approach for the fourth.

### 1. Zooming into AdS black holes: plane waves

I applied a scaling limit (the _Inönü–Wigner contraction_) to the Schwarzschild–AdS<sub>5</sub> and Reissner–Nordström–AdS<sub>5</sub> black holes: it zooms onto one point of the horizon while boosting it to the speed of light, turning the spherical (SU(2)) symmetry into the Nil one.

**Result.** The limit is still an exact solution of the field equations, describing a gravitational wave with flat wave fronts (with an electromagnetic wave travelling along it in the charged case). Because of the cosmological constant it is _not_ a standard pp-wave but a plane-fronted wave of **Kundt type**, the AdS analogue of the Siklos waves.

### 2. A black hole in a Gödel universe: time travel everywhere

The Gödel universe is a rotating spacetime famous for allowing _closed timelike curves_ — paths that return to their own past. I studied light rays around a black hole placed in it, and then applied the same contraction.

<div class="row justify-content-sm-center">
  <div class="col-sm-7 mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/thesis/godel-geodesics.png' | relative_url }}" alt="Light rays around the Gödel black hole" loading="lazy">
  </div>
</div>
<div class="caption">
  Light rays near the Gödel black hole: they reach the "velocity-of-light surface" (dotted), stop, turn back and spiral towards the horizon.
</div>

**Result.** After the contraction the horizon disappears and the spacetime is no longer a black hole. Once the Nil directions are made compact, a closed timelike curve passes through **every point**, whatever the mass of the black hole and the size of the compact directions.

### 3. The magnetic Sol black hole: a numerical map

The core of the thesis is a black hole whose horizon has **Sol** geometry, supported by a magnetic field of strength $$p$$. No analytic solution with all metric functions varying was known, and none of the ansätze I tried worked, so I built the solution numerically: a series expansion near the horizon, then a Runge–Kutta integration outwards, using one of the Einstein equations as a check on the error (~10<sup>−9</sup>).

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/thesis/sol-profiles.png' | relative_url }}" alt="Metric functions for different magnetic parameters" loading="lazy">
  </div>
</div>
<div class="caption">
  How the geometry changes with the magnetic parameter p. Below a critical value the solutions settle to anti-de Sitter at large distance (right panel, lower dashed line); above it they break down at a finite radius.
</div>

**Result: three regimes.** Scanning the parameters, and locating the boundaries with a bisection algorithm, I found that everything is controlled by a critical field $$p_* = \alpha_0\sqrt{-\Lambda}$$, which does not depend on the temperature of the black hole:

- **$$p < p_*$$** — a regular black hole that is asymptotically AdS<sub>5</sub>, with boundary $$\mathbb{R}_t \times \mathrm{Sol}$$: a new family generalising the known solutions.
- **$$p = p_*$$** — exactly the analytic solution already known in the literature, recovered numerically.
- **$$p > p_*$$** — two of the Sol directions collapse at a finite radius, forming a curvature singularity with a precise power-law structure (exponent 2/3), which I derived analytically and checked against the numerics.
- In part of parameter space a second threshold $$p_\text{low}$$ appears, below which the third direction collapses instead — so regular solutions exist only for $$p_\text{low} < p < p_*$$.

<div class="row">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/thesis/sol-phase-diagram.png' | relative_url }}" alt="Phase diagram of the magnetic Sol black hole" loading="lazy">
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/thesis/sol-collapse.png' | relative_url }}" alt="Collapse near the singularity" loading="lazy">
  </div>
</div>
<div class="caption">
  Left: map of the solutions — green are regular, asymptotically AdS black holes; red and blue are the two ways the geometry collapses. Right: near the singularity the numerical curves become straight lines with the predicted slope 2/3.
</div>

**The extremal (zero-temperature) case.** Here the geometry near the horizon is AdS<sub>2</sub> × Sol, and small deformations of it grow with an _irrational_ power of the distance, $$k_+ = \tfrac{1}{2}\left(-1+\sqrt{35/3}\right) \simeq 1.2078$$. This means the solution cannot be written as an ordinary Taylor series: I built the correct double series and matched it numerically with the Fefferman–Graham expansion at infinity, obtaining the horizon size as a function of the magnetic field.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/thesis/sol-extremal.png' | relative_url }}" alt="Extremal solutions" loading="lazy">
  </div>
</div>
<div class="caption">
  Left: scan of 441 extremal solutions — only the teal ones (61) reach anti-de Sitter space at infinity. Right: the resulting relation between horizon size and magnetic field.
</div>

**What's next.** An analytic solution guided by this numerical map (e.g. a perturbative construction around $$p_*$$), the thermodynamics of the new Sol black holes and their holographic interpretation, and a classification of the singular behaviours.

**Tools.** General relativity and supergravity, Lie groups and homogeneous spaces, asymptotic/series expansions, and Python for the numerics (Runge–Kutta integration, bisection, parameter scans).
