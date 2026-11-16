# Affine Switching Lab

**Interactive educational companion to**

**Sub-Nyquist Affine Antenna Switching for Low-Complexity Angle–Doppler Estimation**  
Alireza Pourafzal, Nitin Jonathan Myers, Dario Tagliaferri, Musa Furkan Keskin, and Henk Wymeersch.

[**Try the interactive lab**](https://alirezap94.github.io/subnyquist-affine-switching/) · [**Read the paper (DOI: 10.31224/8383)**](https://doi.org/10.31224/8383)

## Overview

The lab illustrates how affine antenna switching turns a target's Doppler phase progression into a deterministic shift in the spatial-frequency domain. A single receiver RF chain samples one antenna element at a time, using two different affine sweeps. Different sweep slopes produce different spectral shifts for the same physical target.

The goal is to communicate the central idea of the paper through a lightweight, interactive visualization. This is a teaching companion, **not** a full implementation of the estimator.

## Explore the concept

1. **Design two switching sweeps.** Choose the planar-array dimensions, sampling budget, maximum Doppler, and switching interval. The demo generates two distinct feasible affine antenna-switching schedules and shows their selected antenna positions.
2. **Move a target in Doppler.** Change the target Doppler and inspect the two single-target spatial point-spread functions (PSFs), together with a combined view that overlays both responses.
3. **Compare the shifts.** At zero Doppler the main peaks overlap. With nonzero Doppler the affine sweep slopes move the peaks differently.

## Mathematical foundation

For an antenna selected at index `(i_m, j_m)` and time index `m`, the noiseless single-target switched measurement is

```text
y_m = alpha * exp(j * (omega_x*i_m + omega_y*j_m + gamma*m))
gamma = 2*pi*nu*T
```

Within sweep `s`, the affine time relation is `p = a_s*i + b_s*j + c_s`, giving shifted spatial frequencies

```text
theta_x,s = omega_x + a_s*gamma
theta_y,s = omega_y + b_s*gamma
```

The PSF panels evaluate a normalized matched-filter response over spatial-frequency grids for the actual selected antennas of each sweep. The page does not run a peak detector, add measurement noise, recover physical angle/Doppler parameters, or solve the paper's offline spatial-prior optimization.

## Contents

- `index.html`: full standalone interactive lab, including the styles and JavaScript.
- `sitemap.xml`: site map for search engine discovery.
- `README.md`: project description, mathematical context, and citation.

The site is static, with no external JavaScript dependencies and no build step. It is hosted on GitHub Pages.

## Citation

Pourafzal, A., Myers, N. J., Tagliaferri, D., Keskin, M. F., and Wymeersch, H., *Sub-Nyquist Affine Antenna Switching for Low-Complexity Angle–Doppler Estimation*.

https://doi.org/10.31224/8383
