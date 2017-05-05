
# Three Dimensional Optimal Spectral Extraction (TDOSE)

README for the optimal spectral extraction software presented by Schmidt et al. (some day)

TDOSE will be presented in a forthcoming publication (Schmidt et al.), until this publication has apparead, please references the TDOSE GitHub repository (https://github.com/kasperschmidt/GLASSinspectionGUIs) if TDOSE is used. 


## Table of Content

- [Description](#description)
- [Script Overview](#script-overview)
- [Dependencies and Requirements](#dependencies-and-requirements)
  - [Standard Packages](#standard-packages)
  - [Special Packages](#special-packages)
- [Running TDOSE](#running-tdose)
  - [Default Run](#default-run)
- [Main Keywords in TDOSE](#main-keywords-in-tdose)
- [References](#references)
- [Schematic Overview of TDOSE](#schematic-overview-of-tdose)

## Description

TBD

## Script Overview

The following gives and overview of the scripts provided with the TDOSE code

- `tdose_parameters.txt`
  - Text file containig the paramter setup for the TDOSE functions and routines.
- `tdose_??.py`
  - Wrapper...

## Dependencies and Requirements

The code is written in python and uses a wide range of default packages included in standard installations of python. A few special packages as outlined below, needs to be installed on top of that to get TDOSE running.

### Standard Packages

The following standard packages are imported in one or more of the TDOSE scripts and therefore needs to be available to run TDOSE successfully: 
`pdb`,
`sys`,
`time`,
`glob`,
`numpy`,
`scipy`,
`shutil`,
`pyfits`,
`astropy`,
`datetime`,
`warnings`,
`matplotlib`,
`subprocess`, and
`collections`.

### Special Packages

No special Python packages are required to run TDOSE so far.


## Running TDOSE

In the following a few useful examples of how to produce outputs using the TDOSE scripts are given. For examples on how to run individual pieces of code, please refer to the individual code headers.

### Default Run

TBD

### Generate Mock Data Cube

```
import tdose_build_mock_cube as tbmc
sourcecat       = 'mock_cube_sourcecat161213_all.fits'
cube_dim        = [100,200,150]
noisetype       = 'gauss'
noise_gauss_std = 0.03
psf             = 'moffat'
psf_param       = [10.0,[1.1,1.3,1.5]]
outputcube      = tbmc.build_cube(sourcecat,cube_dim=cube_dim,clobber=False,noisetype=noise,noise_gauss_std=noise_gauss_std,psf=psf,psf_param=psf_param)

```
Here, the `sourcecat` is a fits catalog containing x and y pixel positions, a flux scale, indicators of the source (model) types and spectral (model) types. For further details see header of `tbmc.build_cube()`. The `psf*` paramters define the psf model to convolve the cube with using `tdose_utilities.gen_psfed_cube()`.

## Main Keywords in TDOSE 

TBD

## References 

- Kamann, Wisotzki and Roth (2013)

## Schematic Overview of TDOSE
TDOSE_illustration.pdf (displayed below) presents a schemative overview of the different elements, functions and routines making up TDOSE.

![schematicTDOSEoverview](TDOSE_illustration.pdf)


