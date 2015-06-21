.. _harmonic-oscillator:

###################
Harmonic oscillator
###################

I want to work through the classical equations for oscillation, using as one of my sources the set of lectures by Prof. Shankar.

http://oyc.yale.edu/physics/phys-200

The simplest example is called the mass and spring system.

.. image:: /figs/spring1.png
   :scale: 50 %

In the picture, the left panel is the equilibrium position, while the right view is the mass displaced to the right by some distance :math:`x`.  We pulled it there and have just released it.  The force due to the spring is :math:`F = -kx`.  Not shown is the picture when the mass goes to the left of the equilibrium position and compresses the spring.  To begin with, we will use a frictionless table.  Without friction, the mass will oscillate back and forth forever.

We don't need vectors for this since we are working in one dimension.  By experiment, we find that the force is proportional to the displacement and directed toward the equilibrium position.  Newton's Law says that :math:`F=ma` so

.. math::

    F = ma = m \ddot{x} = - kx

    \ddot{x} + \frac{k}{m} x = 0

(We use the dot and double-dot notation of physics:  :math:`\dot{x}` and :math:`\ddot{x}` are the first and second derivatives of :math:`x` with respect to time).

This equation is easy to solve.  We need something whose second derivative is minus itself, within some constant.  A good choice is

.. math::

    x(t) = A \cos \omega t

(We don't choose :math:`\sin t` because we want :math:`x(t) \ne 0`).

.. math::

    \ddot{x}(t) = - \omega^2 A \cos \omega t

so that

.. math::

    [ \ - \omega^2 + \frac{k}{m} \ ] \ A \cos \omega t = 0

:math:`A` corresponds to :math:`x(0)`, which we want to be non-zero.  This equation is zero (for all :math:`t`) only when 

.. math::

    \frac{k}{m} = \omega^2

    \omega = \sqrt{k/m}

Observe that :math:`A` can be anything we want.  It corresponds to the maximum amplitude of the oscillation, determined by how far we pull out the mass to start things off.

In contrast, :math:`\omega` is determined by the characteristics of the spring, and is inversely proportional to the mass.  :math:`\omega` is also related to the frequency of oscillation.  If :math:`T` is the time period for one complete oscillation, then :math:`\omega T = 2 \pi`, or if :math:`f` is the frequency of oscillation, then :math:`\omega = 2 \pi f`.

Finally, this solution assumes that :math:`v_0 = 0`.

.. math::

    \dot{x}(t) = - \omega A \sin \omega t

    \dot{x}(0) = - \omega A \sin \omega (0) = 0

That is more restrictive than necessary.  We can deal with this in various ways, one is to add a term containing the sine to :math:`x(t)`.

.. math::

    x(t) =  A \cos \omega t + B \sin \omega t

    \dot{x}(t) =  - \omega A \sin \omega t + B \cos \omega t

    \dot{x}(0) = B = v_0

Another way is to add a phase term to the angle, which doesn't change the derivatives

.. math::

    x(t) =  A \cos \omega t + \phi

    \dot{x}(t) = - \omega A \sin \omega t + \phi

    \dot{x}(0) = v_0 = - \omega A \sin \phi

It is interesting to see why these amount to the same thing.  Recall

.. math::

    \cos \omega t + \phi = \cos \omega t \cos \phi - \sin \omega t \sin \phi

But :math:`\phi` is a constant so if :math:`-B = \sin \phi` and :math:`A = \cos \phi`

.. math::

    \cos \omega t + \phi = A \cos \omega t + B \sin \omega t

However, for now we will agree to set our clock to zero when the mass has just been released and has zero velocity, at the maximum amplitude of the oscillation.

======================
Conservation of Energy
======================

Here, Prof. Shankar does this calculation

.. math::

    x(t) = A \cos \omega t

    v = \dot{x} = - \omega A \sin \omega t

    E = \frac{1}{2}mv^2 + \frac{1}{2} kx^2

    = \frac{1}{2}m \omega^2 A^2 \sin^2 \omega t + \frac{1}{2} k A^2 \cos^2 \omega t

But :math:`\omega^2 = k/m` so

.. math::

    = \frac{1}{2}k A^2 \sin^2 \omega t + \frac{1}{2} k A^2 \cos^2 \omega t

    E = \frac{1}{2}k A^2

Not only is this independent of time, but we can write

.. math::

    \frac{1}{2}k A^2 = \frac{1}{2}mv^2 + \frac{1}{2} kx^2

Given :math:`A` and :math:`x`, we can find :math:`v`, and so on.

========
Pendulum
========

A useful extension is to the problem of the pendulum.

.. image:: /figs/pendulum1.png
   :scale: 50 %

The *torque* on the mass is the component of the gravitational force perpendicular to the rod, which is :math:`-mg \sin \theta` (this vector is drawn a bit too long in the figure).

.. math::

    \tau = -mgL \sin \theta = I \ddot{\theta}

We apply the small angle approximation and obtain

.. math::

    \tau = -mgL \theta = I \ddot{\theta}

    I \ddot{\theta} + mgL \theta = 0

This is exactly the equation we solved above.  In particular

.. math::

    \omega = \sqrt{\frac{mgL}{I}} = \sqrt{\frac{mgL}{mL^2}} = \sqrt{\frac{g}{L}}

The period :math:`T` times the angular frequency is :math:`2\pi`

.. math::

    T \omega = 2 \pi

    T = 2 \pi \sqrt{\frac{L}{g}}

The period is independent of the mass.

