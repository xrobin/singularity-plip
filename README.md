# Singularity container with PLIP (Protein-Ligand Interaction Profiler)

https://projects.biotec.tu-dresden.de/plip-web/plip/index

## To pull a pre-built container:
```bash
singularity pull shub://xrobin/singularity-plip
```

## To build this container from scratch execute this:

```bash
sudo singularity build singularity-plip.img Singularity
```

## To run PLIP inside the container

```bash
singularity run singularity-plip.img
singularity run singularity-plip.img --help
```



