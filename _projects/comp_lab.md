---
layout: project
title: Lattice simulations, from oscillators to QCD.
description: Computational physics lab — Monte Carlo path integrals in C for the quantum harmonic oscillator, and the topological susceptibility of SU(3) gauge theory.
lede: "Computational physics lab — Feynman's path integral turned into a Monte Carlo simulation: first validated on the quantum harmonic oscillator, then applied to the topology of the QCD vacuum."
kind: Course project
thumb: assets/img/thumbs/comp-lab.jpg
importance: 3
category: work
related_publications: false
github: https://github.com/MatthewMaisano/Computational-physics-lab
stack: [C, Makefile, Python, Monte Carlo, Jackknife]
links:
  - label: View the code
    url: https://github.com/MatthewMaisano/Computational-physics-lab
    icon: fa-brands fa-github
    primary: true
highlights:
  - value: "0.9979 ± 0.0006"
    label: energy gap in the continuum (exact value 1)
  - value: "0.5000 ± 0.0003"
    label: matrix element |⟨0|x|1⟩|² (exact value 0.5)
  - value: "175 ± 5 MeV"
    label: topological susceptibility χ<sup>1/4</sup> of SU(3)
---

## The idea

Many problems in quantum physics — up to the strong force that holds protons together — cannot be solved with pen and paper. **Lattice** methods attack them by brute force: space and time are replaced by a grid of points, Feynman's path integral becomes a (huge) statistical average, and that average is computed with Monte Carlo simulations. The physical answer is recovered at the end by taking the **continuum limit**, letting the grid spacing shrink to zero.

In this lab I went through the whole chain twice: first on a problem with a known answer, to validate the method, then on a real quantity of quantum chromodynamics (QCD).

## <span class="pj-step">Part 1</span> The quantum harmonic oscillator

I wrote a C program that simulates the paths of a quantum particle in a harmonic potential with the **Metropolis algorithm**, on lattices from 64 up to 1024 time slices, using Lüscher's RANLUX random number generator. The pipeline, driven by a Makefile, is split into three executables:

<div class="pj-features">
  <div class="pj-feature"><strong>1 · Generation</strong><p>Thermalisation of the Markov chain, then 100,000 sweeps recording the paths.</p></div>
  <div class="pj-feature"><strong>2 · Binning</strong><p>Measurement of the autocorrelation time and grouping of the data into independent bins.</p></div>
  <div class="pj-feature"><strong>3 · Analysis</strong><p>Correlation functions with jackknife errors, from which energy and matrix element are extracted.</p></div>
</div>

<div class="pj-figrow-wrap">
  <div class="pj-figrow">
    <figure class="pj-figure">
      <img src="{{ 'assets/img/comp-lab/ground-state.png' | relative_url }}" alt="Ground-state probability distribution" loading="lazy">
      <figcaption>Where the simulated particle spends its time reproduces the quantum ground state.</figcaption>
    </figure>
    <figure class="pj-figure">
      <img src="{{ 'assets/img/comp-lab/correlator.png' | relative_url }}" alt="Correlation function decay" loading="lazy">
      <figcaption>Correlations decay exponentially in time; the decay rate is the energy gap.</figcaption>
    </figure>
  </div>
</div>

Repeating the simulation at six lattice spacings, from a = 1 down to a = 1/16, and fitting the discretisation effects (proportional to a² and a⁴), I extrapolated to the continuum:

<figure class="pj-figure">
  <img src="{{ 'assets/img/comp-lab/continuum-limit.png' | relative_url }}" alt="Continuum limit of energy gap and matrix element" loading="lazy">
  <figcaption>Continuum extrapolation of the energy gap and of the matrix element ⟨0|x|1⟩ (units ħ = m = ω = 1).</figcaption>
</figure>

<div class="pj-callout" markdown="1">
<span class="pj-callout-title">Result</span>
Energy gap E₁ − E₀ = **0.9979 ± 0.0006** (exact: 1) and |⟨0|x|1⟩|² = **0.5000 ± 0.0003** (exact: 0.5), with good fits (χ²/dof = 0.8 and 0.5). The simulation reproduces the exact quantum-mechanical results to better than 0.3%.
</div>

## <span class="pj-step">Part 2</span> Topology of the QCD vacuum

The vacuum of the strong interaction is not empty: gauge fields can wind in topologically distinct ways, labelled by an integer **topological charge Q**. How much Q fluctuates — the _topological susceptibility_ χ = ⟨Q²⟩ / V — is a fundamental number, connected through the Witten–Veneziano formula to the unusually large mass of the η′ meson.

I analysed about 1,000 gauge-field configurations of SU(3) Yang–Mills theory on each of four lattices (12⁴, 16⁴, 16⁴, 20⁴), on which the charge was measured along the **gradient (Wilson) flow**, a smoothing procedure that removes the short-distance noise of the lattice.

<figure class="pj-figure">
  <img src="{{ 'assets/img/comp-lab/qcd-charge.png' | relative_url }}" alt="Topological charge before and after gradient flow" loading="lazy">
  <figcaption>Topological charge on the 20⁴ lattice: a noisy continuous number on the raw configurations, clustered around integers after the gradient flow.</figcaption>
</figure>

For each lattice I computed t₀²χ (made dimensionless with the reference flow scale t₀), estimated its error with the jackknife, and extrapolated linearly in a²/t₀ to the continuum, checking that the result does not depend on the flow time used for the measurement (four choices, from t₀/4 to t₀).

<figure class="pj-figure pj-narrow">
  <img src="{{ 'assets/img/comp-lab/qcd-continuum.png' | relative_url }}" alt="Continuum extrapolation of the topological susceptibility" loading="lazy">
  <figcaption>Continuum extrapolation of the topological susceptibility, compared with the high-precision literature value (grey band).</figcaption>
</figure>

<div class="pj-callout" markdown="1">
<span class="pj-callout-title">Result</span>
t₀²χ = **(5.9 ± 0.7) × 10⁻⁴**, i.e. χ<sup>1/4</sup> ≈ **175 ± 5 MeV**, compatible within about one standard deviation with the precision lattice determination t₀²χ = 6.67(7) × 10⁻⁴.
</div>

## What I learned

Writing a complete simulation-and-analysis pipeline from scratch — modular C code, reproducible builds, thermalisation and autocorrelation checks, resampling error estimates — and the logic, shared by all lattice calculations, of validating on a known case before trusting the numbers on an unknown one.
