.. _Center of mass:

##############
Center of mass
##############

As you know, in single variable calculus we interpret the integral of :math:`f(x)` over a closed interval :math:`[a,b]`

.. math::

    \int_a^b f(x) dx 

as the area underneath the curve :math:`y=f(x)` between the lines :math:`x=a` and :math:`x=b` (our limits).  

In multi-variable calculus we compute the double integral over the same region as follows

.. math::

    \int_{x=a}^{x=b} \int_{y=0}^{y=f(x)} dy \ dx 
    
    =  \int_{x=a}^b y \bigg |_0^{f(x)}  \ dx 
    
    = \int_a^b f(x) \ dx 

To be more general, we'd just say that we compute the double integral over the region :math:`R`

.. math::

    \iint\limits_{R} dx \ dy  

with the understanding that we can compute the inner integral with respect to either :math:`x` or :math:`y`, whichever is more convenient.

==============
Center of mass
==============

We can extend this approach by computing

.. math::

    \iint\limits_{R} g(x,y) \ dx \ dy  

Suppose, for example, that :math:`g(x,y)` is a function that gives the density of a flat object for each coordinate :math:`x,y`.  In this case we usually use the label :math:`\rho (x,y)`.

This integral gives the total mass of the object:

.. math::

    M = \iint\limits_{R} \rho (x,y) \ dx \ dy  

To find the center of mass we compute

.. math::

    M_x = \iint\limits_{R} \rho (x,y)\  y \ dx \ dy  

    M_y = \iint\limits_{R} \rho (x,y) \ x \ dx \ dy 

And then finally

.. math::

    \bar{x} = \frac{M_y}{M} 

    \bar{y} = \frac{M_x}{M} 

+++++++
Example
+++++++

Let's do a simple example.  Suppose the region is a rectangle with the origin at one corner and the point :math:`(1,2)` as the opposite corner.  

It's just a 2D box of width :math:`1` and height :math:`2`.  If the density function is :math:`\rho (x,y) = xy`, then

.. math::

    M = \iint\limits_{R} \rho (x,y) \ dx \ dy =  \int_{y=0}^{y=2} \int_{x=0}^{x=1} xy \ dx \ dy  

The inner integral is

.. math::

    \frac{1}{2} x^2 y \ \bigg |_0^{1} = \frac{1}{2} y 

and the rest is

.. math::

    M = \int_{y=0}^{y=2} \frac{1}{2} y \ dy = \frac{1}{4} y^2 \  \bigg |_0^{2} = 1 

Now

.. math::

    M_x =  \int_{y=0}^{y=2} \int_{x=0}^{x=1} xy^2 \ dx \ dy  

The inner integral is

.. math::

    \frac{1}{2} x^2 y^2 \ \bigg |_0^{1} = \frac{1}{2} y^2 

and the rest is

.. math::

    M_x  = \int_{y=0}^{y=2} \frac{1}{2} y^2 \ dy = \frac{1}{6} y^3 \  \bigg |_0^{2} = \frac{4}{3} 

Last, :math:`M_y` can be done in the same order

.. math::

    M_y =  \int_{y=0}^{y=2} \int_{x=0}^{x=1} x^2y \ dx \ dy  

The inner integral is

.. math::

    \frac{1}{3} x^3 y \ \bigg |_0^{1} = \frac{1}{3} y 

and the rest is

.. math::

    M_y  = \int_{y=0}^{y=2} \frac{1}{3} y \ dy = \frac{1}{6} y^2 \  \bigg |_0^{2} = \frac{2}{3} 

Thus our center of mass is at the point :math:`2/3,4/3`.  If it had made our lives easier, either integral could be computed with respect to :math:`y` before :math:`x`.

The answer makes sense.  The density increases as we go to the right and up, so the center of mass is offset from the geometric center in the same direction.

+++++++
Example
+++++++

If the density is constant, then we can leave it out of the calculation.

This integral gives the total area of the object:

.. math::

    A = \iint\limits_{R} \ dx \ dy  

To find the center of mass we compute

.. math::

    M_x = \iint\limits_{R}  y \ dx \ dy  

    M_y = \iint\limits_{R}  x \ dx \ dy 

And then finally

.. math::

    \bar{x} = \frac{M_y}{A} 

    \bar{y} = \frac{M_x}{A}

Let's do the calculation for a right triangle with sides :math:`p` (on the :math:`x`-axis) and :math:`q` (on the :math:`y` axis).

The equation for the line connecting :math:`(0,q)` and :math:`(p,0)` is

.. math::

    y = -\frac{q}{p}x + q

The double integral is

.. math::

    M_y = \int_0^p \int_0^{-\frac{q}{p}x + q} x \ dy \ dx
    
    = \int_0^p -\frac{q}{p}x^2 + qx \ dx
    
    = -\frac{q}{p} \ \frac{x^3}{3} + q \frac{x^2}{2} \ \bigg |_0^p
    
    = -\frac{1}{3}p^2q + \frac{1}{2}p^2q = \frac{1}{6} p^2 q
    
Then

.. math::

    \bar{x} = \frac{1/6 \ p^2 q}{A}
    
    = \frac{1/6 \ p^2 q}{1/2 \ p q} = \frac{1}{3} p

Similarly

.. math::

    \bar{y} = \frac{1/6 \ p^2 q}{1/2 \ p q} = \frac{1}{3} q

and the centroid of the triangle is at

.. math::

    (\bar{x},\bar{y}) = (p/3, p/3)

If you draw this point inside the triangle, and draw the ray through that point and extending to the hypotenuse at :math:`M`

.. image:: /figs/CM-centroid.png
   :scale: 50 %

it is easy to see that not only is the inset triangle similar to the large one, but that both of the two medium-sized triangles including the ray :math:`OM` are isosceles (because they have two angles the same), and therefore, :math:`M` lies at the midpoint of the hypotenuse.

Thus, the center of mass is at the centroid of this triangle.  This makes a lot of sense, since each midpoint bisector divides the triangle into two regions of equal area.

Since we can turn any acute triangle into two adjacent right triangles by dropping an altitude, the resulting centers of mass can be averaged, so can the centroids.
