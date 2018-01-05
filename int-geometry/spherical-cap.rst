.. _spherical-cap:

#############
Spherical cap
#############

Here, we'll explore the formula for the volume of a spherical cap.  This is the solid obtained by slicing off a part of a sphere with a plane. 

.. image:: /figs/spherical_cap.png
   :scale: 50 %

The formula we will derive is 

.. math::

    V_{cap} = \frac{1}{3} \pi h^2(3R - h)

or equivalently

.. math::

    V = \pi(Rh^2 - \frac{1}{3} h^3 )

We can see that this equation makes sense for the extreme case where :math:`h=R`.  We get 

.. math::

    V = \frac{1}{3} \pi R^2(3R - R) =   \frac{2}{3} \pi R^3

==========================
Surface area of the sphere
==========================

Let's begin by recalling the formula for the surface area of the sphere

.. math::

    A = 4 \pi R^2

Archimedes has a derivation of this in *On the Sphere and Cylinder* which is explained in Dunham's book *The Mathematical Universe*.  I'd prefer not to take that detour here, but note that calculus provides a simple proof, starting from the formula for the volume of a sphere

.. math::

    V= \frac{4}{3} \pi R^3

Suppose we take a sphere of radius :math:`r`.  (I use :math:`r` here because for just this part, the radius will be a variable).  If we increase the radius by a little bit :math:`dr`, then how does the volume change?  It changes exactly like the surface area!  That is

.. math::

    dV = A \ dr

    A = \frac{d}{dr} \ V = \frac{d}{dr} \ \frac{4}{3} \pi r^3 = 4 \pi r^2

Another way to see this is to break up the entire surface area of the sphere into small cones, each with area :math:`dA` (almost flat) and height :math:`R`.  The volume of one cone is

.. math::

    \frac{1}{3}R \ dA

If we add up the volumes of all the little cones from the entire sphere we will have the volume of the sphere

.. math::

    \frac{1}{3}R \ A

but we already know this is just :math:`4/3 \pi R^3`,
so clearly

.. math::

    \frac{1}{3} RA = \frac{4}{3}\pi R^3

    A = 4 \pi R^2

===================================
Volume of the sphere using calculus
===================================

A modern way to do this is by integration of slices (from Strang)

.. image:: /figs/sph_slices.png
   :scale: 50 %

At each value of :math:`x`, the cross-section of the hemisphere (radius :math:`R`) is a half-circle with radius :math:`r` such that

.. math::

    x^2 + r^2 = R^2

the area of this hemisphere cross-section is

.. math::

    A = \frac{1}{2} \pi r^2= \frac{1}{2} \pi (R^2 - x^2)

For the whole sphere, each cross-section is a circle with area

.. math::

    A =  \pi r^2= \pi (R^2 - x^2)

For the volume, we just add up all these slices.  To make it simple, take :math:`x` from :math:`x=-R \to x=R` 

.. math::

    V =  \int_{-R}^{R} \pi (R^2 - x^2) \ dx

    V =  \pi \int_{-R}^{R}  (R^2 - x^2) \ dx

    =  \pi \ [ \ R^2x - \frac{1}{3}x^3 \ ] \ \bigg |_{-R}^R

    =  \pi \ ( R^3 - \frac{1}{3}R^3 -(-R)^3 + \frac{1}{3}(-R)^3

    =  \frac{4}{3}\pi R^3

===========================
Volume of the spherical cap
===========================

For the cap, just change the lower limit of integration to :math:`x=R-h`  !! 
 
.. image:: /figs/spherical_cap.png
   :scale: 50 %

We need to evaluate

.. math::

    V = \pi \ [ \ R^2x - \frac{1}{3}x^3 \ ] \ \bigg |_{R-h}^R

Leave aside the factor of :math:`\pi`, and break the expression into two parts

.. math::
 
    R^2x  \ \bigg |_{R-h}^R - \frac{1}{3} x^3  \ \bigg |_{R-h}^R

For the left term we get

.. math::

    R^3 - R^3 + R^2h = R^2h

For the right side we get

.. math::

    -\frac{1}{3} R^3 + \frac{1}{3}(R-h)^3 )

    -\frac{1}{3} R^3 + \frac{1}{3} R^3 - R^2h + Rh^2 -\frac{1}{3} h^3

