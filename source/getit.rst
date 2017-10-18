.. _getit:


Get It !!
---------
As Lima is not packaged,the only way for now is to retreive it from the git repository.

For both Linux and Windows we recommend to use the git tools.

For Linux::
  
Install Git_ package if your linux distribution did not.


For Windows::

Install Git_ first. Then use the git-bash tool with linux-like command line commands.


Command to get all sources
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: bash 

  seb@pcbliss01:~/$ git clone --recursive git://github.com/esrf-bliss/Lima.git

Commands for a minimum checkout to get all source needed for a particular camera
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^  

.. code-block:: bash

  seb@pcbliss01:~/$ git clone git://github.com/esrf-bliss/Lima.git
  seb@pcbliss01:~/$ cd Lima
  seb@pcbliss01:~/Lima$ git submodule init third-party/Processlib third-party/Sps third-party/libconfig
  seb@pcbliss01:~/Lima$ git submodule init camera/CAMERA_YOU_WANT_TO_COMPILE
  seb@pcbliss01:~/Lima$ git submodule update

In addition (but optional) you can get the **TANGO** python device servers, so update your git clone again:

 .. code-block:: bash

  seb@pcbliss01:~/Lima$ git submodule init application/tango/python
  seb@pcbliss01:~/Lima$ git submodule update

 
Particular version?
^^^^^^^^^^^^^^^^^^^
Stable versions of lima are tracked via Git branches and Git tags. So you can retrieve any particular version using git tools.
Please refer to the release notes document `release notes`_ , for more information of the latest release and tags.

For instance if you want to get version 1.7.1 of Lima core, do:

.. code-block:: bash

  seb@pcbliss01:~/Lima$ git checkout core-1.7.1
  seb@pcbliss01:~/Lima$ git submodule init
  seb@pcbliss01:~/Lima$ git submodule update


.. _git: https://git-scm.com
.. _release notes: ./ReleaseNotes.txt
