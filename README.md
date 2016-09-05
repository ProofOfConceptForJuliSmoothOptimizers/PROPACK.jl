# PROPACK

[![Build Status](https://travis-ci.org/JuliaSmoothOptimizers/PROPACK.jl.svg?branch=master)](https://travis-ci.org/JuliaSmoothOptimizers/PROPACK.jl)
[![Coverage Status](https://coveralls.io/repos/github/JuliaSmoothOptimizers/PROPACK.jl/badge.svg?branch=master)](https://coveralls.io/github/JuliaSmoothOptimizers/PROPACK.jl?branch=master)

A Julia interface to [PROPACK](http://sun.stanford.edu/~rmunk/PROPACK), a library for the computation of the truncated singular value decomposition of matrices or linear operators.
PROPACK only requires operator-vector products to estimate singular values and singular vectors.

## How to Install

```julia
julia> Pkg.clone("https://github.com/JuliaSmoothOptimizers/PROPACK.jl.git")
julia> Pkg.build("PROPACK")
julia> Pkg.test("PROPACK")
```

## Examples

### Compute leading singular triplets

```julia
U, s, V, bnd = tsvd(A, k=3)  # 3 largest singular values and their singular vectors
```

### Compute leading singular values only

```julia
s, bnd = tsvdvals(A, k=3)
```

### Compute smallest singular triplets

Make sure `A` is square or short and wide to avoid the trailing zero singular values:

```julia
U, s, V, bnd = tsvd_irl(A, k=2)
```

### Compute smallest singular values

```julia
s, bnd = tsvdvals_irl(A, k=2)
```
