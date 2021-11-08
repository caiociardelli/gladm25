# SphModel
-----------------------

`SphModel` is a subpackage of `SphGLLTools`, a toolbox for visualization, processing, sharing, and spherical harmonics analysis of tomographic models defined on GLL meshes.

Author: Caio Ciardelli

If you use SphModel, please, cite the following paper:

Ciardelli, C., Bozdağ, E., Peter, D., and van der Lee, S., 2021. SphGLLTools: A toolbox for visualization of large seismic model files based on 3D spectral-element meshes. Computer & Geosciences, submitted.

# GLAD-M25
-----------------------

Please, also make sure to cite the authors of GLAD-M25:

Lei, W., Ruan, Y., Bozdağ, E., Peter, D., Lefebvre, M., Komatitsch, D., Tromp, J., Hill, J., Podhorszki, N., Pugmire, D., 2020. Global adjoint tomography—model glad-m25. Geophysical Journal International 223, 1–21. URL: https://doi.org/10.1093/gji/ggaa253.

## Installation
-----------------------

`SphModel` requires no installation. Just take the following steps:

1. Make sure you have:

* GCC 5.5.0 or greater;
* Python 2.7.12 or greater;
* GMT 6.0.0 or greater;

2. Download the latest version of GLAD-M25 at [SphModel:GLAD-M25](https://github.com/caiociardelli/gladm25).

3. Untar the crustal block model using:

```sh
$ for file in crust/*tar.xz; do tar -xvJf "$file" -C crust/; done
```

4. Run the Makefile with:

```sh
$ make
```

## Usage
-----------------------

All routines have a help menu that shows up whenever you run them with no or with a wrong number of command-line parameters. The
same menu is also at the beginning of each source code. For more details, please, refer to the manual of `SphGLLTools`.

## Development
-----------------------

Development is hosted on GitHub at [SphGLLTools](https://github.com/caiociardelli/sphglltools).

## Model parametrization
-----------------------

This parametrization includes Vpv (km/s), Vph (km/s), Vsv (km/s), Vsh (km/s), Eta, and Rho (g/cm^3). The perturbations for the default parameters, as well as some derived parameters such as the isotropic velocities (Vp and Vs), the bulk sound speed, the Vp/Vs ratios, and the transverse isotropy, can also be computed using these routines.

The model is composed of four layers:

Zone 1: Represents the crust using a block model. The horizontal resolution is 0.5 degrees, both in latitude and longitude, and the vertical resolution is 1 km. This zone stretches from 5 km above sea level to 80 km depth.

Zone 2: Represents the upper mantle using a combination of spherical harmonics of various degrees and six cubic B-splines. This zone stretches from 80 km to 410 km depth.

Zone 3: Represents the transition zone using a combination of spherical harmonics of various degrees and five cubic B-splines. This zone stretches from 410 km to 650 km depth.

Zone 4: Represents the lower mantle using a combination of spherical harmonics of various degrees and fourteen cubic B-splines. This zone stretches from 650 km to 2891 km depth.

## Plate boundaries
-----------------------

The plate boundaries are from http://geoscience.wisc.edu/~chuck/MORVEL/citation.html (access on June 20, 2020)

DeMets, C., Gordon, R. G., and Argus, D. F., 2010. Geologically current plate motions, Geophysical Journal International, v. 181, no. 1, p. 1-80, doi: 10.1111/j.1365-246X.2009.04491.x

## Hot spots
-----------------------

The hot spot locations are from the table compiled by Don L. Anderson using multiple sources, available at http://www.mantleplumes.org/CompleateHotspot.html (access on November 27, 2020)

## Contact
-----------------------

If you have any questions, suggestions, and bug reports, you can email *caio.ciardelli@gmail.com*

