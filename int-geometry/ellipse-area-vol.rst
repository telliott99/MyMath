.. _ellipse-area-vol:

#######
Ellipse
#######

The area of an ellipse can be computed in several different ways, all interesting.  The simplest way is rescaling.  In :math:`xy`-coordinates, the formula is

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

    (\frac{bx}{a})^2 + y^2 = b^2

What this says is that if the :math:`x` value of each point on the ellipse is re-scaled by a factor of :math:`b/a`, the result is

.. math::

    u = \frac{b}{a}x

    u^2 + y^2 = b^2

a circle of radius :math:`b` and area :math:`A = \pi b^2`.  Because the scaling factor is only in the :math:`x`-direction

.. math::

    x = \frac{a}{b}u

the area of the original ellipse is bigger by a factor of :math:`a/b`

.. math::

    A = \pi b^2 \ \frac{a}{b} = \pi ab

=====
Guess
=====

We might also argue as follows.  The area of the ellipse clearly depends on both :math:`a` and :math:`b`, so we write

.. math::

    A = k a b

where :math:`k` is an unknown constant.  Now, if :math:`a=b`, we obtain

.. math::

    A = k a^2

but this is just a circle, with known area

.. math::

    A = \pi a^2 = k a^2

Hence :math:`k = \pi` and :math:`A = \pi ab`.

========================
Single variable calculus
========================

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

Solve the equation of the ellipse for :math:`y`

.. math::

    y = b \sqrt{1 - \frac{x^2}{a^2} } \ dx

We take the positive square root, and integrate from :math:`x = 0 \rightarrow a`, and should obtain :math:`1/4` the area of the ellipse.

.. math::

    A = 4 b \int \sqrt{1 - \frac{x^2}{a^2} }

Get rid of the :math:`a` by substitution.  Let :math:`u = x/a`, so :math:`au = x` and :math:`a \ du = dx`, then

.. math::

    A = 4 ab \int \sqrt{1 - u^2} \ du

The next step is to recognize that :math:`f(x) = \sqrt{1-u^2}` is the equation of a circle.  We need to be careful with the bounds.  Originally, we had :math:`x = 0 \rightarrow a`.  Since :math:`u = x/a`, now we have :math:`u = 0 \rightarrow 1`.  Thus, we have a unit circle.

Since we are integrating over the first quadrant, the value of the area is just :math:`\pi/4`.  The whole thing is :math:`\pi` and we pick up the factor :math:`ab` from outside to give :math:`A = \pi ab`.

To actually compute this, do a trig substitution.  If :math:`u` is the side opposite angle :math:`\theta`, and :math:`1` is the hypotenuse, then 

.. math::

    \sqrt{1-u^2} = \cos \theta

    u = \sin \theta

    du = \cos \theta \ \ d\theta

and the integral becomes

.. math::

    4 ab \int \cos^2 \theta \ d\theta

Before we do the integration, consider the changing bounds.  We originally had :math:`x = 0 \rightarrow a`, in changing to :math:`u` by remembering that

.. math::

    au = x

we obtain :math:`u = 0 \rightarrow 1`.  Then, in changing to :math:`\theta` we have

.. math::

    u = \sin \theta

    \theta = \sin^{-1} u

and we have :math:`\theta = 0 \rightarrow \pi/2` for the first quadrant.

I'm not going to do the integral (see :ref:`here <cosine_sq>`, but just give the result

.. math::

    \int \cos^2 \theta \ d \theta = \frac{1}{2} (\theta + \sin \theta \cos \theta)

(and there are other ways to write it).  But we will take a moment to check that by differentiating

.. math::

    \frac{d}{d \theta} \ \frac{1}{2} (\theta + \sin \theta \cos \theta)

    =  \frac{1}{2}(1 + \cos^2 \theta - \sin^2 \theta)

    =  \frac{1}{2}(1 + \cos^2 \theta + \cos^2 \theta - 1) = \cos^2 \theta

So we need to evaluate

