.. _intro:

############
Introduction
############

The essential ideas of calculus are surprisingly simple. See if you don't agree.

We can talk about the slope of a curve at a single point. This seems odd because "slope" refers to a change in y divided by a change in x. We ought to need two points, not just one. But we don't.

A single point can have a slope for the same reason that the earth seems to be flat where I'm standing right now even though I know it is curved---it is flat, on the ocean or the Mohave desert anyway. The carpenters who built your house assumed that the earth's curvature is negligible, and we will too. We can mentally zoom in indefinitely (ask an ant if the earth is flat). 

.. image:: /figs/earth.png
   :scale: 50 %

So for any given point on a curve, we can always find another point very close nearby which has the same slope, and then we know the slope between them is constant (within any limits you want to establish).

A car's odometer and speedometer perform related functions :), and these functions are a good way to think about the fundamental operations of calculus. Suppose a car is going in a straight line (say, on the Bonneville salt flats). We need to deal only with the positive x-axis. 

Distance (often labeled :math:`s`) is a function of time:

.. math::

    s = f(t)

If the velocity is constant and we start from :math:`s = 0` then:

.. math::

    s = v * t

Distance equals velocity times time. (:math:`60` miles per hour for :math:`2` hours = :math:`120` miles).

Now, velocity might be changing, it might be a function of time. Let's say we'll figure out how it changes later, and just write in a general way:

.. math::

    v = f(t)

If the velocity is changing, we call the rate of change in velocity the acceleration. (It is the slope of the curve for :math:`v` as a function of :math:`t`). If the acceleration is constant (like gravity), then:

.. math::

    v = a * t

For a car, imagine increasing the pressure on the gas pedal steadily so that after :math:`1` second you are going :math:`10` mph, after :math:`2` seconds :math:`20` mph, after :math:`3` seconds :math:`30` mph. If we continue at the same rate, we'll accelerate from :math:`0` to :math:`60` mph in :math:`6` seconds.

.. image:: /figs/ferrari.png
   :scale: 50 %

As I said before, there is a special trick symbolized with a prime mark placed next to the s (the physicists put a dot on top). The trick is called differentiation:

.. math::

    s' = ... \text{something}

What it is depends on the exact form of :math:`s` as a function of time. If the acceleration is constant:

.. math::

    s = 1/2 a t^2

The rule we had above was:

.. math::

    y  = c x^n

    y' = n c x^{n-1}

Or, using the time and distance symbols:

.. math::

    s  = 1/2 a t^2

    s' = v = a t

    s'' = a

So that is where the factor of :math:`1/2` comes from in the equation involving acceleration. It is needed to cancel the the :math:`2` that comes out of the exponent when we differentiate. One way to think about this is to say that the velocity after a period of constant acceleration is the average of the initial acceleration and the final acceleration, times the time. But this differentiation mumbo jumbo will work even if the velocity and acceleration are more complicated functions of time.

Before we go any further with calculus, I want to review a few topics from pre-calculus and trigonometry that will come in handy.  As Professor Shankar says:

    You have to know your trigonometry, to know what’s a sine and what’s a cosine and some simple identities. You cannot say, “I will look it up.” Your birthday and social security number are things you look up; trigonometric functions and identities are what you know all the time.
    
http://www.amazon.com/Fundamentals-Physics-Mechanics-Relativity-Thermodynamics/dp/0300192207

