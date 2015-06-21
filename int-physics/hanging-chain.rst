.. _hanging-chain:

#############
Hanging Chain
#############

The hanging chain, or catenary, is a famous problem solved by Johann Bernoulli about 1700.

https://en.wikipedia.org/wiki/Johann_Bernoulli

.. image:: /figs/hanging-chain-catenary.png
   :scale: 50 %
   
http://intmstat.com/blog/2010/05/hanging-chain-catenary.jpg

(By the way:  the parent site is like this book, only better:

http://www.intmath.com/help/sitemap.php

We imagine an ideal hanging cable (like the cable for a suspension bridge, without the vertical cables or bridge deck), although its ends might be at different heights.  The cable is ideal:  it will not stretch or contract, is perfectly flexible, and has constant mass per unit length. 

.. image:: /figs/Kline-16-10.png
   :scale: 50 % 

Consider a position :math:`P` on the chain.  The part of the chain below :math:`P` pulls down on it, because of its weight, and the part above pulls up.  This force is called tension, :math:`T`, and since the cable isn't moving, these forces are equal and opposite for every position on the chain.

The tension is in the direction of the angle :math:`\theta` tangent to the curve.  By convention it is positive upward.

We can decompose the tension :math:`T` into components in the :math:`x` and :math:`y` directions:

.. math::

    T = T_x + T_y
    
    T_x = T \cos \theta
    
    T_y = T \sin \theta

The curve traced out by the chain is described by :math:`y = f(x)`, and it has a tangent at each point which is the ratio :math:`T_y/T_x`.

===========
moving to Q
===========

Now consider moving from :math:`P` up to the nearby point :math:`Q`.  The weight acting at :math:`Q` is greater than that at :math:`P`.  If the arc length of :math:`L` to :math:`P` is :math:`s`, we add an additional small length :math:`\Delta s` to it in moving from :math:`P` to :math:`Q`.  The weight of that little segment is the weight per unit length :math:`w` \times :math:`\Delta s`.

The key point in the solution to this problem is that the additional force from the added weight changes :math:`T_y` (because gravity points downward), but does not affect :math:`T_x`.  :math:`T_x` is the *same* at every point in the chain, including at the lowest point, which has no weight acting on it.  At this point, :math:`L`, the tension is labeled as :math:`T_0`, but :math:`T_x` is equal everywhere.

.. math::

    T_x = T_0

The change in :math:`T_y` is:

.. math::

    \Delta T_y = w \Delta s
    
So

.. math::

    \frac{\Delta T_y}{\Delta s} = w

and as we pass to the limit:

.. math::

    \frac{d T_y}{ds} = w

Since :math:`w` is a constant, this means that

.. math::

    T_y = ws + D

where :math:`D` is a constant of integration.  But at :math:`L`, both :math:`s = 0` and :math:`T_y = 0`, so :math:`D = 0`, and so:

.. math::

    T_y = ws

This difference in :math:`T_y` at each point is what is responsible for the change in :math:`\theta` as we trace out the curve of the cable or chain.

=======
Tangent
=======

From above:

.. math::

    \frac{T_y}{T_x} = \frac{ws}{T_0}
    
but 

.. math::

    \frac{T_y}{T_x} = \frac{T \sin \theta}{T \cos \theta}
    
    = \tan \theta
    
    = y'

Let :math:`c = T_0/w` so

.. math::

    y' = \frac{s}{c}

============
Getting to x
============

The second point of real insight required for this problem is that we now have a differential equation relating :math:`y'` to :math:`s`, but we would like to have :math:`y` as a function of :math:`x`.

So finally, we need to relate :math:`s` to :math:`x,y`.  Recall that :math:`s` is *arc length*.  Well, we know a formula for that:

.. math::

    ds^2 = dx^2 + dy^2

and

.. math::

    \frac{ds}{dx} = \sqrt{1 + y'\ ^2}

    = \sqrt{1 + s^2/c^2}

Hence

.. math::

    dx = \frac{1}{\sqrt{1 + s^2/c^2}} \ ds

===========
Integration
===========

We do two substitutions.  First, let :math:`u = s/c` and then :math:`c \ du = ds` so

.. math::

    dx = c \frac{1}{\sqrt{1 + u^2}} \ du

Second, because we have :math:`\sqrt{1 + u^2}`, do a trig substitution with :math:`u/1 = \tan t`.  Then :math:`1/\sqrt{1 + u^2} = \cos t`, :math:`\sqrt{1 + u^2} = \sec t` and :math:`du = \sec^2 t \ dt` so

.. math::

    \int dx = c \int \cos t \ \sec^2 t \ dt
    
    = c \int \sec t \ dt

Integrate:

.. math::
    
    x = c \ln | \sec t + \tan t |
    
    = c \ln | \sqrt{1 + u^2} + u |
    
    = c \ln | \frac{s}{c} + \sqrt{1 + s^2/c^2} |

===========
Solve for s
===========

Exponentiate:

.. math::

    e^{x/c} = \frac{s}{c} + \sqrt{1 + s^2/c^2}

Let :math:`z = s/c`.  Then

.. math::

    (e^{x/c} - z)^2 = 1 + z^2
    
    e^{2x/c} - 2 z e^{x/c} + z^2 = 1 + z^2
    
    e^{2x/c} - 2 z e^{x/c} = 1
    
    e^{x/c}(e^{x/c} - 2z) = 1
    
    e^{x/c} - 2z = e^{-x/c}
    
    z = \frac{1}{2} (e^{x/c} - e^{-x/c})
    
    s = c \ \frac{e^{x/c} - e^{-x/c}}{2}
    
=========
Back to y
=========

Finally, recall that

.. math::

    y' = \frac{s}{c}
    
So 

.. math::

    y' = \frac{e^{x/c} - e^{-x/c}}{2}

Time to integrate:

.. math::

    y = \frac{1}{2} \ c (e^{x/c} + e^{-x/c})

This is the :ref:`hyperbolic cosine <hyperbolic>`.

.. math::

    y = c \ \cosh \frac{x}{c}
    
And

.. math::

    s = c \ \sinh \frac{x}{c}

Recall that :math:`c = T_0/w`.  There is more to the problem (see Kline, for example), we need to figure out how :math:`T_0` depends on the geometry of the problem.  But, this seems a good place to stop.

Let's just plot it:

.. image:: /figs/y=cosh(x).png
   :scale: 50 % 

It looks like a parabola but it's steeper.