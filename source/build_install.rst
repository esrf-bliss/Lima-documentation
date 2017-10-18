.. _build_installation:

Build and Install
-----------------

Using scripts
^^^^^^^^^^^^^
the **install** scripts will run cmake, compile and install. 

It accepts input arguments (see below) but it also uses a configuration file  **scripts/config.txt**. Feel free to update this file for setting a permanent configuration for your own installation.

Linux::

     [sudo] install.sh
     [--git]
     [--prefix=<desired installation path>]
     [--python-packages=<desired python installation path>]
     [options]

Windows::

  install.bat
  [--prefix=<desired installation path>]
  [--python-packages=<desired python installation path>]
  [options]

The **--git** (Linux only) option cab be used to clone the required submodules as a prerequisite. Otherwise you should install the submodules with git commands, for instance::

 $ git submodule init third-party/Processlib
 $ git submodule init camera/basler
 $ git submodule init applications/tango/python
 $ git submodule update


Options are <camera-name> <saving-format> python pytango-server:

- camera-name::

  andor|andor3|basler|prosilica|adsc|mythen3|ueye|xh|xspress3|ultra|
  xpad|mythen|pco|marccd|pointgrey|imxpad|dexela|merlin|v4l2|
  eiger|pixirad|hexitec|aviex|roperscientific|rayonixhs|espia|maxipix|frelon

- saving-format::

  cbf|nxs|fits|edfgz|edflz4|tiff|hdf5

- python: to compile python module

- pytango-server: to install the PyTango_ server

Example::

 $ sudo install.sh --git 
                 --prefix=./install 
                 --python-packages=./install/python
                 tiff basler python pytango-server

Using cmake
^^^^^^^^^^^

Install first the project submodules::

 $ git submodule init third-party/Processlib
 $ git submodule init camera/basler
 $ git submodule init applications/tango/python
 $ git submodule update

Run cmake in the build directory::

 $ mkdir build
 $ cd build
 $ cmake ..
     [-G "Visual Studio 9 2008 Win64" | -G "Visual Studio 9 2008" | -G "Unix Makefiles"] 
     [-DCMAKE_INSTALL_PREFIX=<desired installation path>]
     [-DPYTHON_SITE_PACKAGES_DIR=<desired python installation path>]     
     -DLIMA_ENABLE_TIFF=true
     -DLIMACAMERA_BASLER=true
     -DLIMA_ENABLE_PYTANGO_SERVER=true
     -DLIMA_ENABLE_PYTHON=true

Then compile and install::

 $ cmake --build
 $ sudo cmake --build --target install


May you need to update your environment?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you have changed the default destination path for both libraries and python modules you should update
your environment variables.

For Linux:

.. code-block:: sh

  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<my-new-install-dir>/Lima/lib
  
  export PYTHONPATH=$PYTHONPATH:<my-new-install-dir>

For Windows:

Update the system wide variables PATH for the libraries and PYTHONPATH for python.


.. _PyTango: http://github.com/tango-cs/pytango
