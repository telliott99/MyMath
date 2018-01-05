.. _trig_sub:

##################
Trig Substitutions
##################

By now we've had plenty of experience with the trigonometric functions sine and cosine, and the others constructed from them like tangent and secant.  For example

.. math::

    y = \sin \ \frac{\pi}{4} = \frac{1}{\sqrt{2}}

Here, we will consider the *inverse* trigonometric functions.  We use as our independent variable the value of the sine, and we ask which angle :math:`\theta` has that value for its sine (we can also use :math:`y` as the label for this variable, of course).  The function that yields the angle given the sine is called the inverse sine (:math:`\sin^{-1}` or :math:`arc \sin` or simply :math:`asin`).

.. math::

    y = \sin^{-1} (x)

or 

.. math::

    \theta = \sin^{-1} (\frac{1}{\sqrt{2}})

    \theta = \frac{\pi}{4}

Here is the figure from the wikipedia article on this topic showing the inverse sine and cosine.  (Recall that a function can assign only *one* value of :math:`y` to each value of :math:`x`.  Hence, the limits on the domain of the inverse sine function are :math:`x = -1 \rightarrow 1`, and similarly for the inverse cosine.

.. image:: /figs/arcsin.png
       :scale: 25%

If we imagine the mirror image of the sine function rotated by 90 degrees (that is, both flipped and rotated), we obtain the inverse sine.  In the figure below, both hands are left hands, so in the left panel we are looking at the back of the hand, and in the right panel we are looking at the front or palm.

.. image:: /figs/hands.png
       :scale: 25%

These two views have the same relationship as the sine and inverse sine (in fact, any function and its inverse have this property).

Below, both the sine and inverse sine are plotted.  They are symmetrical across the line :math:`y=x`.

.. image:: /figs/arcsin2.png
       :scale: 25%

The inverse trig functions might be no more than a curiosity, except that they provide solutions to some integrals.

Consider the figure below.  

.. image:: /figs/trig1.png
       :scale: 25%

.. math::

    x = \sin \ \theta

    dx = \cos \theta \ d \theta

    \sqrt{1-x^2} = \cos \ \theta

So if we have an integral like

.. math::

    \int \frac{x}{\sqrt{1-x^2} } \ dx

substituting

.. math::

    \int \frac{1}{\cos \theta} \ \sin\theta \ \cos\theta \ d\theta = \int  \sin\theta \ d \theta = -\cos \theta = -\sqrt{1-x^2}

Now, admittedly, we could also have done the integral by seeing that in the numerator we have the derivative of the :math:`x^2` squared term in the denominator, or by a more familiar type of substitution:

.. math::

    u = 1-x^2
    
    du = -2x \ dx

    \int -\frac{1}{2} \  \frac{1}{\sqrt{u} } \ du = - \sqrt{u} = \ - \sqrt{1-x^2}
    
But this is the basic idea of "trig substitutions".

The real advantage is that these substitutions allow us to integrate even when we don't have the derivative of what is under the square root sign.  Consider these two integrals

.. math::

    \int \sqrt{1-x^2} \ dx
    
    \int \frac{1}{\sqrt{1-x^2}} \ dx
    
with the substitution from before

.. math::

    x = \sin \theta

    dx = \cos \theta \ d\theta

    \sqrt{1-x^2} = \cos \theta
    
The second one is just

.. math::

    \int \frac{1}{\sqrt{1-x^2}} \ dx = \int \frac{1}{\cos \theta} \ \cos \theta \ d \theta = \theta  = \sin^{-1}x
    
while the first is the familiar

.. math::

    \int \sqrt{1-x^2} \ dx = \int \cos^2 \theta \ d \theta

    = \frac{1}{2} \ [ \sin \theta \ \cos \theta + \theta ]

    = \frac{1}{2} \ [x \ \sqrt{1-x^2}  + \sin^{-1} x ]
    
which only becomes a little tricky in substituting back to x.

If we substitute a for 1 as the hypotenuse in the diagram, then we have

.. math::

    x = a \sin\theta
    
    dx = a \cos\theta \ d\theta
    
    \sqrt{(a^2-x^2)} = a \cos\theta

and so

.. math::

    \int \frac{1}{\sqrt{a^2-x^2}} \ dx
    
    = \int \frac{1}{a \cos \theta} \ a \cos \theta \ d \theta
    
    = \theta \ = \sin^{-1} (\frac{x}{a})
    
A definite integral requires consideration of the limits of integration.  For example, suppose the above example is

.. math::

    x=0 \rightarrow x=a, \ \ \  a = 4
    
What happens to :math:`\theta`?

.. math::

    \theta = \sin^{-1} \frac{x}{a}
    
when :math:`x=0`, :math:`\theta = 0`.  When :math:`x = 4`, :math:`x/a = 1` and :math:`\theta = \pi/2`.

All the integrals above involve :math:`\sqrt{a^2-x^2}` or :math:`\sqrt{1-x^2}`.  For any of these, if we can work an example with :math:`a=1`, we can work it for any constant :math:`a`.

===========
Other types
===========

Two other classes are those with :math:`\sqrt{x^2 + a^2}` and :math:`\sqrt{x^2-a^2}`.  

For the first type we should put :math:`x` as the side opposite :math:`\theta`, :math:`a` as the side adjacent, and :math:`\sqrt{x^2 + a^2}` as the hypotenuse.

.. image:: /figs/trigints.png
       :scale: 25%

.. math::

    x = a\ \tan \ \theta
    
    dx = a \ \sec^2 \theta \ d \theta
    
    \theta = \tan^{-1} (\frac{x}{a})
    
    \int \frac{1}{x^2 + a^2} \ dx = \int \frac{1}{a^2 \ \tan^2 \theta + a^2} \ a \ \sec^2 \theta \ d \theta
    
Notice that :math:`\sec^2 = 1 + \tan^2 \theta` so

.. math::

    = \frac{1}{a} \ \int d \theta = \frac{1}{a} \ \theta = \frac{1}{a} \tan^{-1}(\frac{x}{a})

============
Last example
============

.. math::

    \int \sqrt{x^2-a^2} \ dx

In this case, we will have :math:`x` as the hypotenuse, :math:`a` as the side adjacent to :math:`\theta`, and :math:`\sqrt{x^2 - a^2}` as the side opposite.

We have 

.. math::

    \frac{1}{a} \sqrt{x^2-a^2} = \tan \theta

    \sqrt{x^2-a^2} = a \tan \theta
    
    \frac{1}{a} x = \sec \theta

    dx = a \sec \theta \tan \theta \ d \theta

So we have

.. math::

    \int \sqrt{x^2-a^2} \ dx

    = a^2 \int \sec \theta \tan^2 \theta \ d \theta

using the familiar identity :math:`1 + \tan^2 \theta = \sec^2 \theta`:

.. math::

    = a^2 \int \sec \theta \ (\sec^2 \theta - 1) \ d \theta

    = a^2 \int (\sec^3 \theta - \sec \theta) \  d\theta

which is a bit tricky.  If you look it up in a table of integrals, the individual answers are

.. math::

    \int \sec \ x \ dx = \ln | \sec x + \tan x|

    \int \sec^3 x \ dx = \frac{1}{2}(\sec x \ \tan x + \ln | \sec x + \tan x|)



======================
Doing the cubed secant
======================

.. math::

    \int  \sec^3 x \ dx

This one is very similar to :ref:`cosine squared <cosine_sq>`.  We use integration by parts to obtain an expression that has the negative of secant-cubed on the right-hand side.

Start by recalling that :math:`\sec^2 x = 1 + \tan^2 x`, so

.. math::

    \int  \sec^3 x \ dx
    
    = \int \sec x \ (1 + \tan^2 x) \ dx
    
    = \int \sec x \ dx + \int \sec x \tan^2 x \ dx

To do the right-hand expression, we use integration by parts

.. math::

    u = \tan x
    
    du = \sec^2 x \ dx
    
    dv = \sec x \tan x \ dx
    
    v = \sec x
    
So what we have above (in the second term on the right) is :math:`\int u \ dv` and we get:

.. math::

    = uv - \int v \ du

    = \sec x \tan x - \int \sec^3 x \ dx

Seems like we are back where we started, except .. 

Let's write out the whole thing:

.. math::

    \int  \sec^3 x \ dx = \int \sec x \ dx + \int \sec x \tan^2 x \ dx

    \int  \sec^3 x \ dx = \ln |\sec x + \tan x| + \sec x \tan x - \int \sec^3 x \ dx
    
So

.. math::

    2 \int  \sec^3 x \ dx = \ln |\sec x + \tan x| + \sec x \tan x
    
    \int  \sec^3 x \ dx = \frac{1}{2} \ [ \ \ln |\sec x + \tan x| + \sec x \tan x  \ ]

We developed a similar argument with :math:`\int \cos^2 x \ dx`, if you remember.

To check it (save the :math:`1/2` for later):

.. math::

    \frac{d}{dx} \ \ln |\sec x + \tan x| + \sec x \tan x

    = \frac{1}{\sec x + \tan x} (\sec x \ \tan x + \sec^2 x) + \sec^3 x + \sec x \tan^2 x

    = \sec x + \sec^3 x + \sec x \tan^2 x

    = \sec x + \sec^3 x + \sec x (\sec^2 x - 1)

    = 2 \sec^3 x

The extra factor of :math:`1/2` makes it exactly correct.

=====================
Completing the square
=====================

Here's another one that looks weird at first:

.. math::

    \int \sqrt{x^2 + 6x} \ dx

Try completing the square

.. math::

    = \int \sqrt{x^2 + 6x + 9 - 9} \ dx

    = \int \sqrt{(x + 3)^2 - 3^2} \ dx

Now substitute

.. math::

    \frac{x+3}{3} = \sec t

:math:`x+3` is the hypotenuse, :math:`3` the side adjacent to angle :math:`t`, and :math:`\sqrt{(x + 3)^2 - 3^2}` is the side opposite.  So

.. math::

    \sqrt{(x + 3)^2 - 3^2} = 3 \tan t

and for :math:`dx`:

.. math::

    \frac{x+3}{3} = \sec t

    \frac{1}{3} \ dx = \sec t \tan t \ dt

So our integral is 

.. math::

    = \int 3 \tan t \ 3 \sec t \tan t \ dt

Recall that :math:`\tan^2 t + 1 = \sec^2 t`

.. math::

    = 9 \int \sec^3 t - \sec t \ dt

We had a trick for `\sec t` which gives 

.. math::

    \int \sec t \ dt = \ln | \sec t + \tan t | + C

(easily checked by differentiating).  The other term is solved by integration by parts.  I'll just give a sketch here:

.. math::

    \int sec^3 t \ dt = \sec t \tan t - \int \sec^3 t \ dt + \int \sec t \ dt

    \int sec^3 t \ dt = \frac{1}{2} \ [ \ \sec t \tan t + \int \sec t \ dt \ ]

combined with what was above, we end up subtracting (one-half) :math:`\int \sec t \ dt`

.. math::

    = (9) \  \frac{1}{2} \ [ \ \sec t \tan t - \ln | \sec t + \tan t | \ ]  + C

I'll leave it to you to substitute back for :math:`x`.
