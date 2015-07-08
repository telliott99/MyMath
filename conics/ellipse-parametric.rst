.. _ellipse-parametric:

#######################
Ellipse, parametrically
#######################

.. image:: /figs/ellipse_draw.png
   :scale: 50 %

Learning how to draw an ellipse using two pins and a circular string holding a pencil is an early adventure in mathematics.  The ellipse is the set of all points whose combined distance to the two pins (foci) is the same.

.. image:: /figs/ellipse_wikipedia.png
   :scale: 50 %

The pin positions with respect to the origin or center are called the foci, lying at the points (:math:`\pm f,0`).  The lengths of the axes (called semi-major and semi-minor) are usually labeled :math:`a` and :math:`b`.  Consider the situation when the pencil is at the point :math:`(0,a)`.  The length :math:`L` of the string is equal to twice the distance to the left focus, :math:`L = 2(f+a)`, so

.. math::

    a = \frac{L}{2} - f

We learn in algebra that the equation for an ellipse is

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

Here are three ellipses drawn with the same center.

.. image:: /figs/ellipses_three.png
   :scale: 50 %

They were drawn by adjusting the value on the right-hand side of the equation

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = r^2

where :math:`r = \{ 1/2,1,2 \}`.  This is equivalent to scaling both :math:`a` and :math:`b` by the same factor of :math:`r`

.. math::

    \frac{x^2}{(ra)^2} + \frac{y^2}{(rb)^2} = 1

When :math:`r=2` we need to make the string a bit less than twice as long, because the length :math:`f` is also involved:

.. math::

    ra = r(\frac{L}{2} - f)

===============
Parametrization
===============

An alternative view is the one below, which shows (black curves) the upper half of two circles of radius :math:`r=1` and :math:`r=2` and an ellipse whose equation is 

.. math::

    \frac{x^2}{2^2} + \frac{y^2}{1} = 1

.. image:: /figs/p_ellipse.png
   :scale: 50 %

Here :math:`a=2` and :math:`b=1`.

The standard parametrization of the ellipse is

.. math::

    x = a \cos t

    y = b \sin t

which I had trouble visualizing, until I drew the picture.  The point is that the parameter :math:`t` is *not* the angle that a ray to :math:`P` makes with the :math:`x`-axis, as it is for the circle.  Instead, to find the :math:`x` value of :math:`P` corresponding to :math:`t`, we extend the ray with angle :math:`t` to the larger circle, with radius :math:`a`, where we read off the :math:`x`-value as 

.. math::

    x=a \cos t

We go back to find the intersection of the same ray with the small circle to get 

.. math::

    y = b \sin t

The algebraic way to do this is to show that the parametrization is equivalent to the original formulation

.. math::

    x^2 = a^2 \cos^2 t

    y^2 = b^2 \sin^2 t

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = \cos^2 t + \sin^2 t = 1

as expected.

========
Rotation
========

Let's return to the diagram of the ellipse with two bounding circles of radius :math:`a` and radius :math:`b`.  I have a new diagram below.

Consider the coordinates of the point :math:`P=(x,y)` (the red dot in the first quadrant) as functions of the angle :math:`t`.  As we said, :math:`t` is *not* the angle of a ray from the origin to :math:`P`.

Let's draw a ray (blue dotted line) from the origin that does have angle :math:`t` with the :math:`x`-axis.  How to find :math:`x` and :math:`y` from the diagram.  For :math:`x`, extend the ray to the outer circle.  The radius is :math:`a`, the angle is :math:`t`, and

.. math::

    a \cos t = x

This is the parametrization of the ellipse introduced above.

.. image:: /figs/ellipse_fancy.png
   :scale: 50 %

The ray drawn with angle :math:`t` has the same :math:`x`-intercept with the outer circle as our point :math:`P` on the ellipse.  Similarly, the intercept of the ray with the inner circle has the same :math:`y`-value as the point :math:`P` on the ellipse.

We estimate the point :math:`P=(1.2,0.8)=(6/5,4/5)`.  Using our algebraic equation:

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

