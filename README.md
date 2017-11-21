# pyregrid_examples

This repository contains examples showing how to use pyregrid. This is a wrapper
around code written by Nic Hannah to input various commonly used earth system
model grids and prepare input grids suitable for use with the ESMF regridding
package. The intention is to regrid 2D spatial fields only, though they can have 
a time dimension

Regridding an input field is not an expensive operation, creating the input grids
and, particularly, the regridding weights are relatively much more time consuming.

The objective is to resuse this expensive information as much as possible.

These examples created the input grids and remapping weight outputs once, in 
the subdirectory esmf_files. These are then used by more than one mapping operation
in the various subdirectories.

To create a set of regridding weights for one of the grids, say 10 (1 deg MOM5 ocean
model grid):

```bash
cd esmf_files/10
bash README
```

To then use these regridding weights to regrid sea surface salinity data to the
MOM model grid:

```bash
cd sss/10
bash README
```
