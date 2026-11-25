---
layout: project
title: Homogeneous black holes in 5D.
description: My Master's thesis in theoretical physics — black holes with exotic horizon geometries in five-dimensional gauged supergravity.
lede: "Master's thesis in theoretical physics (University of Milano-Bicocca, November 2026) — can a black hole have a horizon shaped like one of Thurston's exotic geometries, and what does the spacetime around it look like? Supervisors: Prof. Silke Klemm and Prof. Silvia Penati."
kind: Master's thesis
year: 2026
thumb: assets/img/thumbs/thesis.jpg
importance: 2
category: work
related_publications: false
stack: [General relativity, Supergravity, AdS/CFT, Numerical ODEs, Python]
links:
  - label: Read the thesis (PDF)
    url: assets/pdf/Maisano_MSc_thesis.pdf
    icon: fa-solid fa-file-pdf
    primary: true
highlights:
  - value: "4"
    label: families of 5D black holes studied
  - value: "p* = α₀√−Λ"
    label: critical magnetic field separating regular and singular solutions
  - value: "k₊ ≈ 1.2078"
    label: irrational exponent of the extremal horizon
  - value: "~10⁻⁹"
    label: numerical error on the field equations
---

## The question

In our four-dimensional world, Hawking proved that the horizon of a black hole must be a sphere — but the theorem relies on a cosmological constant that is positive or zero. In **anti-de Sitter (AdS)** space, the negatively curved universe at the heart of the AdS/CFT correspondence (which links gravity to quantum field theories), the rules are much looser: horizons can be flat, hyperbolic, or have far stranger shapes.

In five dimensions the horizon is a three-dimensional space, and Thurston's classification gives eight possible _model geometries_ for it. The familiar ones (sphere, flat, hyperbolic) are well studied; my thesis focuses on the more exotic **twisted** ones, **Nil** and **Sol**. I studied four families of black holes in five-dimensional gauged supergravity, combining analytic techniques for the first three with a numerical approach for the fourth.

## <span class="pj-step">Part 1</span> Zooming into AdS black holes

I applied a scaling limit — the _Inönü–Wigner contraction_ — to the Schwarzschild–AdS<sub>5</sub> and Reissner–Nordström–AdS<sub>5</sub> black holes. It zooms onto one point of the horizon while boosting it to the speed of light, turning the spherical SU(2) symmetry into the Nil one.

<div class="pj-callout" markdown="1">
<span class="pj-callout-title">Result</span>
The limit is still an exact solution of the field equations: a gravitational wave with flat wave fronts (carrying an electromagnetic wave along with it in the charged case). Because of the cosmological constant it is **not** a standard pp-wave but a plane-fronted wave of **Kundt type**, the AdS analogue of the Siklos waves.
</div>

## <span class="pj-step">Part 2</span> A black hole in a Gödel universe

The Gödel universe is a rotating spacetime famous for allowing _closed timelike curves_ — paths that return to their own past. I studied how light moves around a black hole placed in it, and then applied the same contraction.

<figure class="pj-figure pj-narrow">
  <img src="{{ 'assets/img/thesis/godel-geodesics.png' | relative_url }}" alt="Light rays around the Gödel black hole" loading="lazy">
  <figcaption>Light rays near the Gödel black hole reach the "velocity-of-light surface" (dotted), stop, turn back and spiral towards the horizon.</figcaption>
</figure>

<div class="pj-callout" markdown="1">
<span class="pj-callout-title">Result</span>
After the contraction the horizon disappears and the spacetime is no longer a black hole. Once the Nil directions are made compact, a closed timelike curve passes through **every point**, whatever the mass of the black hole and the size of the compact directions.
</div>

## <span class="pj-step">Part 3</span> The magnetic Sol black hole

The core of the thesis is a black hole whose horizon has **Sol** geometry, supported by a magnetic field of strength _p_. No analytic solution with all the metric functions varying was known, and none of the ansätze I tried worked, so I built the solution numerically: a series expansion near the horizon, then a Runge–Kutta integration outwards, using one of the Einstein equations as a check on the error (about 10<sup>−9</sup>).

<figure class="pj-figure">
  <img src="{{ 'assets/img/thesis/sol-profiles.png' | relative_url }}" alt="Metric functions for different magnetic parameters" loading="lazy">
  <figcaption>How the geometry changes with the magnetic parameter p. Below a critical value the solutions settle to anti-de Sitter at large distance (right panel, lower dashed line); above it they break down at a finite radius.</figcaption>
</figure>

Scanning the parameters, and locating the boundaries with a bisection algorithm, I found that everything is controlled by a critical field **p\* = α₀√−Λ**, which does not depend on the temperature of the black hole:

<div class="pj-features">
  <div class="pj-feature"><strong>p &lt; p*</strong><p>A regular black hole, asymptotically AdS<sub>5</sub> with boundary ℝ<sub>t</sub> × Sol — a new family generalising the known solutions.</p></div>
  <div class="pj-feature"><strong>p = p*</strong><p>Exactly the analytic solution already known in the literature, recovered numerically.</p></div>
  <div class="pj-feature"><strong>p &gt; p*</strong><p>Two Sol directions collapse at a finite radius: a curvature singularity with a power-law structure (exponent 2/3), derived analytically and checked against the numerics.</p></div>
  <div class="pj-feature"><strong>p &lt; p<sub>low</sub></strong><p>In part of parameter space the third direction collapses instead, so regular solutions exist only for p<sub>low</sub> &lt; p &lt; p*.</p></div>
</div>

<div class="pj-figrow-wrap">
  <div class="pj-figrow">
    <figure class="pj-figure">
      <img src="{{ 'assets/img/thesis/sol-phase-diagram.png' | relative_url }}" alt="Phase diagram of the magnetic Sol black hole" loading="lazy">
      <figcaption>Map of the solutions: green are regular, asymptotically AdS black holes; red and blue are the two ways the geometry collapses.</figcaption>
    </figure>
    <figure class="pj-figure">
      <img src="{{ 'assets/img/thesis/sol-collapse.png' | relative_url }}" alt="Collapse near the singularity" loading="lazy">
      <figcaption>Near the singularity the numerical curves become straight lines with the predicted slope 2/3.</figcaption>
    </figure>
  </div>
</div>

### The extremal (zero-temperature) case

Here the geometry near the horizon is AdS<sub>2</sub> × Sol, and small deformations of it grow with an **irrational** power of the distance, k₊ = ½(−1 + √(35/3)) ≈ 1.2078. The solution therefore cannot be written as an ordinary Taylor series: I built the correct double series and matched it numerically with the Fefferman–Graham expansion at infinity, obtaining the horizon size as a function of the magnetic field.

<figure class="pj-figure">
  <img src="{{ 'assets/img/thesis/sol-extremal.png' | relative_url }}" alt="Extremal solutions" loading="lazy">
  <figcaption>Left: scan of 441 extremal solutions — only the teal ones (61) reach anti-de Sitter space at infinity. Right: the resulting relation between horizon size and magnetic field.</figcaption>
</figure>

## What's next

<div class="pj-features">
  <div class="pj-feature"><strong>Analytic solution</strong><p>Use the numerical map as a guide, e.g. a perturbative construction around p*.</p></div>
  <div class="pj-feature"><strong>Thermodynamics &amp; holography</strong><p>Temperature, entropy and free energy of the new Sol black holes, and their dual interpretation.</p></div>
  <div class="pj-feature"><strong>Singularities</strong><p>A systematic classification of the power-law behaviours where the geometry collapses.</p></div>
</div>
