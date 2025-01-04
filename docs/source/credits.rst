.. _credits:

**********************
References and credits
**********************

.. use Chicago Manual of Style 16th edition (full note) for citation format. In
   Zotero, select this style as your copy-and-paste style - then you can hit
   Ctrl-Shift-C to copy references from your library and then paste them into
   the document

Principal articles to read and cite
===================================

[Barkley2020]_ describes the design and functionality of the HoloPy software
package itself. Although some of the code examples have become outdated with
more recent changes to the HoloPy API, this paper is still a good paper to
learn about what HoloPy can do and the ideas that went into its design. Please
cite this paper if you use HoloPy in your research:

.. [Barkley2020] Barkley, Solomon, Thomas G. Dimiduk, Jerome Fung, David M. Kaz,
                 Vinothan N. Manoharan, Ryan McGorty, Rebecca W. Perry, and Anna
                 Wang. “Holographic Microscopy With Python and HoloPy.”
                 Computing in Science and Engineering 22, no. 5 (September
                 2020): 72–82. :doi:`10.1109/MCSE.2019.2923974`.

[Martin2022]_ is a primer on holographic microscopy and generative modeling of
holograms. It's a good paper to learn about the design of a holographic
microscope and modern computational inference methods that are used to analyze
holograms. Please cite this paper (along with other relevant references from
this page) if you use an approach based on scattering models to analyze
holograms:

.. [Martin2022] Martin, Caroline, Lauren E. Altman, Siddharth Rawat, Anna Wang,
                David G. Grier, and Vinothan N. Manoharan. “In-Line Holographic
                Microscopy with Model-Based Analysis.” Nature Reviews Methods
                Primers 2, no. 1 (October 20, 2022): 1–17.
                :doi:`10.1038/s43586-022-00165-z`.

Technical advances and applications
===================================

The following references describe the technical advances that have gone into
HoloPy, and the applications of the technique to scientific questions. We ask
that you read and cite the articles that are relevant to your application.

Bayesian inference
------------------

HoloPy uses a Bayesian approach to fit scattering models to holograms. We first
introduced this approach in [Dimiduk2016]_, which describes the theory, methods,
and results in detail:

.. [Dimiduk2016] Dimiduk, Thomas G., and Vinothan N. Manoharan. “Bayesian
                 Approach to Analyzing Holograms of Colloidal Particles.” Optics
                 Express 24, no. 21 (October 17, 2016): 24045–60.
                 :doi:`10.1364/OE.24.024045`.

This approach takes advantage of random sampling of the data to speed up the
calculations and perform tempered MCMC calculations. The random sampling
approach was originally described (in a non-Bayesian context) in [Dimiduk2014]_:

.. [Dimiduk2014] Dimiduk, Thomas G., Rebecca W. Perry, Jerome Fung, and
                 Vinothan N. Manoharan. “Random-Subset Fitting of Digital
                 Holograms for Fast Three-Dimensional Particle Tracking.”
                 Applied Optics 53, no. 27 (September 20, 2014): G177–83.
                 :doi:`10.1364/AO.53.00G177`.

HoloPy relies on the affine-invariant ensemble sampler `emcee`
[Foreman-Mackey2013]_ for Markov-chain Monte Carlo (MCMC) calculations. We also
use the Covariance Matrix Adaptation Evolution Strategy (CMA-ES), as described
in [Hansen1996]_ and (for the parallelized version) in [Hansen2003]_ to find
starting points for MCMC.

.. [Foreman-Mackey2013] Foreman-Mackey, Daniel, David W. Hogg, Dustin Lang, and
                        Jonathan Goodman. “emcee: The MCMC Hammer.” Publications
                        of the Astronomical Society of the Pacific 125, no. 925
                        (2013): 306. :doi:`10.1086/670067`.

.. [Hansen1996] Hansen, N., and A. Ostermeier. “Adapting Arbitrary Normal
                Mutation Distributions in Evolution Strategies: The Covariance
                Matrix Adaptation.” In Proceedings of IEEE International
                Conference on Evolutionary Computation, 312–17, 1996.
                :doi:`10.1109/ICEC.1996.542381`.

.. [Hansen2003] Hansen, Nikolaus, Sibylle D. Müller, and Petros Koumoutsakos.
                “Reducing the Time Complexity of the Derandomized Evolution
                Strategy with Covariance Matrix Adaptation (CMA-ES).”
                Evolutionary Computation 11, no. 1 (March 1, 2003): 1–18.
                :doi:`10.1162/106365603321828970`.

