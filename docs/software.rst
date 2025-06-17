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

.. image:: /img/shinnen_aisatsu_hebi_medousa_couple.png
    :alt: hebi medousa couple
    :width: 50%
    :align: left

Larch is programmed in Python and requires a local Python installation to run. I recommend using `Miniconda`_ as your local Python installation since it allows you to create compartmentalized virtual enviroments for different projects. [#f1]_  If you already have an existing Miniconda, Anaconda, or Micromamba installation, you can adjust these instructions accordingly.

`Install Miniconda`_ by following the official instructions for your operating system. On Linux, Miniconda (or a similar package) is probably available in your distribution's repositories. [#f2]_

After installing Miniconda on macOS or Windows, you'll find a new terminal emulator called Anaconda Prompt installed on your computer. If you don't know what any of this means, you should run all of the terminal commands below in Anaconda Prompt.

`conda`_ is the built-in package and Python environment manager for Miniconda. We'll be calling a few times to install Larch. [#f3]_

Installing Larch
----------------

.. image:: /img/job_technical_evangelist_ai_woman.png
    :alt: a woman introducing conda to a man
    :width: 25%
    :align: right

Start by installing mamba, a faster alternative to conda:

.. code-block::

    conda install -y mamba

Create a new virtual environment for Larch, then activate the new virtual environment:

.. code-block::

    conda create -n xraylarch
    conda activate xraylarch

Install xraylarch:

.. code-block::

    conda install -yc xraylarch

If you want to create desktop shortcuts for the Larch applications, run

.. code-block::

    larch -m

Alternatively, you can launch the Larch applications by typing their names into an Anaconda Prompt with the ``xraylarch`` conda environment active. For example, use the ``larix`` command to launch Larix, the main graphical data analysis program provided by Larch.


.. [#f1] macOS comes with Python pre-installed. Despite this, I recommend using Miniconda anyway, since doing so will keep your system's Python installation free of unnecessary packages and will allow you to use conda to automatically install dependencies.
.. [#f2] ...but if you're using Linux, you probably don't need me to tell you about any of this.
.. [#f3] `mamba`_ is an optimized, more performant version of conda that you can use as a drop-in replacement. However, conda now uses mamba as a backend, so many of the speedups of mamba are already implicitly part of conda. You can install mamba by running ``conda install -y mamba``.

.. _Larch: https://xraypy.github.io/xraylarch/
.. _RSXAP: https://lise.lbl.gov/RSXAP/
.. _Install Miniconda: https://www.anaconda.com/docs/getting-started/miniconda/install#linux-terminal-installer
.. _Miniconda: https://www.anaconda.com/docs/getting-started/miniconda/main
.. _conda: https://docs.conda.io/en/latest/
.. _mamba: https://mamba.readthedocs.io/en/latest/user_guide/mamba.html