---
layout: page
title: Lattice simulations, from oscillators to QCD.
description: Computational physics lab — Monte Carlo path integrals in C for the quantum harmonic oscillator, and the topological susceptibility of SU(3) gauge theory.
img:
importance: 3
category: work
related_publications: false
github: https://github.com/MatthewMaisano/Computational-physics-lab
---

**Code: [github.com/MatthewMaisano/Computational-physics-lab](https://github.com/MatthewMaisano/Computational-physics-lab)**

**The idea.** Many problems in quantum physics — up to the strong force that holds protons together — cannot be solved with pen and paper. _Lattice_ methods attack them by brute force: space and time are replaced by a grid of points, Feynman's path integral becomes a (huge) statistical average, and the average is computed with Monte Carlo simulations. The physical answer is recovered at the end by taking the _continuum limit_, i.e. letting the grid spacing shrink to zero. In this computational physics lab I went through the whole chain twice: first on a problem with a known answer, to validate the method, then on a real quantity of quantum chromodynamics (QCD).

**Tools.** C (modular code built with Makefiles, Lüscher's RANLUX random number generator) · Python (NumPy, SciPy, Matplotlib) · Metropolis Monte Carlo · binning and jackknife error analysis

### Part 1 — The quantum harmonic oscillator on a lattice

I wrote a C program that simulates the paths of a quantum particle in a harmonic potential with the **Metropolis algorithm**, on lattices from 64 up to 1024 time slices. The pipeline, driven by a Makefile, is split into three executables:

- **generation** — thermalisation of the Markov chain, then 100,000 sweeps recording the paths;
- **binning** — measurement of the autocorrelation time between successive sweeps and grouping of the data into independent bins;
- **analysis** — correlation functions and their errors with the **jackknife** method, from which the energy and matrix element are extracted.

<div class="row">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/comp-lab/ground-state.png' | relative_url }}" alt="Ground-state probability distribution" loading="lazy">
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/comp-lab/correlator.png' | relative_url }}" alt="Correlation function decay" loading="lazy">
  </div>
</div>
<div class="caption">
  Left: where the simulated particle spends its time reproduces the quantum ground state — the histogram matches the exact lattice prediction, and is already close to the continuum wave function. Right: correlations between distant times decay exponentially, and the rate of decay is the energy gap between the ground and first excited state.
</div>

Repeating the simulation at six lattice spacings, from $$a = 1$$ down to $$a = 1/16$$, and fitting the discretisation effects ($$\propto a^2, a^4$$), I extrapolated to the continuum:

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/comp-lab/continuum-limit.png' | relative_url }}" alt="Continuum limit of energy gap and matrix element" loading="lazy">
  </div>
</div>
<div class="caption">
  Continuum extrapolation of the energy gap and of the matrix element ⟨0|x|1⟩ (in units ħ = m = ω = 1).
</div>

**Result.** Energy gap $$E_1 - E_0 = 0.9979 \pm 0.0006$$ (exact value 1) and $$|\langle 0|x|1\rangle|^2 = 0.5000 \pm 0.0003$$ (exact value 0.5), with good fits ($$\chi^2/\text{dof} = 0.8$$ and $$0.5$$): the simulation reproduces the exact quantum-mechanical results to better than 0.3%.

### Part 2 — Topology of the QCD vacuum

The vacuum of the strong interaction is not empty: gauge fields can wind in topologically distinct ways, labelled by an integer **topological charge** $$Q$$. How much $$Q$$ fluctuates — the _topological susceptibility_ $$\chi_{top} = \langle Q^2\rangle / V$$ — is a fundamental number, connected through the Witten–Veneziano formula to the unusually large mass of the η′ meson.

I analysed about 1,000 gauge-field configurations of SU(3) Yang–Mills theory on each of four lattices (12⁴, 16⁴, 16⁴, 20⁴), on which the charge was measured along the **gradient (Wilson) flow** — a smoothing procedure that removes the short-distance noise of the lattice.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/comp-lab/qcd-charge.png' | relative_url }}" alt="Topological charge before and after gradient flow" loading="lazy">
  </div>
</div>
<div class="caption">
  Topological charge on the 20⁴ lattice. On the raw configurations it is a noisy continuous number; after the gradient flow it clusters around integer values, as it should.
</div>

For each lattice I computed $$t_0^2\,\chi_{top}$$ (made dimensionless with the reference flow scale $$t_0$$), estimated its error with the jackknife, and extrapolated linearly in $$a^2/t_0$$ to the continuum. I checked that the result does not depend on the flow time used for the measurement (four choices, from $$t_0/4$$ to $$t_0$$).

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ 'assets/img/comp-lab/qcd-continuum.png' | relative_url }}" alt="Continuum extrapolation of the topological susceptibility" loading="lazy">
  </div>
</div>
<div class="caption">
  Continuum extrapolation of the topological susceptibility, compared with the high-precision literature value (grey band).
</div>

**Result.** $$t_0^2\,\chi_{top} = (5.9 \pm 0.7)\times 10^{-4}$$, i.e. $$\chi_{top}^{1/4} \approx 175 \pm 5$$ MeV, compatible within about one standard deviation with the precision lattice determination $$t_0^2\chi_{top} = 6.67(7)\times10^{-4}$$.

**What I learned.** Writing a complete simulation-and-analysis pipeline from scratch — modular C code, reproducible builds, thermalisation and autocorrelation checks, resampling error estimates — and the logic, shared by all lattice calculations, of validating on a known case before trusting the numbers on an unknown one.
