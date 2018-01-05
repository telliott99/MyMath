.. _cosine_sq:

##############
Cosine squared
##############

We want to find the integral of

.. math::

    \int \cos^2 x \ dx

It's a very common integral in problems with trig substitution and otherwise.  The first thing to note is that 

.. math::

    \int \sin^2 x \ dx

is the same problem, because

.. math::

    \sin^2 x + \cos^2 x = 1

so 

.. math::

    \int \sin^2 x \ dx + \int \cos^2 x  \ dx = \int 1 \ dx = x

========
Method 0
========

I call this method 0 because it's not really methodical.  The approach is to guess.  If you play around differentiating products of functions (like :math:`e^x`, :math:`\ln x`, :math:`\sin x`, :math:`\cos x` and :math:`x`), you will discover that

.. math::

    \frac{d}{dx} \ [ \ \sin x \cos x \ ] \ = -\sin^2 x + \cos^2 x

    = \cos^2 x - 1 +  \cos^2 x

    = 2 \cos^2 x - 1

Integrating both sides, we obtain

.. math::

    \sin x \cos x = 2 \int \cos^2 x \ dx - x

and rearranging:

.. math::

    \int \cos^2 x \ dx = \frac{1}{2} (x + \sin x \cos x)

=============
Visualization
=============

There is a cool picture for this.  We have from above that (switching notation to the variable :math:`t`):

.. math::

    \int \cos^2 t \ dt = \frac{1}{2}(t + \sin t \cos t)

    = \frac{1}{2}(\sin^{-1}x + x \sqrt{1-x^2})
  
A simple diagram shows that these terms correspond to different parts of the area in question:

.. image:: /figs/area_int_trig.png
   :scale: 50 %
 
What is shown is a portion of the unit circle (the hypotenuse is :math:`1`), and we're interested in the area under the graph between the limits :math:`0 \rightarrow x`, for some value of :math:`x`.

The area is broken up into two parts.  The height of the graph at :math:`x` is :math:`\sqrt{1-x^2}` (since the hypotenuse is equal to :math:`1`), so the area of the gray triangle is

.. math::

    A = \frac{1}{2} x \ \sqrt{1-x^2}

The sine of the angle :math:`t` is :math:`x` (since the hypotenuse is equal to :math:`1`).  The angle :math:`t` is also the angle that sweeps out the sector of the circle as shown (because internal angles, etc.).  

But this is just the ratio of :math:`t` to :math:`2 \pi`, times the area of the (unit) circle

.. math::

    A = \frac{t}{2 \pi} \pi r^2 = \frac{1}{2} t = \frac{1}{2} \sin^{-1} x

So the total area is the sum of the two parts

.. math::

    A =  \frac{1}{2} ( \sin^{-1} x + x\  \sqrt{1-x^2})

    = \frac{1}{2} (t + \sin t \cos t)

========
Method 1
========

There are two other systematic approaches that can be contrasted.  The first, which is arguably the simpler one, is to remember the addition formula for cosine (:ref:`here <cosine_s+t>`)

.. math::

    \cos (s+t) = \cos s \cos t - \sin s \sin t

The trick I use to remember these formulas is to work out the consequences for this one:

.. math::

    \cos (s-t) = \cos s \cos t + \sin s \sin t

This makes perfect sense since if :math:`s=t` then we get

.. math::

    \cos 0 = \cos^2 s + \sin^2 s = 1

which we know is correct.  So

.. math::

    \cos (s+t) = \cos s \cos t - \sin s \sin t

If :math:`s=t` then (changing to :math:`x`)

.. math::

    \cos 2x = \cos^2 x  - \sin^2 x

and using the standard identity :math:`\cos^2 x + \sin^2 x = 1` this becomes

.. math::

    \cos 2x = 2\cos^2 x - 1

The "double angle" formula.

.. math::

    2 \cos^2 x = 1 + \cos 2 x

    \cos^2 x= \frac{1}{2} ( 1 + \cos 2x )

Integrating

.. math::

    \int \cos^2 x \ dx = \int \frac{1}{2} ( 1 + \cos 2x ) \ dx

    \frac{1}{2} ( x + \frac{1}{2} \sin 2x )

