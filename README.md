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