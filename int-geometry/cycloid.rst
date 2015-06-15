.. _cycloid:

###########
The cycloid
###########

We imagine a bicycle with one tire marked at a particular point on the rim, say with fluorescent paint or a small light.  We start at time :math:`t = 0` with that point :math:`P` in contact with the :math:`x` axis at :math:`(0,0)`.  Then we start rolling the bike.  As the tire rotates our fixed point :math:`P` on the rim traces a curve

.. image:: /figs/cycloid.png
   :scale: 50 %

.. image:: /figs/cycloid2.png
  :scale: 50 %

We want to find parametric equations :math:`x(t)`, :math:`y(t)` that give the position of the point :math:`P` as a function of time.  The second diagram above shows the angle through which the wheel has turned as :math:`\theta`, but we will use :math:`t` for :math:`\theta` here.  The :math:`x` displacement of the vertical straight down from the center of the tire is just :math:`at`, where :math:`a` is the radius of the wheel, it is equal to the arc on the circumference of the wheel from the point which is currently in contact with the ground, up to :math:`P`.

It is fairly easy to derive the desired parametric equations, using vectors.  For :math:`x`, we have the vector that goes from :math:`(0,0)` to the contact point with the ground.  As indicated in the figure, that is :math:`at`.  We need to subtract the distance :math:`a \ sin\ t` from that.  It's easier to see for :math:`t < \pi/2`, but it is true always.  This is the usual circular motion, just with the circle flipped so the motion is clockwise, and we started at the bottom.

For :math:`y`, we have a constant factor of :math:`a` above the :math:`x` axis, then the additional displacement is :math:`-a \ cos \ t`.  So for :math:`t=0` we have the additional displacement is -a (we were on the ground), for :math:`t=\pi/2` it is zero, and for :math:`t=\pi` it is plus :math:`a` for a total of :math:`2a`.

The parametric equations are then

.. math::

    x(t) = at - a \ sin\ t \\

    y(t) = a - a \ cos\ t \\

Differentiate:

.. math::

    x'(t) = a - a \ cos\ t \\

    y'(t) = a \ sin\ t  \\


The derivation above did a little mental gymnastics with the circle, flipping it and setting :math:`t=0` when the point is at the bottom.  As an alternative, leave the circle in its usual orientation, with an angle :math:`s` to the positive :math:`x` axis.

It can be seen easily that :math:`s` and :math:`t` are related by the equation 

.. math::

    s = 3\pi/2 - t

The vector from the center of the circle to the point on the edge is just the standard one for a point on a circle of radius :math:`a`:

.. math::

    a \ \langle \cos s, \sin s  \rangle

For the :math:`x` component:

.. math::

    \cos s = \cos 3 \pi / 2 - t

    = \cos 3 \pi / 2  \cos t + \sin 3 \pi / 2 \sin t

Recall that :math:`\cos 3 \pi / 2 = 0` and :math:`\sin 3 \pi / 2 = -1` so

.. math::

    \cos s = - \sin t

And for the :math:`y` component

.. math::

    \sin s = \sin 3 \pi / 2 - t

    = \sin 3 \pi / 2 \cos t - \sin t \cos  3 \pi / 2

    = - \cos t

The vector is then

.. math::

    a \ \langle \cos s, \sin s  \rangle = a \ \langle -\sin t, -\cos t  \rangle

In addition, we have to add another vector, one extending from the origin to the center of the wheel.  The :math:`y` component is constant, it is just :math:`a`.  The :math:`x`-component is the distance the wheel has traveled from its initial position (the distance between the origin and the point of contact with the :math:`x`-axis, which is :math:`at`, shown as :math:`a \theta` in the figure).

Hence the vector to the point is:

.. math::

    a \ \langle -\sin t, -\cos t  \rangle + \langle at, a \rangle

    a \ \langle t - \sin t, 1 - \cos t \rangle

which matches what we had before.

==========
Arc length
==========

We wish to determine the arc length and area under the curve for a complete revolution of the wheel.

We want to use a slightly different version of the :ref:`usual formula <line-integrals>` for arc length

.. math::

    ds^2 = dx^2 + dy^2

    (\frac{ds}{dt})^2 = (\frac{dx}{dt})^2 + (\frac{dy}{dt})^2

    ds = \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2} \ dt 
    
    = \sqrt{(a - a \cos\ t)^2 + (a \sin\ t)^2} \ dt

This expands to

.. math::

    a \sqrt{1 - 2 \cos\ t + \cos^2t + \sin^2t } \ dt 
    
    =  a \sqrt{2 - 2 \cos \ t} \ dt

    =  \sqrt{2} a \ \sqrt{1 - \cos \ t} \ dt

The length is

.. math::

    L = \sqrt{2} a \ \int_0^{2\pi} \sqrt{1 - \cos \ t} \ dt

============
Double angle
============

.. math::

    \cos (s-t) = \cos s \cos t + \sin s \sin \ t

So

.. math::

    \cos (s+t) = \cos s \cos t - \sin s \sin \ t

Let :math:`s = t` and then, :math:`u = 2s`, so

.. math::

    \cos 2s = \cos u = \cos^2 \ (\frac{u}{2}) - \sin^2 \ (\frac{u}{2})
    
    \cos u = 1 - \sin^2 \ (\frac{u}{2}) - \sin^2 \ (\frac{u}{2})

    2 \sin^2 \ (\frac{u}{2}) = 1 - \cos u

:math:`u` is just a dummy variable, so we can switch back to :math:`t`

.. math::

    2 \sin^2 \ (\frac{t}{2}) = 1 - \cos t

We have that 

.. math::

    L = a \sqrt{2} \ \int_0^{2\pi} \sqrt{1 - \cos \ t} \ dt

    \sqrt{1 - \cos t} = \sqrt{2} \sin(\frac{t}{2})

So

.. math::

    L = a \sqrt{2} \ \int_0^{2\pi} \sqrt{2} \sin \ (\frac{t}{2}) \ dt

    2a  \ \int_0^{2\pi} \sin \ (\frac{t}{2}) \ dt

    = 2a \ (-2) \cos \ (\frac{t}{2})\ \bigg |_0^{2\pi}

    = -4a \ (\cos \ \pi - \cos \ 0)

    = -4a \ (-1 - 1) = 8a

A very simple answer to the problem.

==================
Area under the arc
==================

We want

.. math::

    A = \int_{t=0}^{t=2\pi} y \ dx

    = \int_{t=0}^{t=2\pi} (a - a \cos\ t) (a - a \cos\ t) \ dt

    a^2\int_{t=0}^{t=2\pi} (1 - \cos\ t)^2 \ dt

    a^2\int_{t=0}^{t=2\pi} (1 - 2 \cos\ t + \cos^2\ t) \ dt

If you don't remember the result for :math:`\int \cos^2 t \ dt`, you can go back to the double angle formula above and convert from :math:`\sin^2` to :math:`\cos^2`.  Otherwise write:

.. math::

    A = a^2 ( t - 2 \sin \ t + \frac{1}{2}t + \frac{1}{4} \sin 2t ) \ \bigg|_0^{2\pi}

    a^2 ( 2\pi - 0 + \pi + 0 - 0 + 0 - 0 - 0    ) = 3\pi a^2

Also a very simple answer.