Recall that :math:`a=2` and :math:`b=1` so

.. math::

    x^2 + 4y^2 = 4

Plugging in for :math:`x^2` and :math:`y^2` we get

.. math::

    \frac{36}{25} + 4 \ (\frac{16}{25}) = \frac{100}{25} = 4

as expected.  Reading off the intercepts for the ray with angle :math:`t` (dotted blue line) with the outer circle, we have the point :math:`(1.2,1.6)` at a distance :math:`2` from the origin.  Thus,

.. math::

    \frac{1.2}{2} = 0.6 = \cos t

    \approx 0.927\ \text{rad} \approx 53^{\circ}

Looking again at the figure, we want to consider what happens for the angle :math:`u = t + \pi/2`.  This is the dotted blue ray in the second quadrant.

We might calculate the values of sine and cosine for :math:`u`, but notice that if we view :math:`u` as a vector, its *dot product* with :math:`t` must be equal to zero.  The coordinates of the intercept of the rotated vector with the outer circle are :math:`(-1.6,1.2)`, so the cosine of the angle :math:`u` is

.. math::

    \cos u = -0.8

    u \approx 2.498 = t + \frac{\pi}{2} \ \text{rad} \approx 143^{\circ}

We confirm that 

.. math::

    2.498 - 0.927 = 1.57 = \frac{\pi}{2}

The coordinates of the point on the ellipse are :math:`(-1.6,0.6)`, which we check against the formula

.. math::

    x^2 + 4y^2 = 4

    (1.6)^2 + 4(0.6)^2 = 2.56 + 4(0.36) = 4

(no clean fractions this for this one).

=======
Tangent
=======

Finally, and this is really the point of the chapter, the vector to the point, call it :math:`Q`, on the ellipse (red dot in the second quadrant) is the tangent to the ellipse for the point :math:`P` in the first quadrant, and vice-versa.

How did this happen?  Recall what we did.  We had 

.. math::

    x = a \cos t

    y = b \sin t

The rotated point :math:`Q = (x',y')` is

.. math::

    x' = a \cos (t + \frac{\pi}{2})

    y' = b \sin (t + \frac{\pi}{2})

.. image:: /figs/sine_cosine_wikipedia.png
   :scale: 50 %

Sine is like cosine, but shifted to the right (forward in time) by :math:`\pi/2`

.. math::

    \cos \theta = \sin (\theta + \frac{\pi}{2})

    \sin \theta = - \cos (\theta + \frac{\pi}{2})

So

.. math::

    x' = a \cos (t + \frac{\pi}{2}) = -a \sin t

    y' = b \sin (t + \frac{\pi}{2}) = b \cos t

So what, you say.  Well, let's look at the position vector, which can be written :math:`\mathbf{r}(t)`, since it's a function of the angle :math:`t` or the time, but we will just use :math:`\mathbf{r}`.  It has components :math:`x` and :math:`y`.

.. math::

    \mathbf{r} = \ \langle x,y \rangle \ = \ \langle a \cos t,b \sin t \rangle

Now, the tangent to the ellipse is precisely the direction in which a particle at :math:`(x,y)` is currently moving on the ellipse.  The tangent vector points in the same direction as the velocity vector, but :math:`\mathbf{v}` is just the time-derivative of the position vector.

.. math::

    \mathbf{v} = \frac{d\mathbf{r}}{dt} = \ \langle \frac{dx}{dt}, \frac{dy}{dt} \rangle \ = \ \langle -a \sin t,b \cos t \rangle = \ \langle x',y' \rangle

And that's the point.   :)

===============
Tangent algebra
===============

Consider the ellipse with equation:

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

and a point on the ellipse :math:`(x_0, y_0)`

According to 

http://www.algebra.com/algebra/homework/Quadratic-relations-and-conic-sections/Tangent-lines-to-an-ellipse.lesson

The tangent to the ellipse has the equation:

.. math::

    \frac{x \ x_0}{a^2} + \frac{y \ y_0}{b^2} = 1