.. math::

    4ab \ [ \ \frac{1}{2} (\theta + \sin \theta \cos \theta) \ ] \ \bigg |_0^{\pi/2}

Only one term is non-zero and that is :math:`\theta = \pi/2` at the upper limit.  We obtain

.. math::

    A = 4ab \ (\frac{1}{2}\ \frac{\pi}{2}) = \pi ab

Finally, suppose you think it's not politically correct to re-scale or do a U-substitution.  We have solved the equation of the ellipse for :math:`y` 

.. math::

     y^2 = -\frac{b^2}{a^2}x^2 + b^2 
     
     = b^2 (1 - \frac{x^2}{a^2}) 
     
     = \frac{b^2}{a^2} (a^2 - x^2)
     
     y = \frac{b}{a} \sqrt{a^2 - x^2}
    
and we insist on finding the integral directly (in the first quadrant):

.. math::

    A = \int_0^a \frac{b}{a} \sqrt{a^2 - x^2}

Use a trig substitution:

.. math::

    x = a \sin \theta
    
    dx = a \cos \theta
    
    \sqrt{a^2 - x^2} = a \cos \theta

See :ref:`here <trig_sub>` for a diagram.  Then we have

.. math::

    A = \int \frac{b}{a} a^2 \cos^2 \theta \ d \theta
    
The bounds on :math:`\theta` are :math:`0 \rightarrow \pi/2`.  But we are going to switch back to :math:`x` so we don't actually need that.

We know the integral of cosine-squared (:ref:`here <cosine_sq>`).

.. math::

    \int \cos^2 \theta \ d \theta = \frac{1}{2} (\theta + \sin \theta \cos \theta)
    
    A = \frac{1}{2} (\sin^{-1} \frac{x}{a} + \frac{x}{a^2} \sqrt{a^2-x^2} )

so

.. math::

    A = \frac{b}{2a} a^2 (\sin^{-1} \frac{x}{a} + \frac{x}{a^2} \sqrt{a^2-x^2} )

    = \frac{b}{2a} (a^2 \sin^{-1} \frac{x}{a} + x \sqrt{a^2-x^2} )

Evaluate between :math:`x = 0 \rightarrow a`.  The second term is zero at both bounds.

.. math::

    = \frac{b}{2a} (a^2 (\frac{\pi}{2}-0) + (0-0) )
    
    = \frac{\pi a b}{4}

but this is just the first quadrant so the final answer is the familiar :math:`\pi a b`.

======
Volume
======

We want to calculate the volume generated by rotation of an ellipse (centered at the origin) about the x-axis.

.. image:: /figs/ellipse.png
   :scale: 50 %

The basic idea is that the cross-section of each little slice in the direction we are integrating is a circle with radius equal to :math:`f(x)`.

.. math::

    y = f(x)
    
The area of each slice is a function of :math:`x`, given by

.. math::

    A = \pi \ y^2
    
We add up all those little slices by doing this integral

.. math::

    V = \pi \int y^2 \ dx
    
For the general ellipse we have the equation

.. math::

    \frac{ x^2 }{ a^2 } + \frac{ y^2 }{ b^2 } = 1

    y^2 =  b^2 (1 - \frac{ x^2 }{ a^2 })
    
So the integral is

.. math::

    V = \pi \int y^2 dx = \pi \int b^2 (1 - \frac{ x^2 }{ a^2 }) \ dx

which is just

.. math::

    V = \pi b^2 \ ( x - \frac{ x^3 }{ 3a^2 } )

evaluated between :math:`x = -a \rightarrow x = a`

.. math::

    V = \pi  b^2 [ (a - \frac{a}{3}) - (-a - \frac{-a}{3}  ) ] =  \frac{4}{3} \pi b^2 a

This is quite beautiful.  We get a squared contribution for the :math:`b` component, which describes the "stretching" of the ellipse in the direction of the axis of rotation.  Rotation around the :math:`y`-axis would give a formula containing :math:`a^2`, and a bigger solid by a factor of :math:`a/b`.
