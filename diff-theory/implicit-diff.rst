.. _implicit-diff:

########################
Implicit differentiation
########################

Suppose we have

.. math::

    y = x^2
    
    \frac{d}{dx} y = \frac{d}{dx} x^2
    
    \frac{dy}{dx} = 2 x
    
    dy = 2 x \ dx
    
The fancy-pants math guys go to a lot of trouble to prove that the last step is OK, and it is OK.  Here is a case where we would rather not isolate :math:`y`.

.. math::

    x^2 + y^2 = R^2
    
Why not handle this quickly?  What I do is to imagine that :math:`x` is a function of some variable :math:`t` such that :math:`x = t` and then just differentiate with respect to :math:`t`:

.. math::

    \frac{d}{dt} x^2 + y^2 = \frac{d}{dt} R^2 = 0
    
    2 x \frac{dx}{dt} + 2 y \frac{dy}{dt} = 0
    
Now multiply by :math:`1/2` *and* by :math:`dt`:

.. math::

    x dx + y dy = 0
    
    y dy = - x dx
    
    \frac{dy}{dx} = - \frac{x}{y}

The slope of the circle is directly proportional to :math:`-x` and inversely proportional to :math:`y`.

Of course, this particular problem can be solved directly.  Like so:

.. math::

    y = + \sqrt{R^2 - x^2}

So

.. math::
    
    \frac{dy}{dx} = - 2 x \frac{1}{2} \ \frac{1}{\sqrt{R^2 - x^2}}
    
    = - \frac{x}{\sqrt{R^2 - x^2}}
    
    = - \frac{x}{y}
    
which is what we had.