For an introduction to Bayesian analysis of experimental data, we recommend
[Gregory2010]_.

Modeling the lens
-----------------

The following three papers describe how HoloPy models the effects of an
objective lens on a hologram. [Leahy2020]_ describes the theory and results for
a single spherical particle. [Alexander2020]_ extends the method to
non-spherical particles. And [Martin2021]_ describes how the effects of
spherical abberation can be incorporated into the model.

.. [Leahy2020] Leahy, Brian, Ronald Alexander, Caroline Martin, Solomon Barkley,
               and Vinothan N. Manoharan. “Large depth-of-field tracking of
               colloidal spheres in holographic microscopy by modeling the
               objective lens.” Optics Express 28, no. 2 (2020): 1061-1075.
               :doi:`10.1364/OE.382159`.

.. [Alexander2020] Alexander, Ronald, Brian Leahy, and Vinothan N. Manoharan.
                   “Precise Measurements in Digital Holographic Microscopy by
                   Modeling the Optical Train.” Journal of Applied Physics 128,
                   no. 6 (August 10, 2020): 060902. :doi:`10.1063/5.0015976`.

.. [Martin2021] Martin, Caroline, Brian Leahy, and Vinothan N. Manoharan.
                “Improving Holographic Particle Characterization by Modeling
                Spherical Aberration.” Optics Express 29, no. 12 (June 7, 2021):
                18212–23. :doi:`10.1364/OE.424043`.

Modeling and measuring the positions of multiple spherical particles
--------------------------------------------------------------------

[Fung2011]_ describes the use of the multi-sphere superposition method (an exact
solution to Maxwell's equation for scattering from multiple spherical particles
[Mackowski1996]_) to model interacting pairs of colloidal spheres. Fitting the
model to the data reveals the translational, rotational, and vibrational
dynamics in 3D, from which the interactions can be inferred. [Fung2012]_ extends
the approach to holograms of several colloidal particles. In [Perry2012]_ we fit
models of scattering from multiple spheres to measure the thermal fluctuations
of clusters of interacting colloidal spheres, and in [Fung2013]_ we use a
similar approach to measure the 3D diffusion of dimers and trimers of colloidal
spheres.

.. [Fung2011] Fung, Jerome, K. Eric Martin, Rebecca W. Perry, David M. Kaz, Ryan
              McGorty, and Vinothan N. Manoharan. “Measuring Translational,
              Rotational, and Vibrational Dynamics in Colloids with Digital
              Holographic Microscopy.” Optics Express 19, no. 9 (April 25,
              2011): 8051–65. :doi:`10.1364/OE.19.008051`.

.. [Fung2012] Fung, Jerome, Rebecca W. Perry, Thomas G. Dimiduk, and Vinothan N.
              Manoharan. “Imaging Multiple Colloidal Particles by Fitting
              Electromagnetic Scattering Solutions to Digital Holograms.”
              Journal of Quantitative Spectroscopy and Radiative Transfer 113,
              no. 18 (December 2012): 2482–89. :doi:`10.1016/j.jqsrt.2012.06.007`.


.. [Perry2012] Perry, Rebecca W., Guangnan Meng, Thomas G. Dimiduk, Jerome Fung,
               and Vinothan N. Manoharan. “Real-Space Studies of the Structure
               and Dynamics of Self-Assembled Colloidal Clusters.” Faraday
               Discussions 159, no. 1 (June 7, 2012): 211–34.
               :doi:`10.1039/C2FD20061A`.

.. [Fung2013] Fung, Jerome, and Vinothan N. Manoharan. “Holographic
              Measurements of Anisotropic Three-Dimensional Diffusion of
              Colloidal Clusters.” Physical Review E 88, no. 2 (August 30,
              2013): 020302. :doi:`10.1103/PhysRevE.88.020302`.



Modeling and measuring the positions and orientations of non-spherical particles
--------------------------------------------------------------------------------

[Wang2014]_ discusses the use of the discrete-dipole approximation (DDA; see
[Yurkin2011]_) to model the scattering of non-spherical particles. We fit
DDA-based models to infer the dynamics of colloidal rods and Janus particles.
[Wang2016b]_ uses this approach to track the translational and rotational
movement of individual *E\. Coli* cells (modeled as spherocylinders) in 3D.

