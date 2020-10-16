Conda PyTorch Release notes
^^^^^^^^^^^^^^^^^^^^^^^^^^^

This document lists the release notes for the Neuron Conda-Pytorch
package.

Known Issues (updated 9/22/2020)
================================

-  When TorchVision is updated to version >= 0.5, running Neuron
   compilation would crash with "Segmentation fault (core dumped)"
   error. This issue is resolved with version
   1.5.1.1.0.1721.0_2.0.1017.0 of Conda PyTorch Neuron package.
-  When running PyTorch script in latest Torch-Neuron conda environment,
   you may see errors "AttributeError: module 'numpy' has no attribute
   'integer'" and "ModuleNotFoundError: No module named
   'numpy.core._multiarray_umath'". This is due to older version of
   numpy. Please update numpy to version 1.18 using the command "conda
   install --force numpy=1.18.1".
-  Due to changes to Torch-Neuron Conda package content in this release,
   updating from current Torch-Neuron conda environment has no effect.
   Instead please do the following to update:

.. code:: bash

   conda install --force torch-neuron=1.5.1.1.0.1721.0
   conda install --force numpy=1.18.1

.. _1511017210_2010170:

[1.5.1.1.0.1721.0_2.0.1017.0]
=============================

Date: 09/22/2020

Included Neuron Packages
------------------------

`neuron-cc-1.0.20600.0 <../neuron-cc.md>`__

`torch_neuron-1.0.1721.0 <../torch-neuron.md>`__

Resolved Issues
---------------

When TorchVision is updated to version >= 0.5, running Neuron
compilation would crash with "Segmentation fault (core dumped)" error.

Known Issues
------------

-  When TorchVision is updated to version >= 0.5, running Neuron
   compilation would crash with "Segmentation fault (core dumped)"
   error. This issue is resolved with version
   1.5.1.1.0.1721.0_2.0.1017.0 of Conda PyTorch Neuron package.
-  When running PyTorch script in latest Torch-Neuron conda environment,
   you may see errors "AttributeError: module 'numpy' has no attribute
   'integer'" and "ModuleNotFoundError: No module named
   'numpy.core._multiarray_umath'". This is due to older version of
   numpy. Please update numpy to version 1.18 using the command "conda
   install --force numpy=1.18.1".
-  Due to changes to Torch-Neuron Conda package content in this release,
   updating from current Torch-Neuron conda environment has no effect.
   Instead please do the following to update:

.. code:: bash

   conda install --force torch-neuron=1.5.1.1.0.1721.0
   conda install --force numpy=1.18.1

.. _151102980_208800:

[1.5.1.1.0.298.0_2.0.880.0]
===========================

Date: 08/08/2020

.. _included-neuron-packages-1:

Included Neuron Packages
------------------------

`neuron-cc-1.0.18001.0 <../neuron-cc.md>`__

`torch_neuron-1.0.1532.0 <../torch-neuron.md>`__

torch_neuron_base-1.5.1.1.0.298.0

.. _151102580_208710:

[1.5.1.1.0.258.0_2.0.871.0]
===========================

Date: 08/05/2020

.. _included-neuron-packages-2:

Included Neuron Packages
------------------------

`neuron-cc-1.0.17937.0 <../neuron-cc.md>`__

`torch_neuron-1.0.1522.0 <../torch-neuron.md>`__

torch_neuron_base-1.5.1.1.0.258.0

.. _151102510_207830:

[1.5.1.1.0.251.0_2.0.783.0]
===========================

Date: 07/16/2020

Now supporting Python 3.7 Conda packages in addition to Python 3.6 Conda
packages.

.. _included-neuron-packages-3:

Included Neuron Packages
------------------------

`neuron-cc-1.0.16861.0 <../neuron-cc.md>`__

`torch_neuron-1.0.1386.0 <../torch-neuron.md>`__

torch_neuron_base-1.5.1.1.0.251.0

.. _130102150-206330:

[1.3.0.1.0.215.0-2.0.633.0]
===========================

Date 6/11/2020

.. _included-neuron-packages-4:

Included Neuron Packages
------------------------

`neuron-cc-1.0.15275.0 <../neuron-cc.md>`__

`torch_neuron-1.0.1168.0 <../torch-neuron.md>`__

torch_neuron_base-1.3.0.1.0.215.0

.. _130101700-203490:

[1.3.0.1.0.170.0-2.0.349.0]
===========================

Date 5/11/2020

.. _included-neuron-packages-5:

Included Neuron Packages
------------------------

`neuron-cc-1.0.12696.0 <../neuron-cc.md#1068010>`__

`torch_neuron-1.0.1001.0 <../torch-neuron.md#106720>`__

torch_neuron_base-1.3.0.1.0.170.0

.. _13010900_20620:

[1.3.0.1.0.90.0_2.0.62.0]
=========================

Date 3/26/2020

.. _included-neuron-packages-6:

Included Neuron Packages
------------------------

`neuron-cc-1.0.9410.0 <../neuron-cc.md#1068010>`__

`torch_neuron-1.0.825.0 <../torch-neuron.md#106720>`__

torch_neuron_base-1.3.0.1.0.90.0

.. _13010900-109180:

[1.3.0.1.0.90.0-1.0.918.0]
==========================

Date: 2/27/2020

.. _included-neuron-packages-7:

Included Neuron Packages
------------------------

`neuron_cc-1.0.7878.0 <../neuron-cc.md#1068010>`__

`torch_neuron-1.0.763.0 <../torch-neuron.md#106720>`__

torch_neuron_base-1.3.0.1.0.90.0

Known Issues and Limitations
----------------------------

`Conda Tensorflow Release Notes <../tensorflow-neuron.md>`__
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _13010410-107370:

[1.3.0.1.0.41.0-1.0.737.0]
==========================

Date: 1/27/2020

.. _included-neuron-packages-8:

Included Neuron Packages
------------------------

`neuron-cc-1.0.6801.0 <../neuron-cc.md#1068010>`__

`torch-neuron-1.0.672.0 <../torch-neuron.md#106720>`__

torch-neuron-base-1.3.0.1.0.41.0

.. _known-issues-and-limitations-1:

Known Issues and Limitations
----------------------------