Adding left and right terms together, the :math:`R^2h` cancel, and we have finally

.. math::

    V = \pi (Rh^2 - \frac{1}{3} h^3)

Factoring out :math:`\frac{1}{3} h^2`

.. math::

    V = \frac{1}{3} \pi h^2 (3R -h)

which is the formula we gave at the top.

==========================
Volume of a spherical belt
==========================

We can calculate the volume of any spherical belt by using the appropriate limits of integration.  For example, the belt from :math:`r=0 \rightarrow r = R-h` has volume

.. math::

    V = \pi \ [ \ R^2x - \frac{1}{3}x^3 \ ] \ \bigg |_{0}^{R-h}

Leaving the :math:`\pi` aside for now

.. math::

    R^2(R-h) - \frac{1}{3}(R-h)^3

    R^3 - R^2h - \frac{1}{3}(R^3 - 3R^2h + 3Rh^2 - h^3)

    \frac{2}{3}R^3 - Rh^2 + \frac{1}{3} h^3

With the factor of :math:`\pi`

.. math::

    V = \pi ( \frac{2}{3}R^3 - Rh^2 + \frac{1}{3} h^3 )

Adding the cap and the belt together:

.. math::

    V_{tot} =  \pi( Rh^2 - \frac{1}{3}h^3 + \frac{2}{3}R^3 - Rh^2 + \frac{1}{3} h^3)

Almost everything cancels

.. math::

    V_{tot} =  \pi( \frac{2}{3}R^3)

The cap and the belt together make up a hemisphere.

======
Part 2
======

Now I want to show a different derivation of the formula for the volume of a spherical cap. 

.. image:: /figs/spherical_cap.png
   :scale: 50 %

The formula is 

.. math::

    V_{cap} = \frac{1}{3} \pi h^2(3R - h)

Actually, I will show two different derivations.  The first is perhaps easiest but requires us to know the surface area of the spherical cap.  So that's where we start.

=======================
Surface area of the cap
=======================

The formula for the surface area of a part of the sphere is not very complicated.  Amazingly, it doesn't matter whether we are dealing with a spherical cap of height :math:`h` or a belt around the sphere at the equator with width :math:`h` (or somewhere in between).  At each point, the surface area is :math:`A = 2\pi Rh`.  Here is a  simple argument.

If we start from the equator, and think about a thin belt going around the circumference, the belt has length equal to the circumference :math:`2\pi R` and width :math:`h`, and thus area

.. math::

    A = 2 \pi R h

We believe this should be the formula for the surface area of a belt of width :math:`h`, at least near the equator.  In the figure, we have labeled this width as :math:`R-h`, because we are really interested in the cap.  Thus, for the calculation below, this area will be :math:`2\pi R(R-h)`.

Consider that the total surface area of the hemisphere is :math:`2\pi R^2` so the area of the cap is the difference

.. math::

    A = 2\pi R^2 -  2 \pi R (R-h) = 2 \pi Rh

That is, the area of the cap depends only on :math:`R` and its width (here called :math:`h`).

Furthermore, if we look in the figure at the right triangle with :math:`h` and :math:`a` as the sides, then :math:`r` (not labeled in the figure) is the hypotenuse of that triangle.  It is sometimes called the slant height.  We calculate

.. math::

    a^2 = R^2 - (R - h)^2 = 2 Rh - h^2

    r^2 = a^2 + h^2 = 2 Rh - h^2 + h^2 = 2 Rh

