Software
========

.. admonition:: tl;dr

    This section shows you how to install Larch for XAFS analysis. If you already know how to use Conda to install Python modules on your system, you can skip most of this section. Just install ``xraylarch``.

.. image:: /img/computer_doctor_woman.png
    :alt: a female scientist deciding which xafs software to use
    :width: 25%
    :align: right

If a real world closer to utopia than ours existed, it wouldn't matter which software we decided to use to process and analyze our data. In reality, several popular and unpopular analysis packages exist. The ones I support are `Larch`_ and `RSXAP`_ because they're what I know and I trust the people who develop them.

Larch is easy to set up and use, so it's what I'll show you how to use here. While, in terms of speed, RSXAP scales better to complicated fitting jobs than Larch does, Larch's UI and ease-of-use make it convenient for on-the-fly data analysis at the beamline. Because it's a more modern project (RSXAP's Fortran codebase is older than my parents), Larch also has a ton of quality-of-life features and powerful capabilities that RSXAP lacks.

Athena is another well-known analysis package that you'll see frequently cited in papers from XAFS experts and amateurs alike. In ye olden times, Athena was a graphical frontend for the IFEFFIT code, which was written in Fortran. With the advent of Larch's more maintainable and reasonably performant Python codebase, Athena now uses Larch as its backend, making Larch and Athena the same tool with different coats of paint.\ [#]_ The only difference is that Larix, the purpose-built GUI for Larch, is written in Python and is therefore easier to reproducibly install on different platforms. 

Wrangling Pythons
-----------------

.. image:: /img/shinnen_aisatsu_hebi_medousa_couple.png
    :alt: hebi medousa couple
    :width: 37.5%
    :align: left

Larch is programmed in Python and requires a local Python installation to run.

I recommend using `Miniconda`_ as your local Python installation since it allows you to create compartmentalized virtual enviroments for different projects.\ [#]_  If you already have an existing Miniconda, Anaconda, or Micromamba installation, you can adjust these instructions accordingly.\ [#]_

`Install Miniconda`_ by following the official instructions for your operating system. On Linux, Miniconda (or a similar package) is probably available in your distribution's repositories.\ [#]_

.. figure:: /img/anaconda_windows_installer.png
    :align: center

    Recommended installation options for Miniconda on Windows.

Unless you have a reason not to, it's convenient to register Miniconda as the primary Python 3 provider for your system. On macOS or Linux, you may need to modify your system's environment variables to achieve this.


`Conda`_ is the built-in package and Python environment manager for Miniconda. We'll be calling it a few times to install Larch.\ [#]_

Installing Larch
----------------

.. .. image:: /img/job_technical_evangelist_ai_woman.png
..     :alt: a woman introducing conda to a man
..     :width: 25%
..     :align: right

Create a new virtual environment for Larch, then activate the new virtual environment:

.. code-block::

    conda create -n xraylarch
    conda activate xraylarch

Install ``xraylarch``:

.. code-block::

    conda install -yc conda-forge xraylarch

If you want to create desktop shortcuts for the Larch applications, run

.. code-block::

    larch -m

Alternatively, you can launch the Larch applications by typing their names into an Anaconda Prompt with the ``xraylarch`` Conda environment active. For example, use the ``larix`` command to launch `Larix`_.

.. note::

    The ``xraylarch`` environment must be active when you attempt to launch Larch's applications from Anaconda Prompt.

The Larch CLI
-------------

Outside of Larix, Larch can also be used via a CLI. Simply open an Anaconda Prompt window with the ``xraylarch`` environment active and type `larch` to enter the Larch console.

More practically, you can access ``larch`` as a Python module. Things like simultaneous fitting, batch analysis, and more complicated data manipulations are probably easier to do by `programming with Larch from Python`_ rather than by using the graphical interface provided by Larix.

When I need to use Larch for more than just checking data at the beamline, I prefer concatenating all of my data into a Larch project file using Larix, then processing my data using Python scripts or a Jupyter notebook.

.. [#] Larch and IFEFFIT were both developed by `Matt Newville`_, a spectroscopist, beamline scientist, and geophysicist, who also developed the Python fitting module LMFIT.
.. [#] macOS comes with Python pre-installed. Despite this, I recommend using Miniconda anyway, since doing so will keep your system's Python installation free of unnecessary packages and will allow you to use Conda to automatically install dependencies.
.. [#] Larch is also available from PyPI if you don't want to use the Anaconda ecosystem, but good luck resolving weird dependency issues if you decide to go this way.
.. [#] ...but if you're using Linux, you probably don't need me to tell you about any of this.
.. [#] `Mamba`_ is an optimized, more performant version of Conda that you can use as a drop-in replacement. However, Conda now uses mamba as a backend, so many of the speedups of mamba are already implicitly part of Conda. You can install mamba by running ``conda install -y mamba``.

.. _Larch: https://xraypy.github.io/xraylarch/
.. _RSXAP: https://lise.lbl.gov/RSXAP/
.. _Install Miniconda: https://www.anaconda.com/docs/getting-started/miniconda/install#linux-terminal-installer
.. _Miniconda: https://www.anaconda.com/docs/getting-started/miniconda/main
.. _conda: https://docs.conda.io/en/latest/
.. _Larix: https://xraypy.github.io/xraylarch/larix.html
.. _Mamba: https://mamba.readthedocs.io/en/latest/user_guide/mamba.html
.. _Larch GUI: https://xraypy.github.io/xraylarch/guis.html#larchgui-app
.. _programming with Larch from Python: https://xraypy.github.io/xraylarch/python.html
.. _Matt Newville: https://scholar.google.com/citations?user=B03CvhEAAAAJ