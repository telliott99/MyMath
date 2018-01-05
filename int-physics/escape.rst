.. _escape:

###############
Escape velocity
###############

Escape velocity is the velocity required to escape from the earth's gravitational field (or from some other astronomical object like the moon).  We can also think in terms of the requisite kinetic energy :math:`mv^2/2`.

We calculate the energy required, and therefore the minimal velocity required, by finding the work that must be done in moving from the earth's surface to a point infinitely far away.  

Work is *force times distance*.  

The force is the gravitational force:

.. math::

    F = \frac{GmM}{r^2}

The work over a short distance is

.. math::

    dW = \frac{GmM}{r^2} \ dr
    
The total work is the integral:

.. math::

    W = \int_R^{\infty} \frac{GmM}{r^2} \ dr

    = GmM \int_R^{\infty} \frac{1}{r^2} \ dr
    
    = -GmM \ \ \frac{1}{r} \ \bigg |_R^{\infty}

An :ref:`improper integral <improper-int>`.  At the upper limit (:math:`r=\infty`) we obtain :math:`0`, so we have just:

.. math::

    W = - (-\frac{GmM}{R})
    
    = \frac{GmM}{R}
    
This is also the additional potential energy acquired by moving far away.  We need at least this much energy, contributed by the escape velocity:

.. math::

    \frac{1}{2} mv^2 = \frac{GmM}{R}

    v^2 = \frac{2GM}{R}
    
    v = \sqrt{\frac{2GM}{R}}

https://en.wikipedia.org/wiki/Escape_velocity

Since

.. math::

    G = 6.67 \times 10^{-11} \ m^3 kg^{-1} s^{-2}
    
    M = 5.972 \times 10^{24} \ kg
    
    R = 6371 \ km = 6.371 \times 10^6 \ m
    
I calculate:

.. math::

    v^2 = \frac{2 \times 6.67 \times 5.972}{6.371} \times 10^7 \ (m/s)^2
    
    = 12.504 \times 10^7 \ (m/s)^2

So

.. math::

    v \approx 11,200 \ m/s

The velocity is independent of the mass.

================
Orbital velocity
================

Suppose we wish to launch a satellite into stable orbit around the earth.  The orbital speed required is

.. math::

    v_o = \sqrt{\frac{GM}{R}}

The kinetic energy is:

.. math::

    T = \frac{GmM}{2R}

Recall that the escape velocity is

.. math::

    v_e = \sqrt{\frac{2GM}{R}}

Therefore, starting from a particular orbit, the ratio 

.. math::

    \frac{v_0}{v_e} = \frac{1}{\sqrt{2}}

==========
Derivation
==========

Consider a body (like a satellite) orbiting a much larger body (like the earth).  Assume the orbit is circular.  This is uniform circular motion.

In polar coordinates, we write

.. math::

    x = R \cos \theta

    y = R \sin \theta

