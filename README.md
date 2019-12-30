# AlphaStableDistributions

[![Build Status](https://travis-ci.org/baggepinnen/AlphaStableDistributions.jl.svg?branch=master)](https://travis-ci.com/baggepinnen/AlphaStableDistributions.jl)
[![Codecov](https://codecov.io/gh/baggepinnen/AlphaStableDistributions.jl/branch/master/graph/badge.svg)](https://codecov.io/gh/baggepinnen/AlphaStableDistributions.jl)

This library is a port of functionality from [arlpy](https://github.com/org-arl/arlpy/blob/master/arlpy/stable.py).

## Installation
```julia
using Pkg; pkg"add https://github.com/baggepinnen/AlphaStableDistributions.jl"
```

## Usage
```julia
julia> using AlphaStableDistributions

julia> d1 = AlphaStable()
AlphaStable{Float64}(α=1.5, β=0.0, scale=1.0, location=0.0)

julia> s = [rand(d1) for _ in 1:100000];

julia> d2 = fit(AlphaStable, s)

AlphaStable{Float64}(α=1.4748701622930906, β=0.0, scale=1.006340087707924, location=-0.0036724481641865715)

julia> x = rand(AlphaSubGaussian(n=9600));

julia> plot(x)
```
![window](asg.svg)

### Credits
Julia code by @ymtoo and @baggepinnen, original implementation by @mchitre and others.