This is the equation of a line in the unknowns :math:`x` and :math:`y`.

To prove that this is the correct equation, first observe that when we plug in :math:`(x = x_0, y = y_0)` we obtain the equation of the ellipse.

.. math::

    \frac{x_0^2}{a^2} + \frac{y_0^2}{b^2} = 1

This shows that :math:`(x = x_0, y = y_0)` is on the line.

Second, we will show that *only* the point :math:`(x = x_0, y = y_0)` satisfies both equations.  We solve the equation of the tangent line for :math:`y`:

.. math::

    y = \frac{b^2}{y_0} (1 - \frac{x_0}{a^2} x)
    
square it:

.. math::

    y^2 = \frac{b^4}{y_0^2} (1 - 2\frac{x_0}{a^2} x + \frac{x_0^2}{a^4} x^2)

and then substitute into the equation of the ellipse, obtaining:

.. math::

    \frac{x^2}{a^2} + \frac{1}{b^2}\ [ \ \frac{b^4}{y_0^2} (1 - 2\frac{x_0}{a^2} x + \frac{x_0^2}{a^4} x^2) \ ] \ = 1

    \frac{x^2}{a^2} + \frac{b^2}{y_0^2} (1 - 2\frac{x_0}{a^2} x + \frac{x_0^2}{a^4} x^2) = 1

Multiply by :math:`a^2y_0^2/b^2`:

.. math::

    \frac{y_0^2}{b^2}x^2 + a^2 - 2x_0 x + \frac{x_0^2}{a^2} x^2 = \frac{a^2 y_0^2}{b^2}

But

.. math::

    \frac{x_0^2}{a^2} + \frac{y_0^2}{b^2} = 1
    
so the equation reduces to:

.. math::

    x^2 - 2 x_0 x + a^2 - \frac{a^2 y_0^2}{b^2} = 0

Observe first that plugging into the **quadratic equation** and ignoring the determinant for the moment, we have

.. math::

    x = \frac{2 x_0}{2}

    x = x_0

and so 

.. math::

    x_0^2 - 2 x_0 x_0 + a^2 - \frac{a^2 y_0^2}{b^2} = 0
    
    - \frac{x_0^2}{a^2} + 1 - \frac{y_0^2}{b^2} = 0
    
    \frac{x_0^2}{a^2} + \frac{y_0^2}{b^2} = 1

And then secondly, the discriminant squared is:

.. math::

    D^2 = 4 x_0^2 + 4a^2 (\frac{y_0^2}{b^2} - 1) 
    
    \frac{D^2}{4a^2} = \frac{x_0^2}{a^2} + (\frac{y_0^2}{b^2} - 1) 

    \frac{D^2}{4a^2} = 0

The only way this can be zero is if the discriminant :math:`D` is equal to zero.  Therefore :math:`(x_0,y_0)` is the *only* solution.

Finally, consider the original equation of the line:

.. math::

    y = \frac{b^2}{y_0} (1 - \frac{x_0}{a^2} x)

This line has slope:

.. math::

    m = - \frac{b^2}{y_0} \ \frac{x_0}{a^2}

Now think about the point we had above as :math:`(x',y')` and relabel it as :math:`(x_0',y_0')` to be clear that we are talking about the points obtained using the same angle :math:`t`

.. math::

    x_0 = a \cos t
    
    y_0 = b \sin t
    
    x_0' = - a \sin t
    
    y_0' = b \cos t

The slope of the line from the origin to :math:`(x_0',y_0')` is:

.. math::

    m = \frac{- y_0'}{- x_0'} 
    
    = -\frac{b \cos t}{a \sin t}

Substitute for :math:`\cos t` and :math:`\sin t`:

.. math::

    m = - \frac{b}{a} \ \frac{x_0/a}{y_0/b}
    
    = - \frac{b^2}{y_0} \ \frac{x_0}{a^2}

This matches what we have for the slope from the equation for the line tangent to the ellipse at :math:`(x_0,y_0)`.