# Trixi2Vtk.jl

[![Docs-stable](https://img.shields.io/badge/docs-stable-blue.svg)](https://trixi-framework.github.io/Trixi.jl/stable)
[![Build Status](https://github.com/trixi-framework/Trixi2Vtk.jl/workflows/CI/badge.svg)](https://github.com/trixi-framework/Trixi2Vtk.jl/actions?query=workflow%3ACI)
[![Coveralls](https://coveralls.io/repos/github/trixi-framework/Trixi2Vtk.jl/badge.svg?branch=master)](https://coveralls.io/github/trixi-framework/Trixi2Vtk.jl?branch=master)
[![License: MIT](https://img.shields.io/badge/License-MIT-success.svg)](https://opensource.org/licenses/MIT)
[![GitHub commits since tagged version](https://img.shields.io/github/commits-since/trixi-framework/Trixi2Vtk.jl/v0.2.4.svg?style=social&logo=github)](https://github.com/trixi-framework/Trixi2Vtk.jl)

With **Trixi2Vtk.jl** you can convert the HDF5-based output files created by
[Trixi.jl](https://github.com/trixi-framework/Trixi.jl) (solution or restart
files) to VTK files. The converted files can then be further processed with
[ParaView](https://www.paraview.org) or [VisIt](https://visit.llnl.gov) to
generate publication-quality visualizations. Trixi2Vtk is part of the
[Trixi framework](https://github.com/trixi-framework).


## Installation
If you have not yet installed Julia, please [follow the instructions for your
operating system](https://julialang.org/downloads/platform/). Trixi2Vtk works
with Julia v1.5.

Trixi2Vtk is a registered Julia package. Hence, you can install it by executing
the following commands in the Julia REPL:
```julia
julia> import Pkg; Pkg.add("Trixi2Vtk")
```


## Usage
In the Julia REPL, first load the package Trixi2Vtk
```julia
julia> using Trixi2Vtk
```
To process an HDF5 file generated by Trixi.jl, execute
```julia
julia> trixi2vtk(joinpath("out", "solution_000000.h5"), output_directory="out")
```
This will create two unstructured VTK files in the `out/` subdirectory that can
be opened with ParaView or VisIt: `solution_000000.vtu` contains the
discontinuous Galerkin solution data while `solution_000000_celldata.vtu` holds
any cell-based values such as the current AMR indicator or the cell refinement
level.
<p align="center">
  <img width="300px" src="docs/src/assets/solution_000000_scalar_mesh.png">
</p>

For further information on how to use Trixi with Trixi2Vtk, please refer to the
[documentation of Trixi](https://trixi-framework.github.io/Trixi.jl/stable/).


## Authors
Trixi2Vtk is maintained by the
[Trixi authors](https://github.com/trixi-framework/Trixi.jl/blob/master/AUTHORS.md).
Its principal developers are
[Michael Schlottke-Lakemper](https://www.mi.uni-koeln.de/NumSim/schlottke-lakemper)
(University of Cologne, Germany) and [Hendrik Ranocha](https://ranocha.de)
(KAUST, Saudi Arabia).


## License and contributing
Trixi2Vtk is licensed under the MIT license (see [LICENSE.md](LICENSE.md)).
