.. _circles:

#############
Little pieces
#############

Integration can be used to compute more than just areas or even volumes, as long as we can form little pieces that are related by a formula.

We learn in differential calculus to compute the derivative with respect to the independent variable.  Consider the formula for the area of a circle:

.. math::

    A = \pi r^2

compute the derivative

.. math::

    \frac{dA}{dr} = 2 \pi r
    
    dA =  2 \pi r \ dr
    
The derivative is a rate of change.  If we increase the radius by "a little bit" :math:`dr`, the area will change by :math:`dA`, with the rate of exchange between the two given by the formula.  When we ask "how does the area grow with a small change in radius", the answer is that it grows like the circumference :math:`2 \pi r`, times the small change in radius :math:`dr`.

To illustrate, we will calculate the area of a circle, using pieces obtained by one of three different strategies:  divide the circle into either rings, slices of pie, or else rectangles bounded by the function obtained by solving :math:`x^2 + y^2 = R^2`, and using the positive square root.

.. image:: /figs/circles.png
   :scale: 50 %

These three approaches are illustrated in the figure above.

=====
Rings
=====

In the first approach (left panel), we imagine the area being computed by adding up the individual areas of a series of very thin, concentric rings.

The total area to be computed is that of a circle with a definite, fixed size, and we denote the radius of this circle by capital :math:`R`, a constant.  On the other hand, the series of rings ranges from the origin of the circle to the circumference of the outmost ring.  Each ring in this progression has a different radius, so we use a lowercase :math:`r` to describe them, with :math:`r` being a variable---:math:`r` varies from :math:`0` at the origin to :math:`R` at the outside of the circle.

We are working with areas, figures in two dimensions, so the individual rings are similar to the peel or rind surrounding an infinitely thin slice of lemon.  

The area of the ring is the length times the width.  The length is the circumference, which is :math:`2 \pi R` for the outermost ring, but for any ring in general it is :math:`2 \pi r`. The length is multiplied by the width of the slice, which is a small element of radius, :math:`dr`.  The small element of area contributed by an individual ring is :math:`dA`:

.. math::

    dA = 2 \pi r \ dr

Another way to explain this equation is to ask the question:  **how does area change with increasing radius**?  If we take a circle and increase its radius by a bit, how does the area change?  Again, the answer is, it changes in proportion to the circumference, :math:`2 \pi r`.

Proceeding from the equation, we obtain the total area by summing the areas for each of the series of rings.

.. math::

    A = \int dA
    
    = \int_0^R 2 \pi r \ dr

It's worth emphasizing how this view is different than (but similar to) our first uses of integration:  the pieces of area are no longer rectangles but circles.  But it poses most clearly the question we are trying to answer, "how does area vary with :math:`r`"?

The solution is

.. math::

    \int_0^R 2 \pi r \ dr 
    
    = 2 \pi \ \frac{1}{2}r^2 \ \bigg|_{r=0}^{r=R} = \pi R^2

As expected.

======
Wedges
======

.. image:: /figs/circles.png
   :scale: 50 %

In the second method (middle panel), we first need to find the area of a wedge.  For a thin enough slice, a wedge is a triangle with its base on the circumference of the circle, and its area  has the familiar formula: one-half the base times the height.  The height is :math:`R`, the radius of the circle.  

For the base we need the length of a piece of arc of a circle.  Recall that by definition, if we have a unit circle, then the angle of a wedge is equal to the arc it cuts out.  Thus, the total length if we go all the way around the unit circle is :math:`2 \pi`.  For a circle with radius :math:`R`, the length going all the way around is :math:`2 \pi R`, and the length of arc for any angle :math:`\theta` is :math:`\theta \times R`.

The area is built up out of a series of wedges that are almost infinitely slender, with angle :math:`d \theta`, so each wedge has a base measuring :math:`R \ d \theta`.  The area of any wedge is then

.. math::

    dA = \frac{1}{2} R \ R \ d\theta

And we have for the total area

.. math::

    A = \int dA 
    
    = \int  \frac{1}{2} R \ R \ d\theta
    
    = \frac{1}{2} R^2 \int_{\theta=0}^{\theta=2\pi} \ d\theta
    
    = \frac{1}{2} R^2 \theta \  \bigg|_{\theta=0}^{\theta=2\pi}
    
    =  \pi R^2