.. [Wang2014] Wang, Anna, Thomas G. Dimiduk, Jerome Fung, Sepideh Razavi, Ilona
              Kretzschmar, Kundan Chaudhary, and Vinothan N. Manoharan. “Using
              the Discrete Dipole Approximation and Holographic Microscopy to
              Measure Rotational Dynamics of Non-Spherical Colloidal Particles.”
              Journal of Quantitative Spectroscopy and Radiative Transfer 146
              (October 2014): 499–509. :doi:`10.1016/j.jqsrt.2013.12.019`.


.. [Wang2016b] Wang, Anna, Rees F. Garmann, and Vinothan N. Manoharan. “Tracking
               *E. Coli* Runs and Tumbles with Scattering Solutions and Digital
               Holographic Microscopy.” Optics Express 24, no. 21 (October 17,
               2016): 23719–25. :doi:`10.1364/OE.24.023719`.

In [Wang2017]_ we measure the trajectories of nonspherical (spheroidal and
spherocylindrical) colloidal particles that adsorb to a fluid interface.  We
record holograms of the particles and fit a scattering model to the holograms to
infer the position and orientation of the particles as a function of time.  For
the spheroidal particles we use the T-matrix approach of [Mishchenko2000]_ to
model the scattering.  For the spherocylindrical particles we use a DDA-based
model:

.. [Wang2017] Wang, Anna, W. Benjamin Rogers, and Vinothan N. Manoharan.
              “Effects of Contact-Line Pinning on the Adsorption of Nonspherical
              Colloids at Liquid Interfaces.” Physical Review Letters 119, no.
              10 (September 7, 2017): 108004. :doi:`10.1103/PhysRevLett.119.108004`.


High-precision measurement of single-sphere dynamics
----------------------------------------------------

In earlier work, we used holographic microscopy and model-based analysis to
measure the dynamics of individual colloidal spheres as they breach a fluid
interface. As described in [Kaz2012]_, we found that the dynamics are governed
by pinning and depinning of the three-phase contact line on the surface of the
particle, which results in surprisingly long relaxation times. We explored these
dynamics in detail (again using holographic microscopy and model-based
inference, along with theoretical models of dynamics) in [Wang2013]_,
[Rahmani2016]_, and [Wang2016a]_. In [Wang2019]_ we use a similar approach to
understand the dynamics that precede contact between the particle and interface.

.. [Kaz2012] Kaz, David M., Ryan McGorty, Madhav Mani, Michael P. Brenner, and
             Vinothan N. Manoharan. “Physical Ageing of the Contact Line on
             Colloidal Particles at Liquid Interfaces.” Nature Materials 11, no.
             2 (February 2012): 138–42. :doi:`10.1038/nmat3190`.

.. [Wang2013] Wang, Anna, David M. Kaz, Ryan McGorty, and Vinothan N. Manoharan.
              “Relaxation Dynamics of Colloidal Particles at Liquid Interfaces.”
              In AIP Conference Proceedings, 1518:336–43. Sendai, Japan, 2013.
              :doi:`10.1063/1.4794594`.

.. [Rahmani2016] Rahmani, Amir M., Anna Wang, Vinothan N. Manoharan, and
                 Carlos E. Colosqui. “Colloidal Particle Adsorption at Liquid
                 Interfaces: Capillary Driven Dynamics and Thermally Activated
                 Kinetics.” Soft Matter 12, no. 30 (July 27, 2016): 6365–72.
                 :doi:`10.1039/C6SM00966B`.

.. [Wang2016a] Wang, Anna, Ryan McGorty, David M. Kaz, and Vinothan N.
               Manoharan. “Contact-Line Pinning Controls How Quickly Colloidal
               Particles Equilibrate with Liquid Interfaces.” Soft Matter 12,
               no. 43 (October 6, 2016): 8958–67.
               :doi:`10.1039/C6SM01690A`.

.. [Wang2019] Wang, Anna, Jos W. Zwanikken, David M. Kaz, Ryan McGorty, Aaron M.
              Goldfain, W. Benjamin Rogers, and Vinothan N. Manoharan. “Before
              the Breach: Interactions between Colloidal Particles and Liquid
              Interfaces at Nanoscale Separations.” Physical Review E 100, no. 4
              (October 9, 2019): 042605.
              :doi:`10.1103/PhysRevE.100.042605`.



