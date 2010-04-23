This repository contains control files to build debian packages from 
the OpenAccess IC design data reference library.

In order to access the actual library one need at least to be registered at
si2.org.

The instruction in this guide is currently only tested with Ubuntu 9.10

Download
========

Go to the project page at OpenEDA http://www.si2.org/openeda.si2.org/project/showfiles.php?group_id=5#276. 

Download oaSrc_X.XpXXX_all.tar.gz, oaInc_X.XpXXX_all.tar.gz and oaDoc_X.XpXXX_all.tar.gz



Install
=======

Create a clone of liboa-deb

::

	git clone git://github.com/henjo/liboa-deb.git liboa-2.2p084

Create an oa directory in the root of the liboa-deb clone

::
	cd liboa-2.2p084
	mkdir oa

Unpack downloaded files

::
	cd oa
	tar zxf /path/to/downloads/oaSrc_X.XpXXX_all.tar.gz
	tar zxf /path/to/downloads/oaInc_X.XpXXX_all.tar.gz
	tar zxf /path/to/downloads/oaDoc_X.XpXXX_all.tar.gz
	cd ..

Apply patch

::
        cd oa
        patch -p1 <../patches/oa.diff

Build debs

::
	dpkg-buildpackage

If everything went well, install the fresh liboa debs

::
	cd ..
	sudo dpkg -i liboa*deb