We check by differentiating.  Leaving the factor of :math:`1/2` out, we obtain for :math:`d/dx`:

.. math::

    1 + \cos 2x

which, as we saw above, is equal to :math:`2 \cos^2 x`.  Remembering the factor of :math:`1/2`, we obtain the expected result.

======================
Different but the same
======================

Comparing our results so far, we have obtained different answers, namely

.. math::

    \int \cos^2 x \ dx = \frac{1}{2} (x + \sin x \cos x)

    \int \cos^2 x \ dx = \frac{1}{2} ( x + \frac{1}{2} \sin 2x )

which indicates (if there is no mistake), that

.. math::

    \sin x \cos x = \frac{1}{2} \sin 2x

to see that this is correct, recall the addition formula for sine:

.. math::

    \sin (s+t) = \sin s \cos t + \sin t \cos s

then if :math:`s=t`

.. math::

    \sin 2s = 2 \sin s \cos s

with a slight rearrangement, this is indeed what we had.

========
Method 2
========

In the second "method", we do a substitution to take advantage of the integration by parts formula

.. math::

    \int u \ dv = uv - \int v \ du

Let :math:`u=\cos x`, then :math:`du = -\sin x \ dx`, and let :math:`dv = \cos x \ dx` then :math:`v= \sin x`, so

.. math::

    \int \cos^2 x \ dx = \sin x \cos x + \int \sin^2 x \ dx

This still seems like not much progress since (as we saw) :math:`\int \sin^2 x \ dx` is really the same problem as :math:`\int \cos^2 x \ dx`

.. math::

    \int \sin^2 x \ dx = \int (1 - \cos^2 x) dx = \int dx - \int \cos^2 x dx

but, forging ahead

.. math::

    \int \cos^2 x \ dx = \sin x \cos x + \int \sin^2 x \ dx

.. math::

    \int \cos^2 x \ dx = \sin x \cos x  + x -  \int \cos^2 x dx

Rearranging:

.. math::

    \int \cos^2 x \ dx  = \frac{1}{2} \ [ \ \sin x \cos x + x \ ] 

which is what we had before.

=========================
More about cosine squared
=========================

There are a few more things to be said about cosine squared.  First, recall the identity

.. math::

    \sin^2 x + \cos^2 x = 1

Integrate both sides

.. math::

    \int \sin^2 x \ dx + \int \cos^2 x \ dx  = \int 1 \ dx = x

Then consider what these graphs look like

.. image:: /figs/sin2cos2.png
       :scale: 25%

Over the interval :math:`x=0 \rightarrow \pi/2` (or a multiple thereof), the area under the two curves is equal because they are mirror images, reflected about :math:`\pi/4`.  

.. math::

    \int_0^{\pi/2} \sin^2 x \ dx = \int_0^{\pi/2} \cos^2 x \ dx

So, to obtain the area under a full lobe of the curve 

.. math::

    \int_0^{\pi} \sin^2 x \ dx + \int_0^{\pi} \cos^2 x \ dx  = \int_0^{\pi} 1 \ dx = \pi

    \int_0^{\pi} \sin^2 x \ dx = \int_0^{\pi} \cos^2 x \ dx = \frac{\pi}{2}

which may be easier to remember than

.. math::

    \int_0^{\pi} \cos^2x \ dx = \frac{1}{2} ( \sin x \ \cos x + x) \ \bigg |_0^{\pi} 

    = \frac{1}{2} ( 0 + \pi - 0 - 0 ) =  \frac{\pi}{2}
    
It's interesting to compare this result with the area under the simple curves :math:`\sin x` and :math:`\cos x`

.. math::

    \int_0^{\pi} \sin x \ dx = - \cos x  \ \bigg |_0^{\pi} = -(-1 - 1) = 2

The area under the sine or cosine is larger than the area under the square of either, because the values of sine and cosine are all less than one, so their squares are smaller than the values themselves.  The area under :math:`f(x)` from :math:`f(x) = 0 \rightarrow f(x)=1` is equal to :math:`1` for the sine or cosine, and to :math:`\pi/4` for the square.