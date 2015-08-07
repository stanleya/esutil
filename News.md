# Older News for esutil #

2012-01-15: Tagged version 0.5.0

2012-01-15: The comoving volume returned by the cosmology class is now for the **whole sky**, whereas previously it was per steradian.  To get the old behavior, divide by 4\*pi

??-??-??: Updated cosmology package to use fast C code.  You should remove an old
> install before installing because of some old files that may be left in place.

2010-11-19: The module [sqlite\_util](http://code.google.com/p/esutil/source/browse/trunk/esutil/sqlite_util.py) is ready for prime time.

**Note:** The bug in released versions of scipy.weave with gcc >= 4.3 compilers has now been circumvented by writing histogram and gauleg as direct C++ extensiosn rather than using weave.  Also, all code works now on OS X 10.5 and 10.6 when using the default compilers, at least for ESS and BG in their tests.

2010-05-02: Updated recfile to support full slicing.  Slicing now works with
ascii as well.  In plotting, began helper functions for working with biggles
plotting package.

2010-04-18: Added more=True keyword to [histogram](http://code.google.com/p/esutil/source/browse/trunk/esutil/stat/util.py#61), to return tons of statistics for the binned data.  Also added weights= keyword.  Also, gauleg was re-written as a C++ extension to remove the final dependence on weave.

2010-04-16: [stat](http://code.google.com/p/esutil/source/browse/trunk/esutil/stat/__init__.py), the tools for doing statistics, is now a package.  Histogram has been re-written as a C++ extension.

2010-04-06: Added patched version of pyfits (esutil.pyfitspatch) that allows writing a fits binary table from a numpy array with fields (or recarray) with a single call.  The io.read() and io.write() functions now use this for FITS i/o.  Patches have been sent to the pyfits folks.  Much of the new pyfits functionality has now graciously been merged into the main branch by the STScI folks.  Many thanks!

2010-03-19: htm matching now defaults to maxmatch=1, return the closest match only.

2010-03-03:

  * Added the **[random](http://code.google.com/p/esutil/source/browse/trunk/esutil/random.py)** module.  Contains a class for generating random points from arbitrary probability distributions.

  * Added the **[htm](http://code.google.com/p/esutil/source/browse/trunk/esutil/htm/__init__.py)** module, a Class to work with the Hierarchical Triangular Mesh.  Useful for matching lists of positions on the sphere, e.g. ra/dec. and for doing correlation functions.

  * Added **[/include/NumpyVector.h](http://code.google.com/p/esutil/source/browse/trunk/esutil/include/NumpyVector.h)**  This is a C++ template class to simplify using 1-d numpy arrays in C++ codes linked to python.

  * Added the **[integrate](http://code.google.com/p/esutil/source/browse/trunk/esutil/integrate.py)** module.  Contains a class to do Gauss-Legendre integration.

2010-02-15: Added class **Cosmo** for performing cosmological calculations to the **[cosmology](http://code.google.com/p/esutil/source/browse/trunk/esutil/cosmology.py)** module.  This is easier to use compared to the "convenience functions" as the cosmology needs only be specified once on construction.

2010-01: The astro\_util module was renamed to **[coords](http://code.google.com/p/esutil/source/browse/trunk/esutil/coords.py)**.  There is still an alias to astro\_util that you can use to prevent code breakage: i.e. `from esutil import astro_util` will still work.