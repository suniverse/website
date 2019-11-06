---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Notes on Running FDM Simulation in ENZO"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2019-11-05T20:41:43-05:00
lastmod: 2019-11-05T20:41:43-05:00
featured: true
draft: false
markup: mmark

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []

---
# Running FDM simulations

The FDM simulations in ENZO can be run through ProblemType 30 for cosmological simulations and ProblemType 191 for non-cosmological FDM-only simulations.
The key parameters for running FDM simulations are QuantumPressure which should be set to 1 to enable the evolution of Schrodinger-Poisson equation and FDMMass which sets the value of FDM particle mass in unit of $10^{-22}$ eV.
The default method for integrating the Schrodinger equation uses the operator-spliting method and 4th order Runge-Kutta with 4th order accurate finite difference method (see Li, Hui and Bryan 2019). Therefore, the NumberOfGhostZones should be set to 8. The boundary condition should be set to periodic, 3 for both faces. In addition, the de Broglie wavelength must be resolved to obtain accurate results.

## Cosmological simulations
For FDM cosmological simulations, one should use ProblemType 30. The initial data for the wavelength should be provided as hdf5 files with names GridRePsi (the real part), GridImPsi (the imaginary part) and GridFDMDensity (the FDM density). The code will read in the files to start the simulation.
ENZO currently supports the FDM-only simulations, FDM + particles, FDM + fluid and FDM + particles + fluid. The initialization of particles and fluid is not altered. In principle, various chemical components could also be included, but not tested yet.

## Non-cosmological FDM-only simulations
ProblemType 191 is used for the non-cosmological FDM-only simulations. ENZO will read in the hdf5 files GridRePsi and GridImPsi and integrate the Schrodinger euqation. The density will be automatically calculated.

## Development
For development, for example, to add self interaction, one can modify the evolution of Schrodinger equation in Grid_Schrodinger.C.