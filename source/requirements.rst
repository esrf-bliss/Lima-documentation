.. _requirements:


Requirements
------------

You need to install some tools and libraries for building Lima for both windows and Linux.

Build dependencies:

- gcc for Linux
- Visual Studio 2008 (or Express) for Windows
- git_
- cmake_ >= 3
- gsl_: For windows, download the esrf binary package `gsl-windows`_ and install it under "c:\program files\" 
     

**Python** dependencies:

Lima_ is compatible with python 2 and 3 (Linux only).

- numpy_ >= 1.1
- sip_ >= 4.2

The following requirements are optional.

Saving format dependencies:

- tiff_
- libz_
- cbf_
- hdf5_
- ccfits_
- lz4_ = 1.7.x
- libconfig_

PyTango_ server dependencies:

- PyTango_
- libtango_

.. _git: https://git-scm.com
.. _Python: http://python.org
.. _Lima: http://lima.blissgarden.org
.. _gsl: https://www.gnu.org/software/gsl
.. _gsl-windows:  http://ftp.esrf.fr/pub/bliss/lima/GSL-windows.zip
.. _cmake: https://cmake.org

.. _Tango: http://tango-control.org
.. _PyTango: http://github.com/tango-cs/pytango
.. _libtango: http://tango-controls.org/downloads/source

.. _numpy: http://pypi.python.org/pypi/numpy
.. _sip: https://www.riverbankcomputing.com/software/sip

.. _tiff: http://www.libtiff.org/
.. _libz: https://zlib.net/
.. _cbf: http://www.bernstein-plus-sons.com/software/CBF
.. _hdf5: https://support.hdfgroup.org/HDF5
.. _ccfits: https://heasarc.gsfc.nasa.gov/fitsio/ccfits
.. _lz4: https://lz4.github.io/lz4
.. _libconfig: http://www.hyperrealm.com/libconfig
