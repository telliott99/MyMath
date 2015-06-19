.. _polar:

#################
Polar Coordinates
#################

In standard polar coordinates points are plotted by distance from the origin, :math:`r`, as well as the angle that this ray makes with the positive :math:`x`-axis, :math:`\theta`.  Converting from :math:`x,y` to :math:`r, \theta` is pretty easy:

.. math::

    x = r \cos \theta

    y = r \sin \theta

To go the other way, use Pythagoras to write 

.. math::

    x^2 + y^2 = r^2
    
    r = \sqrt{x^2 + y^2}

    \theta = \tan^{-1} (\frac{y}{x}), \ \ x \ne 0

In polar coordinates, as in Cartesian (:math:`xy`) coordinates, the equation of a circle depends on whether it is at the origin or not.  If it is at the origin, then something like

.. math::

    r = 3

defines the graph.  But if it's not, then the equations are of the form:

.. math::

    r = a \cos \theta + b \sin \theta

For example, 

.. math::

    r = 3 \sin \theta

is a circle centered at :math:`x = 0, y = 3/2`, with a radius of :math:`3/2` (it passes through the origin and the point :math:`(x=0,y=3)`.

while

.. math::

    r = \sin \theta + \cos \theta

is a circle centered at  :math:`x = 3/2, y = 3/2` which passes through the origin.

Let's see if we can manipulate these equations to go back to Cartesian coordinates.

+++++++
Example
+++++++

.. math::

    r = 3 \sin \theta

    y = r \sin \theta

    \sin \theta = \frac{y}{r}

    r = \frac{3y}{r}

    r^2 = 3y = x^2 + y^2

complete the square:

.. math::

    x^2 + y^2 -3y + \frac{3}{2} =  \frac{3}{2}

    x^2 + (y - \frac{3}{2})^2 = (\sqrt{\frac{3}{2}})^2

+++++++
Example
+++++++

.. math::

    r = \sin \theta + \cos \theta

    r = \frac{y}{r} + \frac{x}{r}

    r^2 = x + y = x^2 + y^2

    x^2 - x + \frac{1}{4} + y^2 - y + \frac{1}{4} = \frac{1}{2}

    (x - \frac{1}{2})^2 + (y - \frac{1}{2})^2 = (\frac{1}{\sqrt{2}})^2

One can also write the equations for other conic sections in polar coordinates.

+++++++
Example
+++++++

The following is a parabola:

.. math::

    r = \frac{2}{1 + \sin \theta}

Plot it to see.  Or just do this:

.. math::

    r  + r \sin \theta) = 2

    \frac{y}{r} = \sin \theta

    r + y = 2

    r^2 = (2-y)^2  = x^2 + y^2

    4 - 4y + y^2 = x^2 + y^2

    y - 1 = -\frac{1}{4} x^2

This image has some examples from *The Calculus Lifesaver*.

.. image:: /figs/polarex.png
   :scale: 50 %

=========================
Integration to find areas
=========================

The idea for (one-dimensional) integration in polar coordinates is that we know :math:`r` as a function of :math:`\theta`.  For example, we had the circle centered at :math:`(0,3/2)` given by

.. math::

    r = 3 \sin \theta

We imagine dividing up the circle into little triangles, sectors where 

.. math::

    \theta \rightarrow \theta + \Delta \theta

The sector is approximately a triangle with side :math:`r` and base :math:`r \times \Delta \theta` (the latter is the length of the arc of the circle on its circumference).

The area of each little sector is

.. math::

    \frac{1}{2} r^2 d \theta

.. image:: /figs/polararea.png
       :scale: 25%

The total area is then

.. math::

    \int_0^{2\pi}  \frac{1}{2} r^2 d \theta

    = \int_0^{2\pi}  \frac{1}{2} (3 \sin \theta)^2 d \theta

    = \frac{9}{2} \int_0^{2\pi}  \sin^2 \theta d \theta

This looks hard but we've done it before.  One way is to recall that 

.. math::

    [ \ \sin \theta \cos \theta \ ]' = - \sin^2 \theta + \cos^2 \theta

    =  1 - 2 \sin^2 \theta

Integrate