References for reconstruction
=============================

HoloPy uses the convolution approach to numerical reconstruction, as discussed
in [Kreis2002]_ and [Kreis2005]_. For reconstruction of holograms generated by
point sources, HoloPy uses an algorithm based on the description in
[Jericho2011]_. See also [Goodman2017]_ for background on Fourier optics, which
is required to understand reconstruction.


.. [Kreis2002] Kreis, Thomas M. “Frequency Analysis of Digital Holography with
               Reconstruction by Convolution.” Optical Engineering 41, no. 8
               (2002): 1829–39. :doi:`10.1117/1.1489678`.

.. [Kreis2005] Kreis, Thomas M., *Handbook of Holographic Interferometry*,
               Wiley (2005).

.. [Jericho2011] Jericho, Manfred H., and H. Jürgen Kreuzer. “Point Source
                 Digital In-Line Holographic Microscopy Digital In-Line
                 Holographic Microscopy.” In *Coherent Light Microscopy*, edited
                 by Pietro Ferraro, Adam Wax, and Zeev Zalevsky, 3–30. Springer
                 Series in Surface Sciences 46. Springer (2011).
                 :doi:`10.1007/978-3-642-15813-1_1`.


References for scattering calculations
======================================

The following papers describe the methods and algorithms that HoloPy uses in its
scattering calculations.

Lorenz-Mie scattering
---------------------

For scattering calculations and formalism, we draw heavily on the treatise of
Bohren & Huffman [Bohren1983]_.  We generally follow their conventions except
where noted.  Additional algorithms and methods incorporated in HoloPy are
described in [Lentz1976]_, [Wiscombe1980]_ and [Wiscombe1996]_:

.. [Lentz1976] Lentz, William J. “Generating Bessel Functions in Mie Scattering
               Calculations Using Continued Fractions.” Applied Optics 15, no. 3
               (March 1, 1976): 668–71. :doi:`10.1364/AO.15.000668`.

.. [Wiscombe1980] Wiscombe, W. J. “Improved Mie scattering algorithms.” Applied
                  Optics 19, no. 9 (May 1, 1980): 1505.
                  :doi:`10.1364/AO.19.001505`.

.. [Wiscombe1996] Wiscombe, J. “Mie Scattering Calculations: Advances in
                  Technique and Fast, Vector-Speed Computer Codes,” 1979.
                  :doi:`10.5065/D6ZP4414`.

Scattering from multilayer spheres
----------------------------------

[Yang2003]_ is our main source for calculations of scattering from multilayer
spheres.  We also use formulae and algorithms from [Mackowski1990]_:

.. [Yang2003] Yang, Wen. “Improved Recursive Algorithm for Light Scattering by a
              Multilayered Sphere.” Applied Optics 42, no. 9 (March 20, 2003):
              1710–20. :doi:`10.1364/AO.42.001710`.


.. [Mackowski1990] Mackowski, D. W., Altenkirch, R. A., and Menguc, M. P.
                   “Internal absorption cross sections in a stratified sphere.”
                   Applied Optics 29, no. 10 (1990). :doi:`10.1364/AO.29.001551`.

Scattering from clusters of spheres
-----------------------------------

For clusters of spheres, HoloPy uses the multisphere superposition method
described in [Mackowski1996]_ to calculate the scattering.  For a nice pedagogical
introduction to the method, see also [Mackowski2012]_. 

.. [Mackowski1996] Mackowski, Daniel W., and Michael I. Mishchenko. “Calculation
                   of the T Matrix and the Scattering Matrix for Ensembles of
                   Spheres.” Journal of the Optical Society of America A 13, no.
                   11 (November 1, 1996): 2266. :doi:`10.1364/JOSAA.13.002266`.

.. [Mackowski2012] Mackowski, Daniel. “The Extension of Mie Theory to Multiple
                   Spheres.” In *The Mie Theory: Basics and Applications*,
                   edited by Wolfram Hergert and Thomas Wriedt, 223–56. Springer
                   (2012). :doi:`10.1007/978-3-642-28738-1_8`.

Scattering from nonspherical particles
--------------------------------------


For spheroidal and cylindrical particles, HoloPy uses the T-matrix-based
approach discussed in [Mishchenko2000]_ to calculate the scattering. For more
general particles, HoloPy can use the discrete-dipole approximation to calculate
the scattering, as implemented in the software package ADDA [Yurkin2011]_:

