Installation
===================================

Install pip
-------------------------------------------
pip is already installed if you are using Python 2 >=2.7.9 or Python 3 >=3.4 downloaded
from `python.org <python.org>`_ or if you are working in a Virtual Environment created by
`virtualenv <https://packaging.python.org/key_projects/#virtualenv>`_
or `pyvenv <https://packaging.python.org/key_projects/#venv>`_. Just make sure to upgrade
pip. You must first install pip following the instructions: `https://pypi.python.org/pypi/pip <https://pypi.python.org/pypi/pip>`_


Use pip3 to install RSeQC-GSI (v3.0.1 or newer)
-----------------------------------------------

RSeQC-GSI is not available from the Python package index at pypi.org.

Instead, use ``setup.py sdist`` to create a source distribution, and pip3 to install with dependencies as follows:

::

   mkdir $TMPDIR
   python3 setup.py sdist -d $TMPDIR
   cd $TMPDIR
   pip3 install RSeQC-GSI-${VERSION}.tar.gz

To avoid the need to modify the system Python, the above may be done in a `virtual environment <https://docs.python.org/3/tutorial/venv.html>`_.

Use pip3 to install RSeQC (v3.0.0)
----------------------------------

::

 pip3  install RSeQC
 
Use pip2 to install RSeQC (v2.6.5 or older)
--------------------------------------------

::

 pip2  install RSeQC==2.6.5

  
Install RSeQC from source code (Not recommended)
----------------------------------------------------
 
Install RSeQC (Example)::
 
 tar zxf RSeQC-VERSION.tar.gz
  
 cd RSeQC-VERSION
 
 #type 'python setup.py install --help' to see options
 python setup.py install	#Note this requires root privilege
 or
 python setup.py install --root=/home/user/XXX/		#install RSeQC to user specificed location, does NOT require root privilege
 
 #This is only an example. Change path according to your system configuration
 export PYTHONPATH=/home/user/lib/python2.7/site-packages:$PYTHONPATH 
 
 #This is only an example. Change path according to your system configuration
 export PATH=/home/user/bin:$PATH

Finally, type: python -c 'from qcmodule import SAM'. If no error message comes out, RSeQC
modules have been installed successfully. 
