# Complementarity.jl

[![Complementarity](http://pkg.julialang.org/badges/Complementarity_0.4.svg)](http://pkg.julialang.org/?pkg=Complementarity)
[![Complementarity](http://pkg.julialang.org/badges/Complementarity_0.5.svg)](http://pkg.julialang.org/?pkg=Complementarity)


[![Build Status](https://travis-ci.org/chkwon/Complementarity.jl.svg?branch=master)](https://travis-ci.org/chkwon/Complementarity.jl)
[![Build status](https://ci.appveyor.com/api/projects/status/pcb5nb5tsstueq1f?svg=true)](https://ci.appveyor.com/project/chkwon/complementarity-jl)
[![Coverage Status](https://coveralls.io/repos/github/chkwon/Complementarity.jl/badge.svg?branch=master)](https://coveralls.io/github/chkwon/Complementarity.jl?branch=master)

Primarily, this package does the following two things:

- This package provides a modeling and computational interface for solving [Mixed Complementarity Problems](https://en.wikipedia.org/wiki/Mixed_complementarity_problem) (MCP): modeling by [JuMP.jl](https://github.com/JuliaOpt/JuMP.jl) and computing by [PATHSolver.jl](https://github.com/chkwon/PATHSolver.jl) and [NLsolve.jl](https://github.com/EconForge/NLsolve.jl). See [the documentation](MCP.md).

```
F(x) ⟂ lb ≤ x ≤ ub
```

- For solving [mathematical programs with equilibrium constraints (MPEC)](https://en.wikipedia.org/wiki/Mathematical_programming_with_equilibrium_constraints), this package provides an extension to [JuMP.jl](https://github.com/JuliaOpt/JuMP.jl) by providing a macro that accepts complementarity conditions as constraints.  Then it reformulates the complementarity conditions as a set of equality and inequality constraints so that a nonlinear optimization solver such as [Ipopt.jl](https://github.com/JuliaOpt/Ipopt.jl) can solve the problem. See [the documentation](MPEC.md).

```
min  f(x)
s.t. g(x) ≤ 0
     F(x) ⟂ lb ≤ x ≤ ub 
```

# Installation

```julia
Pkg.add("Complementarity")
```

This will also install a few other packages.
