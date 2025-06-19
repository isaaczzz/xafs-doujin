Data
====

.. admonition:: tl;dr

    This section covers how to pull raw data into Larix and how to clean up raw data for XANES and EXAFS analysis. Raw quick-XAFS data from SPring-8 BL01B1 are used as examples.

The example data were recorded at SPring-8 BL01B1 during the 2024B-III cycle (early-2025). The sample of interest is activated CuZn-MFU-4\ `l`, measured in a He cryostat at 10 K, and the reference sample is Cu foil at room temperature. The samples were measured in transmission geometry and the beamline was operated in quick-XAFS mode, resulting in a very high number of data points.

The basic procedure
-------------------

.. image:: /img/work_shigoto_osame_man.png
    :alt: a guy shoving paperwork into a box
    :width: 25%
    :align: right

"Data reduction" means something different for XAFS analysis than it does for machine learning. Reduction means getting raw absorption data ready for XANES and EXAFS analysis by:

1. Rebinning the data points onto a less dense grid to reduce the data size, get rid of unnecessary data points, and sometimes reduce noise.
2. Merging individual scans.
3. Subtracting the pre-edge background to remove the effect of absorption from lower-energy edges and from other sources. At this step, for fluorescence-detected measurements, things like glitch removal (deglitching) and over-absorption (self-absorption) correction are also done.
4. Normalizing the data so that the edge jump (the difference between the pre-edge and the slowly decaying part of the post-edge) is 1.
5. Calibrating the photon energy scale according to a standard. For example, for the Cu K-edge, the scale is aligned so that the first inflection point of a metallic Cu spectrum appears at 8980.3 eV.
6. Transforming the data from (photon) energy space (E-space) to (photoelectron) wavenumber space (k-space) for EXAFS analysis.

Importing data into Larix
-------------------------

.. image:: /img/animal_mogura_kouji2.png
    :alt: a mole wearing a hardhat
    :width: 50%
    :align: center

.. warning::

    These subsections are under construction.

Rebinning
---------

Merging
-------

Pre-edge background
-------------------

Normalization
-------------

Energy calibration
------------------

It's my EXAFS and I need it now!
--------------------------------