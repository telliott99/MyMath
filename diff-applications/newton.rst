.. _newton:

###############
Newton's method
###############

Consider the problem of finding the square root of :math:`2`.

.. math::

    x = \sqrt{2}
    
    x^2 = 2
    
    x^2 - 2 = 0

If we rewrite the last equation as:

.. math::

    y = x^2 - 2

By finding the "roots" of this polynomial, the values of :math:`x` which satisfy :math:`y=0`, we will find the value of the square root of :math:`2`.

Graphically, the equation looks like this:

.. image:: /figs/newton1.png
   :scale: 50 %

We are looking for the places where the curve intercepts the :math:`x`-axis.

Suppose we guess the answer.  For example, we might guess the next largest even square:  :math:`2^2 = 4`.  Guess :math:`g=2`.

If we could follow the tangent at the point :math:`(g,f(g))` down to the :math:`x`-axis, that would be a much better guess.

.. math::

    \frac{\Delta y}{\Delta x} = m = f'(g)
    
So we have

.. math::

    f'(g) = \frac{\Delta y}{\Delta x} = \frac{f(g) - 0}{g - x}

    g - x = \frac{f(g)}{f'(g)}
    
    x = g - \frac{f(g)}{f'(g)}

Our procedure will be:  choose a guess :math:`g`, compute :math:`f(g)` and :math:`f'(g)` and then substitute as above to get a better guess.  Eventually, our guesses should converge on the correct answer.

+++++++++++++
Iteration:  1
+++++++++++++

.. math::

    g = 2
    
    f(g) = g^2 - 2 = 2
    
    f'(g) = 2g = 4
    
    x = g - \frac{f(g)}{f'(g)} = 2 - \frac{2}{4} = 1.5

+++++++++++++
Iteration:  2
+++++++++++++

.. math::

    g = 1.5

    f(g) = g^2 - 2 = 0.25

    f'(g) = 2g = 3

    x = g - \frac{f(g)}{f'(g)} = 1.5 - \frac{0.25}{3} = 1.416666

+++++++++++++
Iteration:  3
+++++++++++++

.. math::

    g = 1.416666

    f(g) = g^2 - 2 = 0.006944

    f'(g) = 2g = 2.833333

    x = g - \frac{f(g)}{f'(g)} = 1.5 - \frac{0.25}{3} = 1.414215

The actual value is :math:`1.4142135623730951`, so round 3 is correct to five places.

Note:  there are *some* functions for which Newton's method does not work.


