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
    
The fancy-pants math guys go to a lot of trouble to prove that the last step is OK, and it is OK, *even though the derivative dy/dx is not a quotient but a limit*.  

Here is a case where we would rather not isolate :math:`y`.

.. math::

    x^2 + y^2 = R^2
    
Why not handle this quickly?  What I do is to imagine that :math:`x` is a function of some variable :math:`t` such that :math:`x = t` and then just differentiate with respect to :math:`t`:

.. math::

    \frac{d}{dt} x^2 + y^2 = \frac{d}{dt} R^2 = 0
    
    2 x \frac{dx}{dt} + 2 y \frac{dy}{dt} = 0
    
Now multiply by :math:`1/2` *and* by :math:`dt`:

.. math::

    x \ dx + y \ dy = 0
    
    y \  dy = - x \ dx
    
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
    
which is the same answer.

=================
Inverse functions
=================

We can also approach this subject from consideration of inverse functions.  For example, :math:`f(x) = x^2` and :math:`g(x) = x^{1/2}` are such functions, because

.. math::

    f(g(x)) = x

although one must always think about taking only the positive square root.  Now, you know that inverse functions have slopes that are inverses as well.  In other words, the graphs of two inverse` functions are reflected across the symmetry axis :math:`y=x`.

Here are the exponential :math:`e^x` and the natural logarithm :math:`\ln x`.

.. image:: /figs/log2.png
   :scale: 50 %

Going back to :math:`f(x) = x^2` and :math:`g(x) = x^{1/2}`:

At :math:`x = 2`:

.. math::

    x^{1/2} = \sqrt{2}

The slope of

.. math::

    g(x) = x^{1/2}
    
is

.. math::

    g'(x) = \frac{1}{2 \sqrt{x}}

At :math:`x = \sqrt{2}` the value of 

.. math::

    f(x) = x^2 = 2

and the slope is

.. math::

    f'(x) = 2x
    
    = 2 \sqrt{2}

The slopes are inverses.  It is easy to see that the same thing is true for :math:`x^3` and :math:`x^{1/3}` etc.

Suppose we start with :math:`y = \sqrt{x}` and then write:

.. math::

    x = y^2

    \frac{d}{dx} x = \frac{d}{dx} y^2 

By the chain rule:

.. math::

    1 = \frac{d}{dx} \ y^2 
    
    = 2 y y'

So therefore:

.. math::

    y' = \frac{1}{2y}
    
    = \frac{1}{2 \sqrt{x}}

As Koblitz says:

	There is one little difficulty here. To use the chain rule to compute :math:`d/dx(y^2) = 2yy'` we need to know that the function :math:`y` has a derivative. All we have shown is that if it has a derivative then that derivative must be :math:`x^−{1/2}/2`. When using this method we will always have to assume that the desired derivative exists, but fortunately this is a safe assumption for most such problems.

+++++++
Example
+++++++

Here is a good example, although it requires knowledge of the exponential function (:ref:`here <exp-diff>`)

.. math::

    y = e^{xy}

There is no way to solve for :math:`y`.  So

.. math::

    \frac{d}{dx} \ y = \frac{d}{dx} \ e^{xy}
    
The left-hand side is :math:`y'`.  For the right-hand side, let :math:`u = xy`, then

.. math::

    \frac{d}{dx} \ e^{u} = e^{u} \frac{du}{dx}

    \frac{du}{dx} = \frac{d}{dx} xy = x'y + xy' = y + xy'

So the right-hand side is:

.. math::

    (y + xy') \ e^{xy}

Altogether, we have:

.. math::

    y' = (y + xy') \ e^{xy}

    =  (e^{xy} + xy') \ e^{xy}
    
and we can solve for :math:`y'`.  According to Koblitz, one can *always* solve for :math:`y'` when using this method.
