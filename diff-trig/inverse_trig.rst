.. _inverse_trig:

###############################
Inverse trigonometric functions
###############################

============
Inverse sine
============

.. image:: /figs/trigints.png
   :scale: 50 %

Suppose we label a right-triangle with side :math:`x` (opposite the angle :math:`t`) and :math:`1` for the hypotenuse (left panel).  Then

.. math::

    \frac{x}{1} = \sin t

    t = \sin^{-1} x

:math:`t` is *the angle whose sine is x*.  Where can we go from this?  

Well, Pythagoras says that the adjacent side is :math:`\sqrt{1-x^2}`, which is also :math:`\cos t`.  What is the derivative of the inverse sine?  A trick is to start with the straightforward sine function:

.. math::

    x = \sin t

    \frac{dx}{dt} = \cos t

but

.. math::

    \cos t =  \sqrt{1-x^2}

Now, we want the derivative of the inverse sine, that is :math:`dt/dx`:

.. math::

    \frac{dt}{dx} = \frac{1}{\cos t} = \frac{1}{\sqrt{1-x^2}}

All this assumes that we limit the range of the inverse sine to the appropriate interval.  Here is a figure that plots the function (with :math:`y` as the angle) over the domain :math:`-1 \le x \le 1` and range:  :math:`-\pi / 2 \le y \le \pi/2`).

.. image:: /figs/arcsin.png
   :scale: 50 %

And above, we actually have to make a choice when we do :math:`\sqrt{1-x^2}`.  We take the positive square root, and if you look at the figure, this is correct.  The function increases continuously, :math:`f'(x)` is positive on this interval, except that it is not defined at the endpoints.

==============
Inverse cosine
==============

.. image:: /figs/arccos.png
   :scale: 50 %

As before, we limit the range of the inverse cosine to the appropriate interval (domain:  :math:`-1 \le x \le 1`), however, the  range is different:  :math:`0 \le y \le \pi`).  Also, if you look at the graph, the function is continuously decreasing over this interval (so we expect :math:`f'(x)` to be negative everywhere (except the endpoints, where it is not defined).

Now here is something curious:  if we plot them both together

.. image:: /figs/arcsincos.png
   :scale: 50 %

Can you believe that if we add the two functions together, the result is a constant?  Actually

.. math::

   \sin^{-1} x + \cos^{-1} x = \frac{\pi}{2}
   
We have known this for a long time.  This statement is the same as saying that the complementary angles of a right triangle add up to :math:`\pi/2`.

.. math::

    \sin^{-1} x + \cos^{-1} x = \frac{\pi}{2}

.. image:: /figs/sumarcsin.png
   :scale: 50 %

We'll call the angle :math:`\alpha` (originally :math:`y`).  We have 

.. math::

    \alpha = \sin^{-1} x

but 

.. math::

    \beta = \cos^{-1} x

and 

.. math::

    \alpha + \beta = \frac{\pi}{2}

Now, it's pretty easy to see how it works.

Differentiating:

.. math::

    \frac{d}{dx} \sin^{-1} x +  \frac{d}{dx} \cos^{-1} x = 0

The derivative of inverse cosine is just the same as the derivative of the inverse sine, multiplied by :math:`-1`!

.. math::

    y = \cos^{-1} x

    \frac{dy}{dx} = - \frac{1}{\sqrt{1-x^2}}

If you want to see an actual calculation:

.. math::

    y = \cos^{-1} x
    
    x = \cos y
    
    dx = -\sin y \ dy
    
    \frac{dy}{dx} = - \frac{1}{\sin y} = 

Now, of course :math:`x = \sin y` but that doesn't really help us here.  Instead do this:

.. math::

    \sin^2 y + \cos^2 y = 1
    
    x = \cos y
    
    \sin^2 y + x^2 = 1
    
    \sin y = \pm \sqrt{1-x^2}

so 

.. math::

    y = \cos^{-1} x
    
    \frac{dy}{dx} = - \frac{1}{\sin y} = \pm \frac{1}{\sqrt{1-x^2}}

but remember that :math:`f'(x) < 0` everywhere so

.. math::

    \frac{d}{dx} \cos^{-1} x = - \frac{1}{\sqrt{1-x^2}}

===============
Inverse tangent
===============

.. image:: /figs/arctan.png
   :scale: 50 %

Notice the domain and range, and that the slope is everywhere greater than :math:`0`, except at the extrema.

.. math::

    y = \tan^{-1} x

so 

.. math::

    x = \tan y
    
    dx = \sec^2 y \ dy

We want

.. math::

    \frac{dy}{dx} = \frac{1}{\sec^2 y}

since 

.. math::

    \sec^2 y = 1 + \tan^2 y
    
    \tan y = x
    
    \sec^2 y = 1 + x^2
    
    \frac{d}{dx} \ \tan^{-1} x = = \frac{1}{\sec^2 y} = \frac{1}{1 + x^2}

