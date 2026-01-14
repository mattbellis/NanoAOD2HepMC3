Converter code. 


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
