.. include:: links.inc

.. _astropy-modeling:

***************************************
Models and Fitting (`astropy.modeling`)
***************************************

Introduction
============

`astropy.modeling` provides a framework for representing models and performing
model evaluation and fitting.  A number of predefined 1-D and 2-D models are
provided and the capability for custom, user defined models is supported.
Different fitting algorithms can be used with any model.  For those fitters
with the capabilities fitting can be done using uncertainties, parameters with
bounds, and priors.

.. note::

    A number of significant changes have been made to the internals that have been
    documented in more detail in :doc:`changes_for_4`. The main change is that
    combining model classes no longer is supported. (Combining model
    instances is still very much supported!)

.. _modeling-using:

Using Modeling
==============

.. toctree::
   :maxdepth: 2

   Models <models.rst>
   Compound Models <compound-models.rst>
   Model Parameters <parameters.rst>
   Fitting <fitting.rst>
   Using Units with Models and Fitting <units.rst>
   Changes in v4.0 <changes_for_4.rst>


.. _getting-started-example:

A Simple Example
================

Using a model is a matter of defining the model (instantiating) and then
calling it with the input values for calculation.  This is illustrated with
the code and plot below for a 1-dimensional Gaussian.

   .. plot::
       :include-source:

       import numpy as np
       import matplotlib.pyplot as plt
       from astropy.modeling import models

       # define and evaluate the model
       g = models.Gaussian1D(amplitude=1.2, mean=0.9, stddev=0.5)
       x = np.linspace(-5., 5.0, 200)
       y = g(x)

       # plot the model
       plt.figure()
       plt.plot(x, y, 'ko')
       plt.xlabel('x')
       plt.ylabel('y')

.. _advanced_topics:

Advanced Topics
===============

.. toctree::
   :maxdepth: 2

   Performance Tips <performance.rst>
   Extending Models <new-model.rst>
   Extending Fitters <new-fitter.rst>
   Adding support for units to models <add-units.rst>


Examples
========

.. toctree::
   :maxdepth: 1

   example-fitting-constraints
   example-fitting-uncertainties
   example-fitting-sigma-clipping
   example-fitting-model-sets

.. TODO list
    fitting with masks
    fitting with priors
    fitting with units
    defining 1d model
    defining 2d model
    fitting 2d model
    defining and using a WCS/gWCS model
    defining and using a Tabular1D model
    statistics functions and how to make your own
    compound models
    model sets w/ fitting

Reference/API
=============

.. toctree::
   :maxdepth: 1

   reference_api
