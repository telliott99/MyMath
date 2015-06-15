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