.. _linear_approx:

####################
Linear approximation
####################

.. image:: /figs/linapprox1.png
   :scale: 50 %

Consider the branch of the hyperbola :math:`xy=1` for :math:`x > 0`, in the first quadrant.  Pick a point :math:`x_0,y_0`---in the figure it is at :math:`P=(1,1)` but it could be anywhere on the curve.  The linear approximation to the curve at :math:`P` is the line that goes through :math:`P` and which has the same slope as the curve does at :math:`P`.

.. math::

    f'(x) = \frac{d}{dx} \ \frac{1}{x} 
    
    = -\frac{1}{x^2} 
    
    = -\frac{1}{x_0^2} \ \ (\text{at} \ x_0)

The equation of the line with this slope and going through :math:`P` is

.. math::

    y - y_0 = -\frac{1}{x_0^2} (x - x_0)

Let's find the x-intercept (:math:`y = 0`).

.. math::

    - y_0 = -\frac{1}{x_0^2} (x - x_0)

But remember that :math:`y_0 = 1/x_0`!

.. math::

    -\frac{1}{x_0} = -\frac{1}{x_0^2} (x - x_0)

    1 = \frac{1}{x_0} (x - x_0)

    x_0 = x - x_0

    x = 2x_0

We could do a similar calculation to find the y-intercept, but life is too short.  By symmetry, :math:`x` and :math:`y` can be interchanged, so

.. math::

    y = 2y_0

And now a neat result is that the area of the triangle determined by this line and the two axes is

.. math::

    A = \frac{1}{2} \ 2x_0 \ 2y_0 =  2x_0 y_0 = 2

The area is the same no matter which point :math:`P` we pick.  Maybe you could sketch a couple of these lines to check the result.