.. math::

    \int [ \ \sin \theta \cos \theta \ ]' \ d \theta = \int (1 - 2 \sin^2 \theta) \ d \theta

    \sin \theta \cos \theta  = \theta - 2 \int \sin^2 \theta \ d \theta

Hence

.. math::

    \int \sin^2 \theta \ d \theta = \frac{1}{2}  (\theta - \sin \theta \cos \theta)


So our answer is

.. math::

    = (\frac{9}{2}) \ \frac{1}{2} (x -  \sin \theta \cos \theta) \ \bigg |_0^{2\pi}

    =  (\frac{9}{2}) \ \frac{1}{2} (2 \pi)

    = \frac{9\pi}{4}

which is correct for a circle with radius :math:`3/2`.

========
Cardioid
========

The second example is the cardioid, which is a bit trickier.  Our example was

.. math::

    r = 1 + 2 \cos \theta

.. image:: /figs/cardioid.png
   :scale: 50 %

Recall

.. math::

    A = \int  \frac{1}{2} r^2 d \theta

so plug in to obtain

.. math::

    \int  \frac{1}{2} (1 + 2 \cos \theta)^2 d \theta

    \int  \frac{1}{2} (1 + 4 \cos \theta + 4 \cos^2 \theta) d \theta

    = \frac{\theta}{2} + 2 \sin \theta + 2\int cos^2 \theta + C

We've also done this one (:math:`\cos^2 \theta`) before, and of course, we did :math:`\sin^2 \theta` above.  Since we already have the integral for :math:`\sin^2`, and to approach things a bit differently, recall

.. math::

    \sin^2 \theta + \cos^2 \theta = 1

Hence

.. math::

    \int \sin^2 \theta \ d\theta + \int \cos^2 \theta \ d\theta = \int 1 \ d\theta

So

.. math::

    \int \cos^2 \theta \ d\theta = \theta - \ [ \ \frac{1}{2}  (\theta - \sin \theta \cos \theta) \ ]

    = \frac{1}{2} ( \theta + \sin \theta \cos \theta)

Putting it all together, we obtain the expression:

.. math::

    \frac{3}{2}\theta + 2 \sin \theta + \sin \theta \cos \theta

The cardioid is a strange shape.  We can get the area of the first sector (:math:`\theta = 0 \rightarrow \pi/2`) easily, just evaluate the expression at both limits and subtract one from the other:

The :math:`\sin \theta \cos \theta` term goes away for both :math:`\theta=0` and :math:`\theta = \pi/2`, as do all the other terms for :math:`\theta = 0`, so we have just :math:`2 + 3\pi/4` as the area under the curve in the first quadrant.

On the other hand, if we look carefully at the figure and the equation, what happens as :math:`\theta = \pi/2 \rightarrow \pi`
 ?

.. image:: /figs/cardioid.png
   :scale: 50 %

The part of the area that shows up as gray in the second quadrant comes comes between :math:`\theta = \pi/2 \rightarrow 2\pi/3`.  We obtain that upper limit by solving for

.. math::

    r = 1 + 2 \cos \theta = 0

    \cos \theta = - \frac{1}{2}

The angle with cosine - 1/2 in this quadrant is :math:`2\pi/3`.

So now we need to evaluate the expression at :math:`\theta = 2\pi/3`:

.. math::

    \frac{3}{2}\theta + 2 \sin \theta + \sin \theta \cos \theta

    \pi + \sqrt{3} - \frac{\sqrt{3}}{4} = \pi + \frac{3}{4}\sqrt{3}

This (minus the value at :math:`\pi/2`) is the area of the sliver in the second quadrant.  (And notice:  we could never do this in Cartesian coordinates).

The last part is even weirder.  If you follow the graph it comes into the fourth quadrant and arches up to the point :math:`(1,0)`, when :math:`\theta = \pi`.  How can this be?  

It happens because although :math:`\theta = 2\pi/3 \rightarrow \pi` (:math:`\theta` is still in the second quadrant), the value of :math:`r` is *negative*.  

In order to get the whole area, we will integrate between :math:`\theta = 0 \rightarrow 2\pi`, but we would like to count the part of the area between :math:`\theta = 2/3 \pi \rightarrow 4/3 \pi` as negative, subtracting it from the earlier result (see the picture).  The problem is that our formula has :math:`r^2` in it.  We fix that by doing the calculation but remembering the area is really negative.  

