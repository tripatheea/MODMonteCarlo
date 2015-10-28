# MODMonteCarlo




### Note to self:

Things to do:

- Download Pythia.
- Extract everything.
- Configure it to have sharing enabled using: `./configure --enable-shared`.
- Compile everything with `make`.
- Add the following runtime variables to `~/.bashrc`.
  
  `export PYTHIA8=/home/aashish/pythia8212`

  `export PYTHIA8DATA=$PYTHIA8/share/Pythia8/xmldoc`
  
  `export LD_LIBRARY_PATH=/home/aashish/pythia8212/lib`

- Compile your file with something like the following:

  `g++ -std=c++11 -I$PYTHIA8/include generateEvents.cc -o generateEvents -L$PYTHIA8/lib -lpythia8 -ldl`


## Delphes
- Looks like you need ROOT 6 for Delphes. Not that you should be using ROOT 5. The only reason it matters is that, for some werid unexplained reason, the **default** version in my Ubuntu distro seems to be 5. Just typing in root loads ROOT 5. So to make sure that during Delphes' compilation, classes from ROOT 6 are loaded instead of from ROOT 5, you need to do the whole `. bin/thisroot.sh` thing. An alternative (and much better) way to do this is remove ROOT 5 and install ROOT 6 in something like `/usr/local/` but a superposition of laziness and `if it ain't broke, don't fix it` is preventing me from doing that. Do that asap.



### Troubleshooting:
  `/usr/bin/ld: cannot find -lPythia` can be fixed by adding `export LD_LIBRARY_PATH=/home/aashish/pythia8212/lib` to your environment variables.

  Sometimes adding them to `~/.bashrc~ doesn't work. So enter the following manually:
  `export LD_LIBRARY_PATH=/home/aashish/hepmc/lib:/home/aashish/pythia8212/lib`