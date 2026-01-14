Converter code. 

# Installing Rivet
https://gitlab.com/hepcedar/rivet/-/blob/release-4-1-x/doc/tutorials/installation.md


Commented out this section of the bootstrap

```
## Make & activate installation directory as a Python venv, set up for bash completion scripts and multi-arch libs
#if [[ "$USE_VENV" == 1 ]]; then
    #$PYTHON_EXE -m venv $INSTALL_PREFIX
    #source $INSTALL_PREFIX/bin/activate
    #pip install --upgrade pip
#fi
```

# Testing with Rivet

https://gitlab.com/hepcedar/rivet

https://gitlab.com/hepcedar/rivet/-/blob/release-4-1-x/doc/tutorials/docker.md

First, 

`docker pull hepstore/rivet:4.1.2`

Then try

`docker run -it --rm hepstore/rivet:4.1.2`

Then I'm in the `rivet` environment!

In another terminal, I run

`docker container ls`

to get a list of the containers. From the `NAMES` field, I grab the name of the container instance and then I can copy in files with something like

`docker cp test_output.hepmc3 admiring_visvesvaraya:/work/`

Right now, in the container I get a beam mismatch error when I run

`rivet -a MC_JETS ./test_output.hepmc3`

# Testing with ATLAS

From Tomasz Procter:

No worries, as far as I'm aware that opendata entry exists as a placeholder/reference for the atlas open data hepmc files. To actually dowload them, you need to use atlas opendata magic 

(https://opendata.atlas.cern/docs/data/atlasopenmagic)

If you want a quick supply of small files for testing, then maybe I could suggest

https://rivetval.web.cern.ch/rivetval/HEPMC 

(these are the files used for rivet validation/CI), you probably want some of the LHC-*-13-* ones.
They're only a 1000 events each so much easier for getting to grips with quickly. 

