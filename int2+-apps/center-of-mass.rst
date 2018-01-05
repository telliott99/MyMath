.. _Center of mass:

##############
Center of mass
##############

In single variable calculus we interpret the integral of :math:`f(x)` over a closed interval :math:`[a,b]`

.. math::

    \int_{x=a}^{x=b} f(x) dx 

as the area underneath the curve :math:`y=f(x)` between the vertical lines :math:`x=a` and :math:`x=b` (the bounds, or limits).  

In multi-variable calculus we compute the double integral over the same region as follows

.. math::

    \int_{x=a}^{x=b} \int_{y=0}^{y=f(x)} dy \ dx 
    
    = \int_{x=a}^b y \bigg |_0^{f(x)}  \ dx 
    
    = \int_a^b f(x) \ dx 

To be more general, we'd just say that we compute the double integral over the region :math:`R`

.. math::

    \iint\limits_{R} \ dx \ dy

with the understanding that we can compute the inner integral with respect to either :math:`x` or :math:`y`, whichever is more convenient.  To be completely general, we might use the area element :math:`dA`:

.. math::

    \iint\limits_{R} \ dA

Sometimes it is more convenient to use polar coordinates.  Then, the area element is (see :ref:`here <polar-area>`):

.. math::

    dA = r \ dr \ d \theta

==============
Center of mass
==============

We can extend this approach by computing a function :math:`g(x,y)` over the region

.. math::

    \iint\limits_{R} g(x,y) \ dx \ dy  

Suppose, for example, that :math:`g` is a function that gives the density of a flat object for each coordinate :math:`x,y`.  In this case we usually use the label :math:`\rho (x,y)`.

This integral gives the total mass of the object:

.. math::

    M = \iint\limits_{R} \rho (x,y) \ dx \ dy

If we want to find the center of mass with respect to a given coordinate (say, :math:`x`) compute:

.. math::

    \iint\limits_{R} \rho (x,y)\  x \ dx \ dy  

and then divide by :math:`M`.  We can recast this definition as

.. math::

    \iint\limits_{R} \rho (x,y)\  \bar{x} \ dx \ dy = \iint\limits_{R} \rho (x,y)\  x \ dx \ dy
    
since the center of mass :math:`\bar{x}` is a constant we can say that:

.. math::

    = \bar{x} \iint\limits_{R} \rho (x,y)\ \ dx \ dy = \iint\limits_{R} \rho (x,y)\  x \ dx \ dy

which is the same thing.

If the density is a constant and we set that equal to :math:`1`, we get the volume (or the area in two dimensions), and the centroid of the object.

.. math::

    \iint\limits_{R}  \bar{x} \ dx \ dy = \iint\limits_{R}  x \ dx \ dy

+++++++
Example
+++++++

Consider a hemisphere of radius :math:`a` with its diameter aligned along the :math:`y`-axis so it lies in the first and fourth quadrants.

We want to calculate first:

.. math::

    \iint_R x \ dA

Polar coordinates are an obvious choice for this problem:

.. math::

    x = r \cos \theta
    
    \int_{-\pi/2}^{\pi/2} \int_0^a r \cos \theta \ r \ dr \ d \theta
    
The :math:`\theta` and :math:`r` parts of the integral are independent:

.. math::

    \int_{-\pi/2}^{\pi/2} \cos \theta \ d \theta = \sin \theta \ \bigg |_{-\pi/2}^{\pi/2} = 2
    
    \int_0^a r^2 \ dr = \frac{r^3}{3} \ \bigg |_0^a = \frac{a^3}{3}
    
So the integral is 

.. math::

    \frac{2a^3}{3}

Finally, divide by the area, which is one-half of :math:`\pi a^2`.  It *could* be found by integration

.. math::
    
    \int_{-\pi/2}^{\pi/2} \int_0^a r \ dr \ d \theta = \pi \frac{r^2}{2}


So the final answer is:

.. math::

    \bar{x} = \frac{2a^3}{3} \ \frac{2}{\pi a^2} = \frac{4a}{3 \pi}
    
+++++++
Example
+++++++

Suppose the region is a rectangle with the origin at one corner and the point :math:`(1,2)` as the opposite corner.  

It's just a 2D box of width :math:`1` and height :math:`2`.  If the density function is :math:`\rho (x,y) = xy`, then

.. math::

    M = \iint\limits_{R} \rho (x,y) \ dx \ dy =  \int_{y=0}^{y=2} \int_{x=0}^{x=1} xy \ dx \ dy  

We compute the mass first.  The inner integral is

