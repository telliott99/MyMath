.. _moments:

#######
Moments
#######

The moment of inertia of a collection of discrete masses is the sum of each mass, times the square of the distance to the chosen axis of rotation.  

====
Rods
====

Imagine that we have a uniform (thin) rod, and it's going to rotate around the center of the rod.  Choose that as the origin of coordinates.  The ends of the rod are then at :math:`-l/2` and :math:`+l/2`.

Calculate the mass per unit length :math:`M/l`, and so in a tiny sliver of the rod of width :math:`dx`, the mass at that position is :math:`M/l \ dx` and its moment is :math:`Mx^2/l \ dx`.  We add them all up:

.. math::

    I = \int_{-l/2}^{l/2} \frac{M}{l} x^2 \ dx

    =  \frac{M}{l} \ \frac{x^3}{3} \bigg |_{-l/2}^{l/2} = Ml^2 (\frac{1}{24} - - \frac{1}{24}) = \frac{1}{12} Ml^2

If we move the axis to the end of the rod, then move the coordinate system as well, and we have

.. math::

    \int_0^l \frac{M}{l} x^2 \ dx

    =  \frac{M}{l} \ \frac{x^3}{3} \bigg |_{0}^{l} = \frac{1}{3} Ml^2

There is a principle called the "parallel axis theorem" which says that 

.. math::

    I = I_{CM} + md^2

where :math:`CM` is the center of mass and :math:`d` is the distance between the two axes.  The first example was at the :math:`CM` of the rod, and the distance we moved was :math:`l/2` so we have

.. math::

    I = \frac{1}{12} Ml^2 + M (\frac{l}{2})^2 = Ml^2 (\frac{1}{12} + \frac{1}{4}) = \frac{1}{3} Ml^2

===============
Rings and disks
===============

Imagine the object is a ring, and we're rotating around the center.  Think of it as a sum of discrete pieces

.. math::

    I = \sum_i m_i r^2

But :math:`r = R` for every piece so we have

.. math::

    I = R^2 \sum_i m_i = MR^2

For a disk, we imagine adding up the contribution for a series of rings with increasing radius.  At radius :math:`r`, the circumference of the ring is :math:`2 \pi r`, and the area of the ring is :math:`2 \pi r \ dr`.  The mass per unit area is :math:`M/\pi R^2` so the mass of each ring is

.. math::

    m = \frac{M}{\pi R^2} \ 2 \pi r \ dr = \frac{2M}{R^2} r \ dr

Integrate mass times radius squared from :math:`r=0 \rightarrow R`

.. math::

    I = \int_0^R r^2 \frac{2M}{R^2} r \ dr

    = \frac{2M}{R^2} \ \frac{r^4}{4} \bigg |_{0}^{R} =  \frac{1}{2} MR^2

Now, if we were to move the axis of rotation to the edge, we would have

.. math::

    I = \frac{MR^2}{2} + MR^2 = \frac{3}{2} MR^2

======
Sphere
======

Start with the sphere.  It's analogous to the ring, but harder.  I struggled with this one, by not using the appropriate slant height when calculating the area of a slice.  I found another approach online:

http://www.miniphysics.com/uy1-calculation-of-moment-of-inertia-of_04.html

.. image:: /figs/moment_sphere.png
   :scale: 50 %

and I liked it so much I want to show that approach.  We slice the sphere perpendicular to the axis of rotation.  For each slice we have a ring of radius :math:`r` whose moment is

.. math::

    dI = r^2 \ dm

where

.. math::

    dm = \frac{M}{A} \ dA = \frac{M}{4\pi R^2} \ dA

The trick is to express the area of the ring (parametrize our slices) in terms of an angle :math:`\theta`, shown in the figure (:math:`\theta = 0 \rightarrow \pi`, where :math:`\theta = \pi/2` is perpendicular to the axis).  Doing this, we get the correct area for the width of the ring, namely :math:`R \ d \theta`, and a total area for the ring of

.. math::

    dA = 2 \pi r \ R \ d \theta

so

.. math::

    dm =  \frac{M}{4\pi R^2} \ dA =   \frac{M}{4\pi R^2} \ 2 \pi r \ R \ d \theta =   \frac{M}{2 R} \ r \ d \theta

and then

.. math::

    dI = r^2 \ dm =  \frac{M}{2 R} \ r^3 \ d \theta
    
Now, we need to get a relationship between :math:`r` and :math:`\theta`, but from the diagram it's clear that

.. math::

    r = R \sin \theta

so we have the integral

.. math::

    I = \int dI = \frac{MR^2}{2}  \int_0^{\pi} \sin^3 \theta \ d \theta

This is pretty easy.  We do

.. math::

    \sin^3 \theta \ d \theta = (1- \cos^2 \theta) \sin \theta \ d \theta

the integral is just

.. math::

    \int \sin^3 \theta \ d \theta = - \cos \theta + \frac{\cos^3 \theta}{3} \ \bigg |_0^{\pi} = (1 - \frac{1}{3}) - (-1 + \frac{1}{3}) = \frac{4}{3}

and the answer is 

.. math::

    \frac{2}{3} MR^2

==========
Solid ball
==========

With the previous result in hand the solid ball is pretty easy.  We imagine a series of concentric spheres with increasing radius :math:`r = 0 \rightarrow R`.  Each sphere has

