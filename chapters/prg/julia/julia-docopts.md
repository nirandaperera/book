# Docopts

Docopts in Julia are similar to Python, Ruby, and other languages.

## Installation

Again, most of Julia's packages that are not in the base code are
contained within git repositories.  [@julia-getting-started]. To get
started with DocOpts in Julia, issue the following command within the
Julia REPL:

```julia
Pkg.add("DocOpt")
```

Usage example is given from the following website:
<https://github.com/docopt/DocOpt.jl> [@docopt-jl].  Create a file
called `naval-fate.jl`:

```julia
#dir/naval-fate.jl
doc = """Naval Fate.
https://github.com/JuliaLang/METADATA.jl

Usage:
  naval_fate.jl ship new <name>...
  naval_fate.jl ship <name> move <x> <y> [--speed=<kn>]
  naval_fate.jl ship shoot <x> <y>
  naval_fate.jl mine (set|remove) <x> <y> [--moored|--drifting]
  naval_fate.jl -h | --help
  naval_fate.jl --version

Options:
  -h --help     Show this screen.
  --version     Show version.
  --speed=<kn>  Speed in knots [default: 10].
  --moored      Moored (anchored) mine.
  --drifting    Drifting mine.
```


In the same directory as `naval-fate.jl`, run the following in the
Julia REPL:

```julia
julia> using DocOpt  # import docopt function
julia> args = docopt(doc, version=v"2.0.0")
```
