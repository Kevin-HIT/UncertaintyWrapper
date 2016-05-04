UncertaintyWrapper
==================

Use ``@unc_wrapper`` decorator to wrap any Python callable to append the
covariance and Jacobian matrices to the return values. See documentation and
tests for usage and examples.

Installation
------------

Use ``pip install uncertainty_wrapper`` to install from
`PyPI <https://pypi.python.org/pypi/uncertainty_wrapper>`_ or download a source
distribution, extract and use ``python setup.py install``.

Requirements
------------

* `NumPy <http://www.numpy.org/>`_

Optional Requirements
~~~~~~~~~~~~~~~~~~~~~

* `Nose <https://nose.readthedocs.org/en/latest/index.html>`_ for testing.
* `Sphinx <http://www.sphinx-doc.org/en/stable/>`_ to build documentation.
* `NREL SOLPOS <http://rredc.nrel.gov/solar/codesandalgorithms/solpos/>`_ for testing
* `AlgoPy <https://pythonhosted.org/algopy/>`_ for testing


History
-------
Releases are named after
`geological eons, periods and epochs <https://en.wikipedia.org/wiki/Geologic_time_scale>`_.

`v0.3.1 <https://github.com/SunPower/UncertaintyWrapper/releases/tag/v0.3.1>`_ `Paleoproterozoic Era <https://en.wikipedia.org/wiki/Paleoproterozoic>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Fixes #1 works with Pint's @ureg.wraps()
* Use indices for positional arguments. Don't use inspect.argspec since not
  guaranteed to be the same for wrapped or decorated functions
* Test Jacobian estimate for IV with `AlgoPy <https://pythonhosted.org/algopy/>`_
* Show Jacobian errors plot in getting started docs.


`v0.3 <https://github.com/SunPower/UncertaintyWrapper/releases/tag/v0.3>`_ `Proterozoic Eon <https://en.wikipedia.org/wiki/Proterozoic>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* new ``unc_wrapper_args()`` allows selection of independent variables that the
  partial derivatives are with respect to and also grouping those arguments
  together so that in the original function they can stay unpacked.
* return values are grouped correctly so that they can remain unpacked in
  original function. These allow Uncertainty Wrapper to be used with
  `Pint's wrapper <http://pint.readthedocs.org/en/latest/wrapping.html>`_
* covariance now specified as dimensionaless fraction of square of arguments
* more complex tests: IV curve and solar position (requires
  `NREL's solpos <http://rredc.nrel.gov/solar/codesandalgorithms/solpos/>`_)


`v0.2.1 <https://github.com/SunPower/UncertaintyWrapper/releases/tag/v0.2>`_ `Eoarchean Era <https://en.wikipedia.org/wiki/Eoarchean>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* update documentation


`v0.2 <https://github.com/SunPower/UncertaintyWrapper/releases/tag/v0.2>`_ `Archean Eon <https://en.wikipedia.org/wiki/Archean>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Fix nargs and nf order mixup in Jacobian
* add more complex test
* fix tile cov by nobs
* move partial derivative to subfunction
* try threading, but same speed, and would only work with NumPy anyway


`v0.1 <https://github.com/SunPower/UncertaintyWrapper/releases/tag/v0.1>`_ `Hadean Eon <https://en.wikipedia.org/wiki/Hadean>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* adds covariance to output
* allows __covariance__ to be passed as input
* uses estimate Jacobian based on central finite difference method