===========
Big picture
===========

Before we do the third calculation for area under the curve :math:`\sqrt{1-x^2}`, let's reinforce the general idea with another striking example.  

We ask, for any quantity including an area or volume, "how does it grow as the independent variable :math:`r` or :math:`x` or :math:`t` changes by a little bit?".

In the case of the circle, area grows like the circumference.  To put it another way, the circumference is the derivative of the area.

Consider a filled sphere (a mathematical "ball").  How does it grow?  It grows like the surface area.  Another way to state this is that the surface area is the derivative of the volume:

.. math::

    dV = 4 \pi r^2\ dr

The volume is the integral of the surface area times the differential :math:`dr`:

.. math::

    V = \int dV 
    
    = \int_0^R 4 \pi r^2 \ dr 
    
    = \frac{4}{3} \pi r^3 \ \bigg |_0^R 
    
    = \frac{4}{3} \pi R^3

====================
Area under the curve
====================

The third view is the most familiar, but it has a somewhat harder calculation.  Nevertheless, we will do it here for completeness.  

We need to find the area under the positive square root in the equation for a circle.  For this problem, the limits should be :math:`x=0  \rightarrow R` or :math:`x=-R  \rightarrow R`.  Start with the standard

.. math::

    x^2 + y^2 = R^2
    
    y = \sqrt{R^2-x^2}

We use a :ref:`trigonometric substitution <trig_sub>`:

.. math::

    x = R \sin \theta
    
    y = R \cos \theta
    
    dx = R \cos \theta \ d\theta
    
The integral we want to calculate is:

.. math::

    \int \sqrt{R^2 - x^2} \ dx

We substitute :math:`x=R \sin \theta`:

.. math::

    \sqrt{R^2 - x^2}
    
    =  \sqrt{R^2 - R^2 \sin^2 \theta}
    
    = R \sqrt{1 - \sin^2 \theta}
    
    = R \sqrt{\cos^2 \theta}
    
    = R \cos \theta
    
plugging in for :math:`dx` we obtain:

.. math::

    = \int R \cos \theta \ R \cos \theta \ d\theta
    
    = R^2 \int \cos^2 \theta \ d\theta

Alternatively, we might have just recognized that the value we want to integrate is :math:`y`

.. math::

    \int y \ dx
    
    = \int R \cos \theta \ R \ cos \  \theta \ d\theta
    
    = R^2 \int \cos^2 \theta \ d\theta

We will look at this integral in detail :ref:`here <cosine_sq>`.  Let's solve it now by looking at a derivative: 

.. math::

    \frac{d}{dx} \sin x \cos x 
    
    = -\sin^2 x + \cos^2 x
    
    = \cos^2 x - 1 + \cos^2 x
    
    = 2 \cos^2 x - 1

Integrating both sides we have

.. math::

    \int 2 \cos^2 x - 1 \ dx = \int \frac{d}{dx} \sin x \cos x \ dx
    
    2 \int \cos^2 x - x = \sin x \cos x
    
    \int \cos^2 x = \frac{1}{2} ( x + \sin x \cos x)

=============================
Area under the curve:  limits
=============================

To actually compute the area, we need to evaluate at the limits.  Suppose we take them for the original integral as 

.. math::

    x = 0 \rightarrow  x = R

and agree that we need to multiply the final result by :math:`4`, because we're calculating the area only for the upper-right quadrant of the circle. 

After the substitution of :math:`\theta` for :math:`x`, these limits become

.. math::

    x = 0 = R \sin \theta
    
    \sin \theta = 0
    
    \theta =  0

and

.. math::
    
    x = R = R \sin \theta
    
    \sin \theta = 1
    
    \theta = \frac{ \pi}{2}

With an upper limit equal to :math:`\pi/2`, and :math:`0` as the lower limit, the term in brackets is

.. math::

    \frac{1}{2} ( x + \sin x \cos x) \ \bigg |_0^{\pi/2}
    
    = \frac{\pi}{4}
        
Recall that we had a factor of :math:`R^2` preceeding the integral so:

.. math::
 
    A = \frac{1}{4} \pi R^2
    
And this is one-fourth of the total, hence the total area is :math:`A =\pi R^2`.