(I'm going to use :math:`R` for the radius since we will also have :math:`\mathbf{r}(t)`, the position vector).

We are talking about objects that change position with time, so we need to introduce time here somehow.  We will say that 

.. math::

    \theta = \omega t

Our clock ticks, and :math:`\omega` (in units of radians per second) tells how :math:`\theta` is calibrated with respect to the clock.

So now we can write the components of the position vector as

.. math::

    \mathbf{r}(t) = \langle \ x(t), y(t) \ \rangle

    = R \langle \cos \theta, \sin \theta \rangle

    = R \langle \cos \omega t, \sin \omega t \rangle

And then we just differentiate to find the velocity and acceleration

.. math::

    \mathbf{v}(t) = \omega R \langle -\sin \omega t, \cos \omega t \rangle

and

.. math::

    \mathbf{a}(t) = -\omega^2 R \langle \cos \omega t, \sin \omega t \rangle

    \mathbf{a}(t) = -\omega^2 R \mathbf{r}(t)

Notice that :math:`\mathbf{v}(t)` is orthogonal---perpendicular---to :math:`\mathbf{r}(t)` (the dot product is zero)

.. image:: /figs/strang_ucm.png
   :scale: 50 %

.. math::

    \mathbf{v}(t) \cdot \mathbf{r}(t) = 0

and the acceleration is on exactly the same line as :math:`\mathbf{r}` but points inward, toward the earth or sun or origin of the system.

.. math::

    \mathbf{a}(t) = -\omega^2 R \mathbf{r}(t)

Perhaps if we adjusted our clock to have the appropriate units of time, we wouldn't need :math:`\omega`, but it gives the magnitude of the velocity.

.. math::

    v = |\mathbf{v}| = \omega R

    a = |\mathbf{a}| = \omega^2 R

so

.. math::

    a =  \omega^2 R = (\frac{v}{R})^2 R = \frac{v^2}{R}

We can apply the formula to find the orbital velocity for an object going around the earth.  The acceleration is due to gravity so

.. math::

    \mathbf{F} = m \mathbf{a}

Its magnitude is 

.. math::

    a = \frac{GM}{R^2} = \frac{v^2}{R}

So

.. math::

    v = \sqrt{\frac{GM}{R}}

For the earth

.. math::

    \begin{array}{lcr}
    \mbox{G =} & 6.67384 \times 10^{-11} \ \text{m}^3 \ \text{kg}^{-1} \ \text{s}^{-2}  \\
    \mbox{R =} & 6.371 \times 10^{6} \ \text{m}  \\
    \mbox{M =} & 5.97219 \times 10^24 \ \text{kg}  \\
    \end{array}

so :math:`GM/R \approx 6.26 \times 10^7` and :math:`v \approx 7910` m/s.  If we increase :math:`R` to an height of :math:`150` km above the surface of the earth we would have :math:`v \approx 7815` m/s.  

Also, we can compare these numbers with the velocity of rotation at the earth's surface.  Roughly speaking, the circumference of the earth is :math:`25,000` miles (:math:`24,908` miles, :math:`40,075` km) and it rotates in :math:`24` hr, so the speed is about :math:`1037` mph.  That is about :math:`463` m/s :math:`^2`.  

In addition we need to add the potential energy to get to a particular orbit.   We have

.. math::

    V = - GM/R

    \Delta V = -GM(\frac{1}{R_2} - \frac{1}{R_1}) = GM(\frac{1}{R_1} - \frac{1}{R_2})

We can use these to look at some other orbits.

Geostationary orbit  :math:`42,000` km

Moon orbit avg :math:`= 385,000` km

The variation in satellite orbits is pretty extreme.

======
Kepler
======

(This is partially a repeat of what's above).

The force due to gravity is

.. math::

    \mathbf{F} = -\frac{GmM}{r^2} \hat{\mathbf{r}}

The potential is a function, which when we take

.. math::

    - \frac{d}{dr} U = \mathbf{F}

    U = - \frac{GmM}{r} + C

Define

.. math::

    U_{\infty} = 0 \rightarrow C = 0

The total energy is

.. math::

    E = K + U = \frac{1}{2}mv^2 - \frac{GmM}{r}

if we want an object to just reach :math:`r=\infty` with zero energy, then

.. math::

    0 = \frac{1}{2}mv^2 - \frac{GmM}{r}

    v^2 = \frac{2GM}{r}

This is the escape velocity.

If the force is as given above, the magnitude of the acceleration is 

.. math::

    a = \frac{GM}{r^2}

but for uniform circular motion we had

.. math::

    a = \frac{v^2}{r} = \frac{GM}{r^2}

    v^2 = \frac{GM}{r}

This is the orbital velocity.

Finally, we know that the velocity is distance divided by time, so for one full revolution it is

.. math::

    v = \frac{2\pi r}{T}

but

.. math::

    v^2 = \frac{GM}{r} = (\frac{2\pi r}{T})^2

Rearranging

.. math::

    T^2 = \frac{(2\pi)^2}{GM} r^3

This is Kepler's Third Law.  The derivation is easy if we assume the orbits are circles, which is pretty close to being true.  It is also true for an elliptical orbit.  That is a bit harder calculation, which I have written up elsewhere.