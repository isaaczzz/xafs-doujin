Software
========

.. image:: /img/computer_doctor_woman.png
    :alt: a female scientist deciding which xafs software to use
    :width: 25%
    :align: right

If a real world closer to utopia than ours existed, it wouldn't matter which software we decided to use to process and analyze our data. In reality, several popular and unpopular analysis packages exist. The ones I support are `Larch`_ and `RSXAP`_ because they're what I know and I trust the people who develop them.

Larch is easy to set up and use, so it's what I'll show you how to use here. While RSXAP scales better to complicated fitting jobs than Larch does, Larch's UI and ease-of-use make it convenient for on-the-fly data analysis at the beamline.

Wrangling Pythons
-----------------

Larch is programmed in Python and requires a local Python installation to run. I recommend using `Miniconda`_ as your local Python installation since it allows you to create compartmentalized virtual enviroments for different projects. [#f1]_  If you already have an existing Miniconda, Anaconda, or Micromamba installation, you can adjust these instructions accordingly.

`conda`_ is the built-in package manager for Miniconda. We'll be calling a few times to install Larch.

The Command-Line Interface
--------------------------

    Right? Grow up!

    -- Dr. Corwin Booth on scientists who fear the command line

After installing Miniconda, you'll find a new terminal emulator called Anaconda Prompt installed on your computer. If you don't know what any of this means, you should run all of the terminal commands below in Anaconda Prompt.

Installing Larch
----------------

Start by installing mamba, a faster alternative to conda:

.. code-block::

    conda install -y mamba

Create a new virtual environment for Larch, then activate the new virtual environment:

.. code-block::

    mamba create -n xraylarch
    mamba activate xraylarch

Install xraylarch:

.. code-block::

    mamba install -yc xraylarch

If you want to create desktop shortcuts for the Larch applications, run

.. code-block::

    larch -m

Alternatively, you can launch the Larch applications by typing their names into an Anaconda Prompt with the ``xraylarch`` conda environment active. For example, use the ``larix`` command to launch Larix, the main graphical data analysis program provided by Larch.


.. [#f1] macOS comes with Python pre-installed. Despite this, I recommend using Miniconda anyway, since doing so will keep your system's Python installation free of unnecessary packages and will allow you to use conda to automatically install dependencies.

.. _Larch: https://xraypy.github.io/xraylarch/
.. _RSXAP: https://lise.lbl.gov/RSXAP/
.. _Miniconda: https://www.anaconda.com/docs/getting-started/miniconda/main
.. _conda: https://docs.conda.io/en/latest/