Now think about a very small spherical cap, then it would be almost flat, a circle, and its radius would be :math:`r` and area

.. math::

    A = \pi r^2

But :math:`r^2 = 2Rh`, so again we have the same formula for the surface area of a small cap and a belt near the equator!

Now consider a belt of width :math:`h` at some position which is not close to either the top or the horizontal diameter of this cross-section of the sphere.  In using the formula :math:`A = 2 \pi R h`, if :math:`h` is the width of the belt on the surface, that suggests that the circumference at this position is :math:`2 \pi R`, which is obviously wrong.  It should be :math:`2\pi a`.

Here's a sketch:

.. image:: /figs/sphcap2.png
   :scale: 50 %

We want the area of the spherical belt of height :math:`h`  whose radius is :math:`a`.  The angles are labeled in blue as :math:`s` and :math:`t`, and they are complementary angles.

.. math::

    a = R \cos s

So :math:`a` is smaller than :math:`R` by the factor :math:`\cos s`.  In the right panel, we show a small triangle at the surface of the sphere.  The width :math:`w` is flat on the surface, and since the dotted line is the radius :math:`R`, :math:`R` makes a right angle where it intercepts :math:`w`.  By complementary angles, we can see that the angle at the top of this triangle is also equal to :math:`s`, so we have the relationship

.. math::

    h = w \cos s

So the true area is

.. math::

    2 \pi a w = 2 \pi R \cos s \frac{h}{\cos s} = 2 \pi R h

The cosine of the angle comes in twice, and these factors cancel.  The formula :math:`2\pi R h` is correct everywhere.

=========================
Approach through calculus
=========================

As an alternative, I have a derivation from calculus.

The surface area of a volume of revolution is

.. math::

    A = 2 \pi \int y \sqrt{1 + (\frac{dy}{dx})^2} \ dx

The square root comes from the surface area element.  This formula looks unwieldy (and often is difficult to work with).  But in this particular case it simplifies dramatically.

If we take a circle as the curve, with formula

.. math::

    x^2 + y^2 = R^2

    2x \ dx + 2y \ dy = 0

    \frac{dy}{dx} = - \frac{x}{y}

So

.. math::

    A = 2 \pi \int y \ \sqrt{1 + \frac{x^2}{y^2}} \ dx

    A = 2 \pi \int \sqrt{y^2 + x^2} \ dx

    A = 2 \pi \int R \ dx = 2 \pi R x

Evaluated between :math:`x=a \to x=b`

.. math::

    A = 2 \pi R (b-a) = 2 \pi R h

This makes it very clear that the area does not depend where we are on the sphere.  A spherical cap with height :math:`h` has the same area as a belt of width :math:`h` wrapped around the equator, or any belt of width :math:`h` in between the two.

And as we noticed before, the area of a belt or sperical cap, :math:`2 \pi R h`, is equal to the surface area of a cylinder of radius :math:`R` and height :math:`h`, the so-called hat-box theorem.

======================================
Volume of the spherical cap:  method 1
======================================

Once we have the area of the spherical cap, we can calculate the volume fairly easily.  We consider first a spherical segment (the segment of the whole sphere whose surface is the spherical cap).  The volume of the segment is just the volume of the sphere times the fractional area

.. math::

    V_{segment} = \frac{4}{3}\pi R^3 \ \ \frac{2 \pi R h}{4 \pi R^2} = \frac{2}{3} \pi R^2 h

The volume of the spherical cap is this volume, minus the volume of the cone with height :math:`R-h` and base of :math:`\sqrt{R^2 - (R-h)^2}`.  The cone has volume

.. math::

    V_{cone} = \frac{1}{3}\pi (R-h)(R^2-(R-h)^2)

Working with the inside part

.. math::

    (R-h)(R^2-(R-h)^2)

    (R-h)(2Rh - h^2)

    2R^2h - Rh^2 - 2Rh^2 + h^3

    2R^2h - 3Rh^2 + h^3

