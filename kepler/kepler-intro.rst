.. _kepler0:

############
Kepler Intro
############

One of my goals has been to understand in detail how Kepler's Laws for the orbits of the planets can be derived from Newton's Laws, namely

.. math::

    \mathbf{F} = m \mathbf{a} 

and the inverse square law of gravitation.

.. math::

    \mathbf{F} = -\frac{GMm}{r^2} \hat{\mathbf{u}}  

I've worked through derivations from several sources, and I think now that I have it figured out.  My goal is to clearly document things here so that I will be able to re-understand in a year (or five) when I read this again.

Kepler's Laws are:  first (K1), the orbits of the planets are not circles but ellipses (non-recurrent orbits may be other conic sections);  second (K2), the area or arc "swept out" per unit time is the same no matter where in the orbit the planet is;  and third (K3) the period of the orbit is independent of the mass of the planet and its square is proportional to the cube of the length of the semi-major axis of the ellipse.

I also spent some time working on Newton's version of the proof as presented in the *Principia* (see Bressoud's vector calculus book), and a version "cooked up" by Richard Feynman and discussed in a book called *Feynman's Lost Lecture*.  I never got either of these figured out, but if you want to go this route I recommend starting with Feynman.

I found that once I cleared up a couple of subtleties,  and verified the application of the product rule for differentiation to vector cross-products, it was pretty easy.

======================
Circular approximation
======================

The equation of an ellipse in :math:`xy`-coordinates is

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 

where :math:`a` is one-half the "diameter" in the long dimension---called the semi-major axis---and :math:`b` is one-half the length perpendicular to that.

A second way is to give the focal length, the distance of each of the two foci from the center of the ellipse

.. math::

    f = \sqrt{a^2 - b^2} 

Yet another way is to give the *eccentricity*, :math:`e`, where

.. math::

    ea = f  

Here is a table of planetary eccentricities I found on the web.

.. image:: /figs/eplanets.png
   :scale: 50 %

Mars is the planet that showed Kepler most clearly that the orbits are not circles;  its eccentricity is 0.09.  For Earth this value is only :math:`0.017`.