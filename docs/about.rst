Pycroscopy Package
==================

**Python Package for scientific analysis of nanoscience data**

.. attention::

   Pycroscopy is undergoing a major reorganization and change to the scope and nature of the package.

.. note::
   **Weekly Hackathons**

   We run weekly hackathons to develop the pycroscopy ecosystem of python packages.
   Hackathons are held every Friday 3-5PM USA Eastern time.
   The requirements for participation are: knowledge of python, git,
   and the basic structure and philosophy of the pycroscopy ecosystem (available through documentation).
   If you would like to participate, please email us at vasudevanrk *at* ornl.gov

Reimagined Package
~~~~~~~~~~~~~~~~~~

.. attention::

   This version of the pycroscopy python package is under development and is not
   yet available to download or use.

* Code in this package is meant to be useful for multiple scientific domains or applications.
* See `scientific research enabled by pycroscopy <https://pycroscopy.github.io/pycroscopy/papers_conferences.html>`_.
* The upcoming version of pycroscopy is being thoroughly restructured and will be substantially different to current or prior versions.
  Differences between the upcoming and existing legacy versions are largely centered in how data is handled:

  * The reimagined pycroscopy package will **not** deal with data files.

    * `SciFiReaders <https://pycroscopy.github.io/SciFiReaders/about.html>`_
      provides ``Readers`` to extract data and metadata from scientific data files into python objects in memory.
      This is unlike ``Translators`` that were part of pycroscopy that wrote the extracted data into
      `USID – Universal Spectroscopy and Imaging and Data <pycroscopy.github.io/usid/about.html>`_
      formatted HDF5 files.
    * Input and output data would be exchanged in the form of ``sidpy.Dataset`` objects
      rather than HDF5 Datasets in a file
    * Users interested in saving results of analyses in ``pycroscopy`` are encouraged to use
      their choice of `pyNSID <https://pycroscopy.github.io/pyNSID/index.html>`_
      or `pyUSID <https://pycroscopy.github.io/pyUSID/about.html>`_ to write their data to files.
  * pycroscopy will not force the use of specific computational backends like ``joblib``, ``mpi4py``, ``dask``, etc.

* The upcoming version of pycroscopy will be `organized <https://github.com/pycroscopy/pycroscopy/issues/245>`_ as follows:

  * ``learn`` - machine and deep learning tools
  * ``stats`` - statistics tools
  * ``image`` - image analysis and processing tools
  * ``signal`` - signal processing and analysis tools
  * ``corr`` - tools to correlate datasets from multiple sources (images with spectra, simulation with experiment, experiments with machine learning, etc.)
  * ``viz`` - visualization tools and dashboards

* The source code is available under the `phoenix <https://github.com/pycroscopy/pycroscopy/tree/phoenix>`_ branch.

Legacy Package
~~~~~~~~~~~~~~

.. attention::

   `V 0.60.7 <https://pypi.org/project/pyCroscopy/>`_ is the last version of
   the legacy iteration of pycroscopy available through pip and conda.

For those interested in the older version, please visit the legacy branch, which will not be amended from hereon. The new version is under development in the 'phoenix' branch, which will be shifted to master in due course.

* The pycroscopy package has so far focused on providing standardized solutions for processing, analyzing, and visualizing multidimensional imaging and spectroscopy data.
* The legacy iteration of pycroscopy used a data and file-centric approach based on the
  `USID – Universal Spectroscopy and Imaging and Data <pycroscopy.github.io/usid/about.html>`_ model
  wherein the raw data collected from the microscope, results from analysis and processing routines are all written to
  standardized hierarchical data format (HDF5) files for traceability, reproducibility, and provenance.

  * pycroscopy therefore used `pyUSID <https://pycroscopy.github.io/pyUSID/about.html>`_
    which provides tools to read, write, visualize, and process USID data stored in HDF5 files.
* The following provides an overview of the existing organization of the pycroscopy
  package and how these capabilities have been / will be made available in the reimagined pycroscopy:

  * ``analysis``

    * Atom finding functions - will be made available under the ``image`` subpackage of the reimagined pycroscopy
    * Band Excitation and General-mode specific functional fitting that have been moved to `BGlib <https://pycroscopy.github.io/BGlib/index.html>`_
  * ``processing``

    * Unsupervised machine learning wrappers - ``Cluster``, ``Decomposition``, ``SVD`` - these will be available via the ``learn`` subpackage of the reimagined pycroscopy.
    * ``fft``, ``SignalFilter`` will be available via the ``signal`` subpackage of the reimagined pycroscopy
    * ``histogram``, ``image_processing`` will be made available as well.
  * ``io``

    * Deprecated utility classes like ``HDFWriter``, ``VirtualDataGroup`` and ``VirtualDataset``
    * ``translators`` from proprietary data formats to USID formatted HDF5 files

      * Band Excitation and General-mode specific translators have been moved to `BGlib <https://github.com/pycroscopy/BGlib/tree/master/BGlib/be/translators>`_.
      * Others have now been refactored to ``Readers`` in `SciFiReaders <https://pycroscopy.github.io/SciFiReaders/about.html>`_
  * ``viz``

    * Band Excitation visualizers - have been moved to ``BGLib``
    * Clustering visualization - will be moved to ``viz`` in the new pycroscopy
    * Image cleaning visualization - will be moved to ``viz`` in the new pycroscopy

* `V 0.60.7 <https://pypi.org/project/pyCroscopy/>`_ is the last version of the
  legacy iteration of pycroscopy available through pip and conda.
  All future versions will be on the reimagined package described above.
* The source code for the legacy iteration always be available on the
  `legacy <https://github.com/pycroscopy/pycroscopy/tree/legacy>`_ branch.