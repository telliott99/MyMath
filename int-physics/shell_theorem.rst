.. _shell_theorem:

#############
Shell Theorem
#############

Wikipedia has a beautiful derivation of the "shell theorem," which says that the mass of a spherical object acts in gravitation as if the entire mass :math:`M` were concentrated at the center.

http://en.wikipedia.org/wiki/Shell_theorem}

.. image:: /figs/shell_thm.png
   :scale: 50 %

We will show that this is true for a shell of radius :math:`R`, after that, if we visualize the solid ball as a series of concentric rings we will have the full theorem.

We start by calculating the force due to a ring of mass covered inside the angular width :math:`d \theta`.  Using :math:`\theta` as the variable here is a great idea, because the mass is proportional to the area of the shell along this ring, and the width of the slice is :math:`R \ d \theta`.  The radius of the ring is :math:`R \sin \theta`, so the total surface area is

.. math::

    dA = 2 \pi R \sin \theta R \ d \theta

The mass per unit area is the total mass divided by the surface area of the sphere :math:`M / 4 \pi R^2` so the mass of the ring is

.. math::

    M_r = \frac{M}{4 \pi R^2} 2 \pi R \sin \theta R \ d \theta

    = \frac{M}{2} \sin \theta \ d \theta

Each small piece of the ring has mass :math:`dm` and lies at a distance :math:`s` from the test mass :math:`m`.  It exerts a force of 

.. math::

    dF = \frac{m G \ dm}{s^2}

The second critical insight is that for each piece the force has two components, one acts along a line from the center of the sphere, and the other part cancels, because on the opposite side of the ring there is another small piece with the same force, but in the opposite direction.  The magnitude of the radial part is

.. math::

    dF_r = dF \cos \phi = \frac{mG \cos \phi}{s^2} \ dm

(the force points toward the center of the shell, but in what follows I will work just with the magnitude.  You can pretend there is a unit radial vector coming along in all the calculations).

The total radial force is obtained by substituting the mass of the ring

.. math::

    dF_r = \frac{mG \cos \phi}{s^2} \ \frac{M}{2} \sin \theta \ d \theta

    = \frac{GmM}{2} \frac{\cos \phi \sin \theta}{s^2} \ d\theta

We should integrate from :math:`\theta = 0 \rightarrow \pi` to get the whole thing.

==============
Law of cosines
==============

While the above equation looks nice, the trouble is that it contains three variables:  :math:`s, \phi`, and :math:`\theta`.  However, the law of cosines comes to the rescue.  We use that to get two formulas.  The first is:

.. math::

    R^2 = s^2 + r^2 - 2rs \cos \phi

    \cos \phi = \frac{s^2 + r^2 - R^2}{2rs}

.. image:: /figs/shell_thm.png
   :scale: 50 %

and the second:

.. math::

    s^2 = R^2 + r^2 - 2rR \cos \theta

    \cos \theta = \frac{R^2 + r^2 - s^2}{2rR}

How does this help?  We need :math:`\sin \theta`.  Differentiate the second equation (implicitly)

.. math::

    -\sin \theta \ d \theta = -\frac{2s}{2rR} \ ds

    \sin \theta \ d \theta = \frac{s}{rR} \ ds

We had

.. math::

    dF_r = \frac{GmM}{2} \frac{\cos \phi \sin \theta}{s^2} \ d\theta

substitute for :math:`\theta`

.. math::

    dF_r = \frac{GmM}{2} \frac{\cos \phi \ s}{rRs^2} \ ds

substitute for :math:`\cos \phi`

.. math::

    dF_r = \frac{GmM}{2} \ \frac{(s^2 + r^2 - R^2)}{2rs} \ \frac{s}{rRs^2} \ ds

    =  \frac{GmM}{4R r^2} \ \frac{(s^2 + r^2 - R^2)}{s^2} \ ds

    =  \frac{GmM}{4R r^2} \ [ \ 1 + \frac{(r^2 - R^2)}{s^2} \ ] \ ds

The integral is

.. math::

    F_r = \int dF_r = \int \frac{GmM}{4R r^2} \ [ \ 1 + \frac{(r^2 - R^2)}{s^2} \ ] \ ds

    =  \frac{GmM}{4R r^2} \ [ \ s -  \frac{(r^2 - R^2)}{s} \ ]

What about the limits on :math:`s`?  When :math:`\theta = 0`, :math:`s = r - R`, and when :math:`\theta = \pi`, :math:`s = r + R` so we have

.. math::

    F_r = \frac{GmM}{4R r^2} \ [ \ s -  \frac{(r^2 - R^2)}{s} \ ] \ \bigg |_{r - R}^{r +R}

Notice that we can factor :math:`r^2 - R^2`

.. math::

    F_r = \frac{GmM}{4R r^2} \ [ \ s -  \frac{(r+R)(r-R)}{s} \ ] \ \bigg |_{r - R}^{r +R}

So, just looking at the part in the brackets, at the upper limit we have

.. math::

    r + R - (r - R) = 2R

at the lower limit

.. math::

    r - R - (r + R) = -2R

doing the subtraction 

.. math::

    = 4R

and :math:`4R` just cancels!  We obtain

.. math::

    F_r = \frac{GmM}{r^2}

That is simply outstanding.