.. _disks-shells:

################
Disks and shells
################

===============
Method of disks
===============

Consider a function :math:`f(x)`, and imagine that we rotate the graph of the function around the :math:`x`-axis.  The rotational symmetry allows us to calculate the volume as a single integral.

The method is to "slice" the volume into disks perpendicular to the :math:`x`-axis.  The cross-sections are circles, because of the rotation.  

Here is a picture of what we're doing, from Hamming's Calculus text.  The notation is different but the idea is the same.

.. image:: /figs/sphere_vol1.png
   :scale: 50 %

Every disk has a volume equal to the area of that slice times the width :math:`dx`.  The area of a slice is :math:`\pi \times` the square of the radius of the slice.  But the radius is just :math:`f(x)`, or :math:`y`.  So a simple formula is:

.. math::

    dV = \pi y^2 \ dx

The total volume is obtained by adding up all of the slices:

.. math::

    V = \pi \int y^2 \ dx
    
This is the general formula for this kind of problem.

One specific problem is to obtain the volume of a sphere, which we get by rotating the top half of the graph of a circle

.. math::

    y = + \sqrt{R^2 - x^2}
    
    y^2 = R^2 - x^2

Suppose we choose the bounds to be :math:`x = -R \rightarrow R`.  The integral is:

.. math::

    V = \pi \int y^2 \ dx
    
    = \pi \int_{-R}^R (R^2 - x^2) \ dx
    
    = \pi \ (R^2x - \frac{x^3}{3}) \bigg |_{-R}^{R}
    
    = \pi \ [ \ (R^3 - \frac{1}{3}R^3) - (-R^3 + \frac{1}{3}R^3) \ ]
    
    = \frac{4}{3}\pi R^3

++++++++++
Variations
++++++++++

One variation is to find the volume bounded between *two* curves revolved around the :math:`x`-axis.  If :math:`f(x) > g(x)` everywhere in the region, then just integrate :math:`\pi` times :math:`[ f(x) ]^2 - [ g(x) ]^2`.  If the curves cross over each other, then you will need to find the intersection point or points and integrate the parts separately.

Another type of problem asks for the solid obtained by rotating a curve (or curves) around the :math:`y`-axis, but give the curve in terms of :math:`y = f(x)`.  To do this kind of problem, you must first convert to :math:`x = f(y)`, and then integrate :math:`\pi x^2`.  It is important to also switch the bounds to be expressed in terms of :math:`y` instead of :math:`x`.

One solid that is commonly encountered is the paraboloid, the shape obtained by rotating a parabola around its central axis.  Consider a parabola oriented in the normal way (:math:`y=x^2`).  Rotate it around the :math:`y`-axis.  Our slices will be perpendicular to the :math:`y`-axis and the slices will have a radius that is :math:`x = \sqrt{y}`.  We integrate

.. math::

    V = \int dV

    \int \pi x^2 \ dy
    
    = \pi \int y \ dy

    = \pi \frac{1}{2} y^2

What bounds should we choose?  Suppose we integrate from :math:`y=0 \rightarrow y = 1`.  The volume is 

.. math::

    = \pi \frac{1}{2} y^2 \ \bigg |_0^1 = \frac{\pi}{2}

Or from :math:`y=0 \rightarrow y = 2`, the volume is 

.. math::

    = \pi \frac{1}{2} y^2 \ \bigg |_0^2 = 2 \pi

================
Method of shells
================

Here is a second picture, for the method of shells, also from Hamming's Calculus text.  Again, his notation is different but the idea is the same.

.. image:: /figs/sphere_vol2.png
   :scale: 50 %

We divide the solid up into a series of concentric cylinders, centered in this case on the :math:`y`-axis.  Let's consider only the part of the sphere above the :math:`x`-axis.

The volume of each cylinder is its circumference times the height, multiplied by the little increment of radius (which is :math:`dx` here).

So as :math:`x` varies from :math:`0 \rightarrow R`, the circumference will be :math:`2 \pi x`, and the height will be :math:`y = \sqrt{R^2-x^2}`.  So the volume element is

.. math::

    dV = 2 \pi \ x \sqrt{R^2-x^2} \ dx
    
We get the volume by integrating:

.. math::

    V = \int dV 
    
    = 2 \pi \int x \sqrt{R^2-x^2} \ dx
    
    = 2 \pi \ [ \ -\frac{1}{3} (R^2 - x^2)^{3/2} \ ]

Evaluate between the bounds :math:`0 \rightarrow R`

.. math::

    -\frac{2}{3}\pi (R^2 - r^2)^{3/2} \bigg|_0^R 
    
    = -\frac{2}{3}\pi \ [ \ - (R^2)^{3/2} \ ] 
    
    = \frac{2}{3} \pi R^3

Multiply by two to obtain the total volume.

Why don't we try a cone of height :math:`H` and radius :math:`R`.  We vary :math:`x` from :math:`0 \rightarrow R`.  

.. image:: /figs/cone_shell2.png
   :scale: 50 %

The height is a little tricky.  When :math:`x=0`, the height is a *maximum*, :math:`H`.  For each value of :math:`x`, the height of the cone decreases in proportion to the height of the small cone that would lie on top of the shell we are constructing.  Thus, the height is *not*

.. math::

    h = \frac{H}{R} x
    
but instead

.. math::

    h = H - \frac{H}{R} x


The circumference is :math:`2 \pi x` so we have that the volume element is

.. math::

    dV = (H - \frac{H}{R} x) \ 2 \pi x \ dx
    
    V = \int dV 
    
    = \int (H - \frac{H}{R} x) \ 2 \pi x \ dx
    
    = 2 \pi \frac{H}{R} \int (Rx - x^2) \ dx
    
    = 2 \pi \frac{H}{R} (\frac{Rx^2}{2} - \frac{x^3}{3}) \ \bigg |_0^R

    = 2 \pi \frac{H}{R} (\frac{R^3}{2} - \frac{R^3}{3})
    
    = 2 \pi \frac{H}{R} \ \frac{R^3}{6}
    
    = \frac{1}{3}  \pi H R^2

The standard result.  Let's just quickly verify that the disk method gives the correct result as well.  Stand the cone on its tip.  Now, as :math:`y = 0 \rightarrow R`, the radius will be equal to :math:`yR/H`.  

The area of each disk is

.. math::

    A = \pi r^2
    
    = \pi y^2 (\frac{R}{H})^2
    
And the volume is

.. math::

    V = \int dV
    
    = \int A \ dy
    
    = \int \pi y^2 (\frac{R}{H})^2 \ dy

:math:`y` varies from :math:`0 \rightarrow H`

.. math::

    = \pi (\frac{R}{H})^2 \ \frac{y^3}{3} \ \bigg |_0^H
    
    = \pi (\frac{R}{H})^2 \ \frac{H^3}{3}
    
    = \frac{1}{3} \pi R^2 H


