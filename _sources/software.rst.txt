Software and Data Analysis
==========================

If utopia existed, we would download XAFS data directly into our brains and perform the processing and analysis simply by ingesting the raw data. Since utopia is a putative construct of theology and/or philosophy (depending on what you choose to believe in), we need software to turn raw x-ray absorption data into interpretable results.

Raw data, reduction, and repetition
-----------------------------------

"Data reduction" means something different for XAFS analysis than it does for machine learning. Reduction means getting raw absorption data ready for XANES and EXAFS analysis by:

1. Rebinning the data points onto a less dense grid to reduce the data size, get rid of unnecessary data points, and sometimes reduce noise.
2. Subtracting the pre-edge background to remove the effect of absorption from lower-energy edges and from other sources. At this step, for fluorescence-detected measurements, things like glitch removal (deglitching) and over-absorption (self-absorption) correction are also done.
3. Normalizing the data so that the edge jump (the difference between the pre-edge and the slowly decaying part of the post-edge) is 1.
4. Transforming the data from (photon) energy space (E-space) to (photoelectron) wavenumber space (k-space) for EXAFS analysis.

Which software?
---------------

If a real world closer to utopia than ours existed, it wouldn't matter which software we decided to use to process and analyze our data. In reality, several popular and unpopular analysis packages exist. The ones I support are ``Larch`` and ``RSXAP`` because they're what I know and I trust the people who develop them.

``Athena`` is a well-known XAFS analysis package that still exists for historical reasons. It's still actively maintained but really is just a legacy frontend for ``Larch`` written in an ancient language. If you know how to use the ``Larch`` GUI, then using ``Athena`` is basically the same deal.

``Larch`` is easy to set up and use since it runs on Python and is based on common, well-maintained modules like ``lmfit``. If your computer can run Python, it can probably run ``Larch``.

``RSXAP`` is a collection of spaghetti codes written in Fortran before my (and probably your) parents were born. ``RSXAP`` requires you to compile Fortran code yourself and so is a bitch to get running, but it has the advantage of running much faster than ``Larch``. This is largely because the EXAFS fitting backend in ``RSXAP`` (``RSFIT``) is parallelized while ``lmfit``, the backend for ``Larch``, isn't. The difference isn't huge for simple EXAFS fitting, but if you need to do multi-shell modelling that attempts to account for distant scattering paths and the effect of multiple-scattering, then you will suffer from the slowness of ``lmfit``, especially if you request Monte-Carlo error bars on your parameter estimates.
