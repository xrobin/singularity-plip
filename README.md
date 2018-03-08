# Singularity container with PLIP (Protein-Ligand Interaction Profiler)

This is a [singularity](http://singularity.lbl.gov/) container containing [Protein-Ligand Interaction Profiler (PLIP)](https://projects.biotec.tu-dresden.de/plip-web/plip/index).

## To pull a pre-built container:
```bash
singularity pull shub://xrobin/singularity-plip
```

## To build this container from scratch execute this:

```bash
sudo singularity build plip.simg Singularity
```

Note: The compilation of OpenBabel requires about 1.5 GB of memory.

## To run PLIP inside the container

```bash
singularity run plip.simg
singularity run plip.simg --help
# Or the shorter syntax:
./plip.simg --help
./plip.simg -i 4HVD -vx
```