.. math::

    dI = \frac{2}{3} dm \ r^2

    dm = \frac{M}{4/3 \pi R^3} \ 4 \pi r^2 = \frac{3M}{R^3} r^2

so 

.. math::

    dI = \frac{2M}{R^3} r^4

    I = \int \ dI = \frac{2M}{R^3}  \int_0^R r^4

    = \frac{2M}{R^3} \ \frac{R^5}{5} = \frac{2}{5} MR^2

=====================
Parallel axis theorem
=====================

The proof of the parallel axis theorem is not too bad (Fitzpatrick).  Choose the origin of coordinates to be at the center of mass of the body.  Orient the :math:`z`-axis with the axis of rotation.  Orient the new axis so that the new moment of inertia lies along the :math:`x`-axis at :math:`x=d; y =0`.

Since the center of mass is at the origin

.. math::

    \iiint x \ dx \ dy \ dz = 0

with the integrals taken over the volume of the body.  The same is true for :math:`y` and :math:`z`.

Now the square of the distance of any point in the body from the $z$-axis is $x^2 + y^2$, so the moment of inertion with respect to the center of mass is

.. math::

    I_{CM} = M \frac{\iiint (x^2 + y^2) \ dx \ dy \ dz}{\iiint \ dx \ dy \ dz}

The new moment of inertia is

.. math::

    I' = M \frac{\iiint ((x-d)^2 + y^2) \ dx \ dy \ dz}{\iiint \ dx \ dy \ dz}

Expanding and taking the constant :math:`d` outside the integral

.. math::

    = M \frac{\iiint (x^2 + y^2) \ dx \ dy \ dz}{\iiint \ dx \ dy \ dz} - 2dM \frac{\iiint x \ dx \ dy \ dz}{\iiint \ dx \ dy \ dz} + d^2M \frac{\iiint \ dx \ dy \ dz}{\iiint \ dx \ dy \ dz}

The middle integral is zero and the first term is $I_{CM}$ so we have

.. math::

    = I_{CM} + d^2M \frac{\iiint \ dx \ dy \ dz}{\iiint \ dx \ dy \ dz}

The third term is just :math:`Md^2`

.. math::

    I' = I_{CM} + Md^2

I think this derivation assumes constant density, but it will still work with variable density, just add a function :math:`\delta(x,y,z)` which never has to be evaluated.

Just in case, let me show you Professor Shankar's version.  We will do this by summation, just pretend we are summing over lots of individual little mass elements with position vectors :math:`\mathbf{r}_i` from the center of mass.

.. math::

    I_{CM} = \sum_i m_i |\mathbf{r}_i|^2 = \sum_i m_i (\mathbf{r}_i \cdot \mathbf{r}_i)

Now we move the axis of rotation to a new position with position vector :math:`\mathbf{d}` from the center of mass.  Notice that :math:`\mathbf{d}` will be the same for every :math:`m_i`.  The new moment is

.. math::

    I_{CM}' = \sum_i m_i (\mathbf{r}_i' \cdot \mathbf{r}_i') 

where

.. math::

    \mathbf{d} +  \mathbf{r}_i'  = \mathbf{r}_i

    \mathbf{r}_i' = \mathbf{r}_i - \mathbf{d}

and so

.. math::

    \mathbf{r}_i' \cdot \mathbf{r}_i'  =  (\mathbf{r}_i - \mathbf{d}) \cdot (\mathbf{r}_i - \mathbf{d})

    = \mathbf{r}_i \cdot \mathbf{r}_i - 2 \mathbf{r}_i \cdot  \mathbf{d} + \mathbf{d} \cdot \mathbf{d}

substitute into the moment calculation

.. math::

    I_{CM}' = \sum_i m_i (\mathbf{r}_i \cdot \mathbf{r}_i) + \sum_i m_i |(-2) \mathbf{r}_i \cdot \mathbf{d} | + \sum_i m_i (\mathbf{d} \cdot \mathbf{d})

Now, the first term is :math:`I_{CM}`, and in the third term, since :math:`\mathbf{d}` does not vary with :math:`i`, it is just :math:`d^2` and we can pull it out of the sum

.. math::

    I_{CM}' = I_{CM} + \sum_i m_i (-2)( \mathbf{r}_i \cdot \mathbf{d}) + d^2 \sum_i m_i

    I_{CM}' = I_{CM} + \sum_i m_i (-2)( \mathbf{r}_i \cdot \mathbf{d}) + Md^2 

We're almost there.  We need the middle term to vanish.The coordinates were set up so that :math:`\mathbf{d}` lies along the :math:`x`-axis, so :math:` \mathbf{r}_i \cdot \mathbf{d}` is just the constant :math:`d` times the :math:`x`-component of :math:`\mathbf{r}_i` for each vector.

.. math::

    \sum_i m_i (-2)( \mathbf{r}_i \cdot \mathbf{d})  = -2d \sum_i m_i  \mathbf{r}_{ix}

:math:`\sum_i m_i  \mathbf{r}_{ix}` is the :math:`x`-component of the center of mass *in this coordinate system*.  But we've chosen that point to be the origin.  So this term vanishes, leaving

.. math::

    I_{CM}' = I_{CM} + Md^2
