.. _ucm:

#######################
Uniform circular motion
#######################

Here we want to discuss some ideas related to the orbits of planets.  The first approach is to think about uniform circular motion.  In this analysis we will idealize the orbits of the planets as circles.

The :ref:`eccentricity <ellipse>` of an ellipse is

.. math::

    e = \frac{f}{a}
    
    ea = f

Eccentricity is the fraction of the major axis that we go out from the origin to the foci of the ellipse.

and since :math:`f = \sqrt{a^2 - b^2}` is the distance from the center to either focus:

.. math::

    e = \sqrt{1 - (\frac{b^2}{a^2})}
    
    e^2 = 1 - \frac{b^2}{a^2}
    
    f^2 = a^2 - b^2

(For more on this see :ref:`here <ellipse>`).

Also, according to wikipedia, the eccentricity of orbit of the planets known to Kepler plus the moon are

.. math::

- Mercury:  0.024

- Venus:  0.007

- Earth:  0.017

- Mars:  0.093

- Jupiter:  0.048

- Saturn:  0.054

- Moon:  0.055


So looking at Earth, for example, its mean distance from the sun is 150 million kilometers, so approximating :math:`a` as that value, :math:`f=ea` is about 2.5 in the same units.  The radius of the sun is about 0.7 in those units.

(Need to re-check this calculation because it disagrees with result based on center of mass).

===============
Basic equations
===============

For the basic setup in polar coordinates, we write

.. math::

    x = R \cos \theta 

    y = R \sin \theta 

(I'm going to use :math:`R` for the radius since we will also have :math:`\mathbf{r}(t)`, the position vector).

We are talking about objects that change position with time, so we need to introduce time here somehow.  We will say that

.. math::

    \theta = \omega t 

Our clock ticks, and :math:`\omega` (in units of radians per second) tells how :math:`\theta` is calibrated with respect to the clock.

So now we can write the components of

.. math::

    \mathbf{r}(t) = \langle \ x(t), y(t) \ \rangle 

    \mathbf{r}(t) = R \langle \cos \theta, \sin \theta \rangle 

    \mathbf{r}(t) = R \langle \cos \omega t, \sin \omega t \rangle 

And then we just differentiate to find the velocity and acceleration

.. math::

    \mathbf{v}(t) = \omega R \langle -\sin \omega t, \cos \omega t \rangle 

    \mathbf{a}(t) = -\omega^2 R \langle \cos \omega t, \sin \omega t \rangle 

    \mathbf{a}(t) = -\omega^2 R \mathbf{r}(t) 

Notice that :math:`\mathbf{v}(t)` is orthogonal (perpendicular) to :math:`\mathbf{r}(t)`

.. image:: /figs/strang_ucm.png
   :scale: 50 %

.. math::

    \mathbf{v}(t) \cdot \mathbf{r}(t) = \omega R \langle -\sin \omega t, \cos \omega t \rangle \cdot R \langle \cos \omega t, \sin \omega t \rangle
    
    = 0 

and the acceleration is on exactly the same line as :math:`\mathbf{r}` but points inward, toward the sun or origin of the system.

.. math::

    \mathbf{a}(t) = -\omega^2 R \mathbf{r}(t) 

If we adjusted our clock to have the appropriate units of time, we wouldn't need :math:`\omega`, but it gives the magnitude of the velocity.

.. math::

    v = |\mathbf{v}| = \sqrt{\mathbf{v}(t) \cdot \mathbf{v}(t)}
    
    = \sqrt{\omega R \langle -\sin \omega t, \cos \omega t \rangle \cdot \omega R \langle -\sin \omega t, \cos \omega t \rangle}
    
    = \omega R  

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

:math:`G = 6.67384 \times 10^{-11} \ \text{m}^3 \ \text{kg}^{-1} \ \text{s}^{-2}`

:math:`R = 6.371 \times 10^{6} \ \text{m}`

:math:`M = 5.97219 \times 10^24 \ \text{kg}`

so :math:`GM/R \approx 6.26 \times 10^7` and :math:`v \approx 7910` m/s.  If we increase :math:`R` to a height of :math:`150` km above the surface of the earth we would have :math:`v \approx 7815` m/s.

Also, we can compare these numbers with the velocity of rotation at the earth's surface.  Roughly speaking, the circumference of the earth is :math:`25,000` miles (:math:`24,908` miles, :math:`40,075` km) and it rotates in :math:`24` hr, so the speed is about :math:`1037` mph.  That is about :math:`463 \ \text{m/s}^2`.

Of course, the velocity depends on latitude.  One must multiply by the cosine of the latitude.

In addition we need to add the potential energy to get to a particular orbit.   We have

.. math::

    V = - GM/R 

    \Delta V = -GM(\frac{1}{R_2} - \frac{1}{R_1}) = GM(\frac{1}{R_1} - \frac{1}{R_2})

We can use these to look at some other orbits.

Geostationary orbit  42,000 km

Moon orbit avg = 385,000 km

A geostationary orbit is "out there", about 3.4 earth diameters and 10% of the way to the moon.  The variation in satellite orbits is pretty extreme.

======
Energy
======

The force due to gravity is

.. math::

    \mathbf{F} = -\frac{GmM}{R^2} \hat{\mathbf{r}} 

The potential is a function, which when we take

.. math::

    - \frac{d}{dr} U = \mathbf{F} 

    U = - \frac{GmM}{R} + C 

Define

.. math::

    U_{\infty} = 0 \rightarrow C = 0 

The total energy is

.. math::

    E = K + U = \frac{1}{2}mv^2 - \frac{GmM}{R} 

if we want an object to just reach :math:`r=\infty` with zero energy, then

.. math::

    0 = \frac{1}{2}mv^2 - \frac{GmM}{R} 

    v^2 = \frac{2GM}{R} 

This is the escape velocity.

If the force is as given above, the magnitude of the acceleration is

.. math::

    a = \frac{GM}{R^2} 

but for uniform circular motion we had

.. math::

    a = \frac{v^2}{R} = \frac{GM}{R^2} 

    v^2 = \frac{GM}{R} 

This is the orbital velocity.

Finally, we know that the velocity is distance divided by time, so for one full revolution it is

.. math::

    v = \frac{2\pi R}{T} 

but

.. math::

    v^2 = \frac{GM}{R} = (\frac{2\pi R}{T})^2 

Rearranging

.. math::

    T^2 = \frac{(2\pi)^2}{GM} R^3 

This is Kepler's Third Law.  The derivation is easy if we assume the orbits are circles, which is pretty close to being true.  It is also true for an elliptical orbit.  That is a bit harder calculation, which I have written up elsewhere.
