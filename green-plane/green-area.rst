.. _green-area:

##############
Green for area
##############

State the theorem:

.. math::

    \oint_C \mathbf{F} \cdot \mathbf{r} = \iint_R \nabla \times \mathbf{F} \ dA 

    \int_C M \ dx + N \ dy = \iint_R (N_x - M_y) \ dx \ dy 

To start with, if :math:`\mathbf{F}` is the gradient of some function, we call such a function the potential, and the integral of the work over a closed path is just zero.

.. math::

    \mathbf{F} = \ <y,x> 

    f = xy 

Suppose we take the line integral of :math:`\mathbf{F}\cdot \mathbf{r}`  over the unit square :math:`(0,0)` to :math:`(0,1)`, etc.

.. math::

    \oint_C y \ dx + x \ dy = 

I get :math:`0 + 1 -1 + 0 = 0`.

A sign change can make all the difference.

.. math::

    \mathbf{F} = \ <-y,x> 

    N_x - M_y = 1 - -1 = 2 \ne 0 

A common field with zero curl in 3D is

.. math::

    \mathbf{F} = \ <yz,xz,xy> 

    \nabla \times \mathbf{F} = \ <R_y-Q_z,P_z-R_x,Q_x-P_y> 

    = x - x, y - y, z - z > \ = \mathbf{0}

Another very useful case is where the curl is just equal to :math:`1` (or :math:`2`):

Suppose :math:`\mathbf{F} = \langle -y , x \rangle`.  Then:

.. math::

    \iint_R (N_x - M_y) \ dx \ dy = \iint_R 2 \ dx \ dy
    
    = 2 \iint_R \ dx \ dy = 2 A

where :math:`A` is the area enclosed by the curve.  Thus:

.. math::

    2A = \oint_C \mathbf{F} \cdot \mathbf{r}
    
    = \oint_C M \ dx + N \ dy
    
    = \oint_C -y \ dx + x \ dy

======
Auroux
======

Suppose

.. math::

    \mathbf{F} = \ <ye^{-x},\frac{1}{2}x^2 - e^{-x}> 

And suppose further that the region is the unit disk centered at :math:`(2,0)`  The line integral does not look like fun, and the region is no help, but

.. math::

    N_x - M_y = x + e^{-x} - e^{-x} = x 

So the integral of the curl is just

.. math::

    \iint_R x \ dA 

which is :math:`\overline{x}` on this disk, which is just equal to :math:`2` by symmetry.

====
Paul
====

Given

.. math::

    \mathbf{F} = \ <xy,x^2y^3> 

The curl is

.. math::

    N_x - M_y = 2xy^3 - x 

If the region is the triangle :math:`(0,0) \rightarrow (1,0) \rightarrow (1,2) \rightarrow (0,0)` then

.. math::

    \int_0^1 \int_0^{2x} 2xy^3 - x \ dy \ dx 

inner

.. math::

    = \frac{1}{2}xy^4 - xy \ \bigg |_0^{2x} = 8x^5 - 2x^2 

outer

.. math::

    \int_0^1 8x^5 - 2x^2 \ dx = \frac{8}{6}x^6 - \frac{2}{3}x^3 \bigg |_0^1 
    
    = \frac{8}{6} - \frac{2}{3} = \frac{2}{3} 

Try the line integral to check it.

=======
Ellipse
=======

Of course, my favorite example is the area of the ellipse.  Suppose :math:`N_x - M_y = 1`.  Then the curl integral is the area of the region.  If the components of :math:`\mathbf{F}` are :math:`N = x/2` and :math:`M=-y/2`, this condition holds.  Parametrize the ellipse.

.. math::

    x = a \cos \theta 

    y = b \sin \theta 

So, for the left hand side we have

.. math::

    \int_C M \ dx + N \ dy = \int_C -\frac{1}{2}y \ dx + \frac{1}{2}x \ dy 

    = \int_0^{2\pi} (-\frac{1}{2})(b \sin \theta) \ (-a \sin \theta) \ d \theta \ + (\frac{1}{2})(a \cos \theta) \ (b \cos \theta) \ d\theta 

    = ab \int_0^{2\pi} \frac{1}{2} + \frac{1}{2} \ d \theta = 2 \pi a b

===========
Hypocycloid
===========

Here is a problem from Marsden.

Take the *hypocycloid* with equation:

.. math::

    x^{2/3} + y^{2/3} = a^{2/3}

It looks like this:

.. image:: /figs/hypocycloid.png
   :scale: 50 % 

The area formula could be useful here!

.. math::

    2A = \oint_C -y \ dx + x \ dy

Don't forget that factor of two.

A trick is to parametrize the curve as 

.. math::

    x = a \cos^3 t
    
    y = a \sin^3 t
    
    0 \le t \le 2 \pi

We can see that this works by plugging it into the equation.  So now we have that

.. math::

    dx = 3a \cos^2 t \ (-\sin t) \ dt
    
    dy = 3a \sin^2 t \cos t \ dt

and

.. math::

    2A = \oint_C -y \ dx + x \ dy
    
    = 3a^2 \int_0^{2 \pi} ( \sin^4 t \cos^2 t + \cos^4 t \sin t) \ dt

which really looks like no fun until we factor out :math:`\sin^2 t \cos^2 t`:

.. math::

    2A = 3a^2 \int_0^{2 \pi} \sin^2 t \cos^2 t \ dt
    
We can convert this to :math:`\cos^2 t - \cos^4 t` and use our formula from :ref:`here <cos^n>`.

.. math::

    \int \cos^2 x \ dx =   \frac{1}{2} \sin x \cos x +  \frac{1}{2} \int \cos^{0} x \ dx 

    = \frac{1}{2}(\sin x \cos x + x)  

    \int \cos^4 x \ dx =   \frac{1}{4} \sin x \cos^3 x +  \frac{3}{4} \int \cos^{2} x \ dx 

    = \frac{1}{4} \sin x \cos^3 x +  \frac{3}{8} (\sin x \cos x + x)  

The nice thing is that every term with sine and cosine drops out at the bounds of the interval (:math:`0 \Rightarrow 2 \pi`) and we are just left with

.. math::

    2A = 3a^2 \ [ \ \frac{1}{2}t - \frac{3}{8} t \ \bigg |_0^{2 \pi} \ ]
    
    = 3a^2 \ [ \ \frac{1}{8}t \ \bigg |_0^{2 \pi} \ ]
    
    = 3a^2 \ \frac{\pi}{4}
    
    A = \frac{3}{8} \pi a^2

A trick I found on the web is to say that

.. math::

    \sin^2 t \cos^2 t = (\sin t \cos t)^2 
    
    = (\frac{\sin(2t)}{2})^2
    
    = \frac{1}{4} \sin^2 2t
    
    = \frac{1}{4} \ \frac{(1 - \cos 4t)}{2}

which integrates to give :math:`t/8` plus some a term with :math:`\sin 4t` that will go away at the bounds of the interval and we have the same as before.

