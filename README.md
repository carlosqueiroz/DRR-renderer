### Simple code to generate Digitally Reconstructed Radiographs from MetaImage (.mhd) CT data

The code generates DRR images in a transparent and simple manner, the user can tune every parameter, such as view point angles, distance to CT, intrinsics of DRR view, step of raytracing, ...
The DRR generation takes 2 seconds on a Intel(R) Core(TM) i7-2600 CPU @ 3.40GHz 8 cores on Ubuntu 14.10.
The .mhd standard is not fixed, therefore it might happen that the CT header use other terms than the ones used in our code for header element such as Element Spacing,... This should be check before running the code.

#### References

[![DOI](https://zenodo.org/badge/88970535.svg)](https://zenodo.org/badge/latestdoi/88970535)
https://zenodo.org/badge/latestdoi/88970535

Stefan, P., Habert, S., Winkler, A., Lazarovici, M., Fürmetz, J., Eck, U., & Navab, N. (2018). A radiation-free mixed-reality training environment and assessment concept for C-arm-based surgery. International journal of computer assisted radiology and surgery, 13(9), 1335-1344.

### Sample Image

![sample chest DRR](/sample/sample0.png)

### Build instructions

* build DRR generator with docker

```
    docker-compose build && docker-compose up -d 
    docker-compose exec drr bash
```

* Generate DRR with built docker, given mhd and raw input paths, output png path and additional parameters (see main.cpp for detail).

```
    DRRgenerator /sample/drr.mhd /sample/drr.zraw /sample/out.png 0 0 0 -90 0 0 0 512 512 0 -1000 1500 1500 256 256
```