.. math::

    \frac{1}{2} x^2 y \ \bigg |_0^{1} = \frac{1}{2} y 

and the rest is

.. math::

    M = \int_{y=0}^{y=2} \frac{1}{2} y \ dy = \frac{1}{4} y^2 \  \bigg |_0^{2} = 1 

Now for :math:`M_x`:

.. math::

    M_x = \int_{y=0}^{y=2} \int_{x=0}^{x=1} x \ xy \ dx \ dy 

The inner integral is

.. math::

    \frac{1}{3} x^3 y \ \bigg |_0^{1} = \frac{1}{3} y 

and the rest is

.. math::

    M_x  = \int_{y=0}^{y=2} \frac{1}{3} y \ dy = \frac{1}{6} y^2 \  \bigg |_0^{2} = \frac{2}{3} 

:math:`M_y` can be done in the same order

.. math::

    M_y = \int_{y=0}^{y=2} \int_{x=0}^{x=1} y \ xy \ dx \ dy 

The inner integral is

.. math::

    \frac{1}{2} x^2 y^2 \ \bigg |_0^{1} = \frac{1}{2} y^2 

and the rest is

.. math::

    M_y  = \int_{y=0}^{y=2} \frac{1}{2} y^2 \ dy = \frac{1}{6} y^3 \  \bigg |_0^{2} = \frac{4}{3} 

Thus our center of mass is at the point :math:`2/3,4/3`.  If it had made our lives easier, either integral could be computed with respect to :math:`y` before :math:`x`.

The answer makes sense.  The density increases as we go to the right and up, so the center of mass is offset from the geometric center in the same direction.

+++++++
Example
+++++++

Here is another calculation where the density is constant, so we can leave it out of the calculation.

Suppose we have an inverted right-circular cone.  Its vertex is at the origin and it opens up.  The height is equal to the radius :math:`z=r`, at any cross-section.

We are asked to find :math:`\bar{z}`.

.. math::

    \bar{z} \iiint\limits_{V} \ dV = \iiint\limits_{V} z \ dV
    
It makes sense to do this one in cylindrical coordinates, where the volume element

.. math::

    dV = dz \ r \ dr \ d \theta
    
To set up the integral, first, fixing the angle :math:`\theta`, if we also fix :math:`z` at some height :math:`0 \rightarrow h`, then :math:`r = 0 \rightarrow z`, so the volume integral is:

.. math::

    V = \int_0^{2 \pi} \int_{z=0}^h \int_0^z r \ dr \ dz \ d \theta
    
inner:

.. math::

    \int_0^z r \ dr = \frac{r^2}{2} \ \bigg |_0^z = \frac{z^2}{2}

middle:

.. math::

    \int_{z=0}^h \frac{z^2}{2} \ dz = \frac{z^3}{6} \ \bigg |_0^z = \frac{h^3}{6}
    
times :math:`2 \pi = h^3/3`.  This is the volume.

For the other integral we add a term of :math:`z`, which is a constant for the inner integral and then the middle is:

.. math::

    \int_{z=0}^h z \ \frac{z^2}{2} \ dz = \frac{z^4}{8} \ \bigg |_0^z = \frac{h^4}{8} 
    
Multiply by :math:`2 \pi` and divide by the volume:

.. math::

    \bar{z} = 2 \pi \ \frac{h^4}{8} \ \frac{3}{h^3} = \frac{3}{4} h

+++++++
Example
+++++++

This integral gives the total area of the object:

.. math::

    A = \iint\limits_{R} \ dx \ dy  

To find the center of mass we compute

.. math::

    M_x = \iint\limits_{R}  x \ dx \ dy  

    M_y = \iint\limits_{R}  y \ dx \ dy 

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

it is easy to see that not only is the inset triangle similar to the large one, but that both of the two medium-sized triangles including the ray :math:`OM` are isosceles---because they have two angles the same---, and therefore, :math:`M` lies at the midpoint of the hypotenuse.

Alternatively, recognize that the point :math:`M` lies on the two lines

.. math::

    y = \frac{q}{p} x 
    
    y = -\frac{q}{p}x + q

so its coordinates are:

.. math::
        
    2y = q
    
    y = \frac{q}{2}
    
    x = \frac{p}{q} y = \frac{p}{2}

Thus, the center of mass is at the *centroid* of this triangle.  This makes a lot of sense, since each midpoint bisector divides the triangle into two regions of equal area.

Since we can turn any acute triangle into two adjacent right triangles by dropping an altitude, the resulting centers of mass can be averaged, and so can the centroids.
