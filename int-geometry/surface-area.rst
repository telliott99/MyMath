.. _surface-area:

############
Surface Area
############

Suppose we revolve a function :math:`y = f(x)` around the :math:`x`-axis.  We imagine slicing it into disks in the usual way, moving along the :math:`x`-axis in increments :math:`dx`.  To compute the surface area of the solid, we might try adding up the perimeter of all the disks.

Let's start with the simple cone with :math:`R=H`.  What we have is the function

.. math::

    r = h

The circumference at any point :math:`h` is

.. math::

    C(h) = 2 \pi r = 2 \pi h

And the surface area should be

.. math::

    SA = \int C(h) \ dh

(this has a subtle error that we will fix in a minute).

.. math::

    \int_0^H 2 \pi h \ dh

    \pi h^2  \ \bigg |_0^H

    \pi H^2 = \pi R^2

Now, this is obviously not the correct answer.

We can look it up, or we can try to calculate it directly.  Imagine cutting the surface of our cone directly up along the slant and then opening it and laying it flat.  What we will end up with is a sector of a circle.  

.. image:: /figs/cut_cone.png
   :scale: 50 %
  
(The labels in the figure are different than I'm using in the text).

The radius of that circle is the slant height of the cone.  If you draw a cross-section of the cone, you will see that the slant height is the hypotenuse of a right triangle with sides :math:`R` and :math:`S`.

.. math::

    S = \sqrt{R^2 + H^2}

The total circumference of this circle would be :math:`2 \pi S`.

However, we have only part of the circle.  The arc length along the sector that we actually have is the length of the circumference of the base of the cone, which is just :math:`2 \pi R`.

So the total area of the sector (exactly equal to the surface area of the cone) is the total area of the circle, times the ratio of the sector circumference to the total circumference.

.. math::

    SA = \pi S^2 \ \frac{2 \pi R}{2 \pi S} = \pi RS

This is the surface area of a cone.

https://en.wikipedia.org/wiki/Cone#Surface_area

The error in our application of calculus to this problem is a factor of :math:`S/R`.

It turns out that the mistake was to multiply the circumference at each point by :math:`dx`.  What we should have done is to multiply it by the little increment of slant instead.  We assumed that we could use a horizontal width of :math:`dx`, but we need to increase that width by a factor of :math:`S/R`.

Since 

.. math::

    S = \sqrt{R^2 + H^2}

and in this problem

.. math::

    R = H

    S = \sqrt{2} R

So the answer we obtained was :math:`\pi R^2`, whereas the correct answer is :math:`\pi R S`, and in this problem :math:`S =  \sqrt{2} R`, so that's just :math:`\sqrt{2} \pi R^2`.

================
General approach
================

Let me return to our more traditional notation of :math:`x` and :math:`y`.  We have some function :math:`y=f(x)` and we imagine rotating this function around the :math:`x`-axis.  The length that we need to multiply with is not :math:`dx` or :math:`dy` but the hypotenuse of the triangle that they form together, namely

.. math::

    ds^2 = dx^2 + dy^2

    ds^2 = (1 + \frac{dy}{dx})^2 \ dx^2

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx

    ds = \sqrt{1 + f'(x)^2} \ dx

After setting up :math:`ds`, we will integrate

.. math::

    \int 2 \pi y \ ds

    \int 2 \pi y \ \sqrt{1 + f'(x)^2} \ dx

Returning to the general cone problem, we have 

.. math::

    y = \frac{R}{H} x

    f'(x) = \frac{R}{H}

    ds = \sqrt{1 + \frac{R^2}{H^2}} \ dx

So the integral is

.. math::

    \int 2 \pi y \ \sqrt{1 + f'(x)^2} \ dx

    = \int_0^H 2 \ \pi \frac{R}{H} x \ \sqrt{1 + \frac{R^2}{H^2}} \ dx

    = \pi \frac{R}{H} \ \sqrt{1 + \frac{R^2}{H^2}} \int_0^H 2 x \ dx

    = \pi \frac{R}{H} \ \sqrt{1 + \frac{R^2}{H^2}} \ (H^2)

    = \pi RH \ \sqrt{1 + \frac{R^2}{H^2}}

We can also clean up the result above by bringing the :math:`H` inside the square root

.. math::

    = \pi R \ \sqrt{H^2 + R^2}

This is :math:`\pi R S`.  In our particular example of the right circular cone, :math:`R=H` so we have just

.. math::

    SA = \pi R \ \sqrt{2R^2} =  \sqrt{2} \pi R^2

+++++++
Example
+++++++

Consider the circle with radius :math:`R` centered at the origin.

.. math::

    x^2 + y^2 = R^2

    y = f(x) = \sqrt{R^2 - x^2}

Using implicit differentiation, it is easy to show that

.. math::

    2x \ dx + 2y \ dy = 0

    \frac{dy}{dx} = -x/y

Then

.. math::

    ds = \sqrt{1 + \frac{x^2}{y^2}} \ dx

    =  \sqrt{1 + \frac{x^2}{(R^2 - x^2)}} \ dx

And

.. math::

    S = 2 \pi \int y \ ds

    = 2 \pi \int   \sqrt{(R^2-x^2)} \  \sqrt{1 + \frac{x^2}{(R^2 - x^2)}} \ dx

    = 2 \pi \int   \sqrt{R^2 - x^2 + x^2 } \ dx

    = 2 \pi \int R \  dx

    = 2 \pi R x

That's a pretty spectacular simplification!

Now, evaluate from :math:`x = -R \rightarrow R`, giving:

.. math::

    S = 4 \pi R^2

The expected result.
