mazurka-plugins
===============

mazurka vamp plugins, originally found in http://sv.mazurka.org.uk/

## Pre-installation

Two dependencies are needed for building: **Vamp plugin SDK** and the **FFTW** library.

### Debian

In Debian these can be installed directly from the distribution official repositories. `vamp-plugin-sdk` is also available from deb-multimedia.

```
sudo apt-get install vamp-plugin-sdk libfftw3-dev
```

## Build and installation

* run `make` from `src` directory
* copy `mazurka-plugins.so` from `src` to Vamp plugin directory (e.g. `/home/USER/vamp/`)
