# Singularity container with PLIP (Protein-Ligand Interaction Profiler)

This is a [Singularity](http://singularity.lbl.gov/) container containing [Protein-Ligand Interaction Profiler (PLIP)](https://projects.biotec.tu-dresden.de/plip-web/plip/index).

It requires a recent version of Singularity on Linux.

## To pull a pre-built container:
```bash
singularity pull shub://xrobin/singularity-plip
```

[The container is available on Singularity-Hub](https://www.singularity-hub.org/collections/704) with [additional usage details](https://www.singularity-hub.org/collections/704/usage)

## To build this container from scratch execute this (requires root):

```bash
git clone https://github.com/xrobin/singularity-plip.git
cd singularity-plip
sudo singularity build plip.simg Singularity
```

Note: The compilation of OpenBabel requires about 1.5 GB of memory.

## To run PLIP inside the container

```bash
singularity run shub://xrobin/singularity-plip
singularity run xrobin-singularity-plip-master.simg
```

### You can rename the file for easier use

```bash
mv xrobin-singularity-plip-master.simg plip.simg
singularity run plip.simg --help
```

### Or use the shorter syntax:

This 

```bash
./plip.simg --help
./plip.simg -i 4HVD -vx
```
