Data
====

This section covers how to pull raw data into Larch and how to clean up raw data for XANES and EXAFS analysis.

The basic procedure
-------------------

.. image:: /img/work_shigoto_osame_man.png
    :alt: a guy shoving paperwork into a box
    :width: 25%
    :align: right

"Data reduction" means something different for XAFS analysis than it does for machine learning. Reduction means getting raw absorption data ready for XANES and EXAFS analysis by:

1. Rebinning the data points onto a less dense grid to reduce the data size, get rid of unnecessary data points, and sometimes reduce noise.
2. Subtracting the pre-edge background to remove the effect of absorption from lower-energy edges and from other sources. At this step, for fluorescence-detected measurements, things like glitch removal (deglitching) and over-absorption (self-absorption) correction are also done.
3. Normalizing the data so that the edge jump (the difference between the pre-edge and the slowly decaying part of the post-edge) is 1.
4. Transforming the data from (photon) energy space (E-space) to (photoelectron) wavenumber space (k-space) for EXAFS analysis.