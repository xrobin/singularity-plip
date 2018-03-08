# Singularity container with PLIP (Protein-Ligand Interaction Profiler)

This is a [Singularity](http://singularity.lbl.gov/) container containing [Protein-Ligand Interaction Profiler (PLIP)](https://projects.biotec.tu-dresden.de/plip-web/plip/index).

It requires a recent version of Singularity on Linux.

## To pull a pre-built container:

[The container is available on Singularity-Hub](https://www.singularity-hub.org/collections/704) with [additional usage details](https://www.singularity-hub.org/collections/704/usage) and can be easily pulled and run on a machine without root:

```bash
singularity pull --name "plip.simg" shub://xrobin/singularity-plip
```

## To run PLIP inside the container

```bash
singularity run plip.simg
# Or the shorter syntax:
./plip.simg
```

### Useful commands:

```bash
./plip.simg --help
./plip.simg -i 4HVD -vx
```

For more PLIP usage, see [the PLIP repository on GitHub](https://github.com/ssalentin/plip) and the [DOCUMENTATION file](https://github.com/ssalentin/plip/blob/stable/DOCUMENTATION.md).

## To build this container from scratch execute this (requires root):

```bash
git clone https://github.com/xrobin/singularity-plip.git
cd singularity-plip
sudo singularity build plip.simg Singularity
```

Note: The compilation of OpenBabel requires about 1.5 GB of memory.