Further we need to subtract this funny area twice ..

The reason is that the area we get by integrating (:math:`\theta = 0 \rightarrow 2\pi`) is really this:

.. image:: /figs/cardioid2.png
   :scale: 50 %

At :math:`\theta = 4/3 \pi`

.. math::

    \frac{3}{2}\theta + 2 \sin \theta + \sin \theta \cos \theta

    2\pi - \sqrt{3} + \frac{\sqrt{3}}{4} = 2 \pi - \frac{3}{4} \sqrt{3}

In summary, we have these values for our expression

.. math::

    f(0)=0

    f(\frac{1}{2}\pi ) = 2 + \frac{3}{4} \pi

    f(\frac{2}{3}\pi ) = \pi + \frac{3}{4}\sqrt{3}

    f(\pi ) = \frac{3}{2}\pi

    f(\frac{4}{3}\pi ) = 2\pi - \frac{3}{4} \sqrt{3}

    f(2\pi ) = 3 \pi

So the total is 

.. math::

    3 \pi - 0 - 2\ [ \ (2\pi - \frac{3}{4} \sqrt{3}) - (\pi + \frac{3}{4}\sqrt{3}) \ ]

    = 3 \pi - 2(\pi - \frac{3}{2} \sqrt{3})

    = \pi + 3 \sqrt{3} \approx 8.38

Compare that with the area of a circle of radius :math:`1/2`, :math:`\approx 7.07`.  It looks like a reasonable answer.

==========
Arc length
==========

Suppose we have this equation

.. math::

    r = \sin^2 \frac{\theta}{2}

I don't have the greatest intuition for these things yet, but a plot shows this is a cardioid.

.. image:: /figs/cardioid.png
   :scale: 50 %

The problem asks us to find the *arc length*.  If this were a problem in Cartesian coordinates, we would be looking for each little bit of arc length :math:`ds` which is the hypotenuse of a right triangle with sides :math:`dx` and :math:`dy` and so

.. math::

    ds^2 = dx^2 + dy^2

Multiply and divide on the right by :math:`dx^2`

.. math::

    ds^2 = (1 + (\frac{dy}{dx})^2) \ dx^2

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx

We just integrate this from the starting point to the end point.

What about polar coordinates?  If you sketch what happens along a little bit of arc of a curve in polar coordinates, one side of our right triangle is :math:`dr`, but the other side is :math:`r d\theta` (:math:`\theta` nad :math:`d \theta` by themselves are just angles).  So

.. math::

    ds^2 = r^2 d \theta^2 + dr^2

Multiply and divide on the right by :math:`d\theta^2`

.. math::

    ds^2 = (r^2 + (\frac{dr}{d \theta})^2)) \ d \theta^2

    ds = \sqrt{r^2 + (\frac{dr}{d \theta})^2} \ d \theta

Check it in wikipedia to confirm.  OK.

Returning to the function in the problem

.. math::

    r = \sin^2 \frac{\theta}{2}

    r^2 = \sin^4 \frac{\theta}{2}

    \frac{dr}{d\theta} = 2 \sin \frac{\theta}{2} (\frac{1}{2}) \cos  \frac{\theta}{2}

    = \sin \frac{\theta}{2} \cos  \frac{\theta}{2}

    (\frac{dr}{d\theta})^2 = \sin^2 \frac{\theta}{2} \cos^2  \frac{\theta}{2}

So

.. math::

    ds = \sqrt{\sin^4 \frac{\theta}{2} + \sin^2 \frac{\theta}{2} \cos^2  \frac{\theta}{2}} \ d \theta

    = \sin \frac{\theta}{2} \sqrt{\sin^2 \frac{\theta}{2} +  \cos^2  \frac{\theta}{2}} \ d \theta

    = \sin \frac{\theta}{2}  \ d \theta

To get the arc length we integrate :math:`ds`

.. math::

    \int \ ds = - 2 \cos \frac{\theta}{2} + C

For example from :math:`\theta = 0 \rightarrow \pi`

.. math::

    = - 2 \cos \frac{\theta}{2} \ \bigg |_0^{\pi} = 2

which seems reasonable.  If this were a circle with radius :math:`r=0.5`, the semi-perimeter would be :math:`\pi r \approx 1.57`.
