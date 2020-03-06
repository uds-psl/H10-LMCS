# Hilbert's tenth problem in Coq

Dominique Larchey-Wendling <dominique.larchey-wendling@loria.fr>, Yannick Forster <forster@ps.uni-saarland.de>

This repository contains the Coq formalisation of the paper "Hilbert's tenth problem in Coq", submitted as preprint to Logical Methods in Computer Science.

## How to compile the code

If you can use `opam 2` on your system, you can follow the instructions here.
If you cannot use `opam 2`, you can use the `noopam` branch of this repository, which has no dependencies, but less available problems.

### Required packages

You need `Coq 8.8.1`, `8.8.2` or `8.9.1` built on OCAML `> 4.02.3`, the [Equations](https://mattam82.github.io/Coq-Equations/) package and the [MetaCoq](https://metacoq.github.io/metacoq/) package for Coq. If you're using opam 2 you can use the following commands to install the dependencies on a new switch:

```
opam switch create coq-library-undecidability 4.07.1+flambda
eval $(opam env)
opam repo add coq-released https://coq.inria.fr/opam/released
opam install . --deps-only
```

### Build external libraries

The Undecidability libraries depends on several external libraries. Initialise and build them once as follows:

``` sh
git submodule update --init --recursive
make deps
```

### Building the undecidability library

- `make all` builds the library
- `make html` generates clickable coqdoc `.html` in the `website` subdirectory
- `make clean` removes all build files in `theories` and `.html` files in the `website` directory
- `make realclean` also removes all build files in the `external` directory. You have to run `make deps` again after this.


## A Coq library of undecidable problems

This repo is a static snapshot of our [library of undecidable problems](https://github.com/uds-psl/coq-library-undecidability) together with the html version of the code. Note that the repository also contains other, unrelated parts of the library, contributed by Andrej Dudenhefner, Yannick Forster, Edith Heiter, Dominik Kirst, Fabian Kunze, Dominique Larchey-Wendling, Gert Smolka, Simon Spies, Dominik Wehr, and Maximilian Wuttke.

An overview over the code is in Appendix A of the ([paper](https://members.loria.fr/DLarchey/files/papers/H10_FSCD19.pdf)).