.. [Mishchenko2000] Mishchenko, Michael I. “Calculation of the Amplitude Matrix
                    for a Nonspherical Particle in a Fixed Orientation.” Applied
                    Optics 39, no. 6 (February 20, 2000): 1026–31.
                    :doi:`10.1364/AO.39.001026`.

.. [Yurkin2011] Yurkin, Maxim A., and Alfons G. Hoekstra. “The
                Discrete-Dipole-Approximation Code ADDA: Capabilities and Known
                Limitations.” Journal of Quantitative Spectroscopy and Radiative
                Transfer 112, no. 13 (September 2011): 2234–47.
                :doi:`10.1016/j.jqsrt.2011.01.031`.


Historically important papers on model-based analysis of holograms
==================================================================

[Alexander2020]_ reviews the history of fitting generative models to holograms
to infer information directly from the holograms instead of from their
reconstructions. As noted in that review, Silverman, Thompson, and Ward
[Silverman1964]_ appear to be the first to demonstrate the inference approach.
They used a Fraunhofer diffraction model to infer the size distribution of large
droplets. Following subsequent developments (see [Alexander2020]_ for more
details), Ovryn and Izen [Ovryn2000]_ used Lorenz-Mie theory to simulate
holograms of micrometer-scale particles and model the effects of an objective
lens on the holograms. Later, Lee and coworkers [Lee2007]_ developed a
simplified model of hologram formation through an objective lens, based on
Lorenz-Mie theory, and fit the model to holograms of colloidal spheres to infer
their position and refractive index.

.. [Silverman1964] Thompson, Brian J., Georgy B. Parrent, John H. Ward, and
                   Bruce Justii. “A Readout Technique for the Laser Fog
                   Disdrometer.” Journal of Applied Meteorology 5, no. 3 (June
                   1, 1966): 343–48.
                   :doi:`10.1175/1520-0450(1966)005<0343:ARTFTL>2.0.CO;2`.

.. [Ovryn2000] Ovryn, Ben, and Steven H. Izen. “Imaging of Transparent Spheres
               through a Planar Interface Using a High-Numerical-Aperture
               Optical Microscope.” Journal of the Optical Society of America A
               17, no. 7 (July 1, 2000): 1202–13. :doi:`10.1364/JOSAA.17.001202`.

.. [Lee2007] Lee, Sang-Hyuk, Yohai Roichman, Gi-Ra Yi, Shin-Hyun Kim, Seung-Man
             Yang, Alfons van Blaaderen, Peter van Oostrum, and David G. Grier.
             “Characterizing and Tracking Single Colloidal Particles with Video
             Holographic Microscopy.” Optics Express 15, no. 26 (December 24,
             2007): 18275–82. :doi:`10.1364/OE.15.018275`.


Useful textbooks
================

.. [Bohren1983] C\. F\. Bohren and D\. R\. Huffman, *Absorption and Scattering
                of Light by Small Particles*, Wiley (1983).

.. [Gregory2010] P\. Gregory, *Bayesian Logical Data Analysis for the Physical
                 Sciences*, Cambridge University Press (2010).

.. [Goodman2017] Joseph W\. Goodman, *Introduction to Fourier Optics*, W. H.
                 Freeman & Company (2017).


Code
====

The package includes code from several sources. We thank Daniel Mackowski for
allowing us to include his multisphere superposition code, which computes
scattering from clusters of spheres: SCSMFO1B_.

.. _SCSMFO1B: ftp://ftp.eng.auburn.edu/pub/dmckwski/scatcodes/index.html

We thank Michael Mishchenko for allowing us to include his LAPACK-based T-matrix
codes for single scatterers in fixed orientation: ampld.lp_

.. _ampld.lp: https://www.giss.nasa.gov/staff/mmishchenko/tmatrix/

We also make use of a modified version of the Python version of mpfit_,
originally developed by Craig Markwardt. The modified version we use is drawn
from the stsci_python_ package.

.. _mpfit: http://www.physics.wisc.edu/~craigm/idl/fitting.html
.. _stsci_python: http://www.stsci.edu/resources/software_hardware/pyraf/stsci_python

We thank A. Ross Barnett for permitting us to use his routine SBESJY.FOR_, which
computes spherical Bessel functions.

.. _SBESJY.FOR: http://www.fresco.org.uk/programs/barnett/index.htm
