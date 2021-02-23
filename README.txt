### NOIR
________________________________________________________________________________


#### Official Repositories
________________________________________________________________________________

The official repositories for NOIR Linux maintained by Daniel M. Matongo.

More information:

    - https://k1ss.org
    - https://k1ss.org/package-system
    - https://repology.org/repository/kiss_main


1. Why NOIR?
________________________________________________________________________________

NOIR is a project I've wanted to embark on since my days of LFS, the whole idea of
owning my own distro simply facinates me and taking advantage of the work done
by @kisslinux I was able to.

2. Whats Different?
________________________________________________________________________________

NOIR aims to become a minimal general purpose distro for
your pleasure;

 - Cuttin down on all dependancies and all other bloat to provide you with a functional distro
with as few packages and a much less combined package weight
as possible.

 - Taking notes from Wyverkiss we want to be as GNU free as we
can and if we can't at least make GNU software optional.


3. NOIR & KISS
________________________________________________________________________________

The NOIR main repositories will be kept as close to the KISS main repositories [for now]
so as to allow users to swap between repositories whenever they see it fit.

4. BINARIES
NOTE: This assumes that the user trusts the source of the binary packages.

Regularly updated binaries are provided for the following packages:
* Firefox
* Firefox ESR
* LLVM
* Rust

Binaries for NOIR (musl) -> https://github.com/kiss-community/repo-bin

### Installing binaries

* Modify `KISS_PATH` such that the `bin` repository takes priority over other repositories:

$ export KISS_PATH=/path/to/main/bin:$KISS_PATH

* The packages can now be installed by a simple [kiss b $PKG && kiss i $PKG] command.