So

.. math::

    V_{cone} = \frac{1}{3}\pi (2R^2h - 3Rh^2 + h^3)

And

.. math::

    V_{cap} = V_{segment} - V_{cone}

    = \frac{2}{3} \pi R^2 h - \frac{1}{3}\pi (2R^2h - 3Rh^2 + h^3)

    = \frac{1}{3} \pi (3Rh^2 - h^3)

    V_{cap} = \frac{1}{3} \pi h^2(3R - h)

======================================
Volume of the spherical cap:  method 2
======================================

I want to use Archimedes' method to repeat this derivation, so let's review how to do the volume for a normal sphere.  If you remember, it is easy to show that the area of each horizontal slice through the hemisphere added to that for the inverted cone (at the same height :math:`h`) is equal to the area of a slice of the cylinder (which is a constant).

.. image:: /figs/sphere_cone.png
   :scale: 50 %

.. math::

    r_{s}^2 = R^2 - h^2

    r_{c}^2 = h^2

    r_{s}^2 + r_{c}^2 = R^2

Therefore

.. math::

    A_{s} + A_{c} = A_{cyl}

To get the volume of a spherical cap, we need to find the volume of the base of the cone after cutting off the top (to form what's called a frustrum).  That volume is the difference between the whole volume of the cone and the volume of the missing top piece.

I didn't redraw the figure above, but to match wikipedia and Wolfram :math:`h` will need to be the height of the frustrum and :math:`R-h` the height of the small cone.

.. image:: /figs/spherical_cap.png
   :scale: 50 %

That is, I will use :math:`h` for the distance from the top of the sphere to the plane which cuts through to form the spherical cap.  The radius of the sphere (and the cone) will be :math:`R` as before, and the radius at the height :math:`h` will be :math:`a`. 

From the Pythagorean Theorem

.. math::

    a^2 + (R-h)^2 = R^2

    a^2 + R^2 - 2hR + h^2 = R^2

    R = \frac{a^2 + h^2}{2h}

We will use this relationship later in simplifying our formula.

Now the volume of the whole cone is

.. math::

    V_C = \frac{1}{3} \pi R^3

And the volume of the small cone with height :math:`R-h` is

.. math::

    V_c = \frac{1}{3} \pi (R-h)^3 = \frac{1}{3} \pi (R^3 - 3R^2h + 3Rh^2 - h^3)

The difference is the volume of the frustrum

.. math::

    V_{frust} = V_C - V_c = \frac{1}{3} \pi \ [ \ R^3 - R^3 + 3R^2h - 3Rh^2 + h^3 \ ]

    = \frac{\pi}{3} \ [ \ 3R^2h - 3Rh^2 + h^3 \ ]

The volume of the cylinder is 

.. math::

    V_{cyl} = \pi R^2 h

Subtracting the volume of the frustrum, we obtain the volume of the spherical cap

.. math::

    V_{cap} = V_{cyl} - V_{frust}

    = \pi R^2 h - \frac{1}{3} \pi (3R^2h - 3Rh^2 + h^3)

    = \frac{\pi}{3} (3Rh^2 - h^3)

    V_{cap} = \frac{\pi}{3} h^2 (3R - h)}

which matches what we had at the top.

.. image:: /figs/spherical_cap.png
   :scale: 50 %

We can get a different form if we substitute for :math:`R` from above

.. math::

    V_{cap} = \frac{\pi}{3} h^2 \ [ \ 3 \ \frac{a^2 + h^2}{2h} - h\ ]

    V_{cap} = \pi ( \frac{1}{2}a^2h + \frac{1}{2}h^3 - \frac{1}{3}h^3 ]

    V_{cap} = \pi ( \frac{1}{2}a^2h + \frac{1}{6}h^3 ]

    V_{cap} = \frac{\pi}{6} h (3a^2 + h^2)
