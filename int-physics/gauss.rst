.. _gauss:

###################
Normal distribution
###################

I want to follow a derivation of the Gaussian distribution from first principles.  

http://www.ncssm.edu/courses/math/Talks/PDFS/normal.pdf

The argument is originally due to Sir John F. W. Herschel.

https://en.wikipedia.org/wiki/Normal_distribution

Imagine that you are throwing darts at the origin of the :math:`x,y`- plane. Under perfect conditions, you would probably hit target dead  every time. 

However, conditions aren't perfect. The wind is gusting from all directions, the music is loud, there are other distractions. As a result, small random errors creep in and the pattern over time looks like this:

.. image:: /figs/gauss1.png
   :scale: 50 %

Now, we assume that there is some *function* for the probability that a dart will land in the interval between :math:`x` and :math:`x + \Delta x`, presently that function is unknown and what we seek. Obviously, the probability depends on :math:`x`, with a maximum at :math:`x = 0` and then finally decreasing to zero as :math:`x` gets large. 

We designate the function as a probability density function :math:`p(x)` and evaluate the density over the interval to get the probability that the dart lands in the interval:

.. math::

   P = p(x) \Delta x

.. image:: /figs/gauss2.png
   :scale: 50 %

Now consider a small rectangular area of size :math:`\Delta x \Delta y`. If the errors in perpendicular directions are independent, then we expect that

.. math::

    p(x) = p(y)

and we can obtain the probability that a dart will land in the small rectangle bounded by :math:`x`, :math:`y` and :math:`x + \Delta x`, :math:`y + \Delta y` as:

.. math::

    P = p(x) \Delta x \ p(y) \Delta y

Furthermore, if we assume that the errors do not depend on the orientation of the coordinate system, then the probability is a function only of :math:`r`, the radial distance from the origin, so we can write

.. math::

    P = g(r) \Delta x \ \Delta y

    g(r) \Delta x \ \Delta y = p(x) \Delta x \ p(y) \Delta y
    
    g(r) = p(x)  \ p(y)

This assumption of rotational independence leads directly to the answer, as you will see. 

:math:`\theta` is defined as usual, as the angle that the ray to a point makes with the positive :math:`x`-axis.  Since :math:`g(r)` depends only on :math:`r`, and since :math:`r` does not depend on the angle :math:`\theta` (but :math:`x` and :math:`y` do), we can take the partial derivative with respect to :math:`\theta` of :math:`g(r)` and set it equal to zero, so that:

.. math::

    \frac{\partial g(r)}{\partial \theta} = p(x) \frac{\partial p(y)}{\partial \theta}  + p(y) \frac{\partial p(x)}{\partial \theta} = 0
    
We used the chain rule here, as well.

If partial derivatives are new, there is a brief introduction :ref:`here <partial-diff>`.

What are these derivatives?  As usual

.. math::

    x = r \cos \theta

    \frac{\partial x}{\partial \theta} = - r \sin \theta = - y

(treating :math:`r` as a constant).  And:

.. math::

    y = r \sin \theta

    \frac{\partial y}{\partial \theta} = r \cos \theta = x

So
    
.. math::

    \frac{\partial p(x)}{\partial \theta} = \frac{\partial p(x)}{\partial x} \frac{\partial x}{\partial \theta} = p'(x)(-y)

And
    
.. math::

    \frac{\partial p(y)}{\partial \theta} = \frac{\partial p(y)}{\partial y} \frac{\partial y}{\partial \theta} = p'(y)(x)
    
To be clear, the last statement is :math:`p'(y)(x)`:  we multiply the derivative of :math:`p` with respect to :math:`y` times the value of :math:`x`...
    
Putting it all together, we get

.. math::

    \frac{\partial g(r)}{\partial \theta} = p(x) \frac{\partial p(y)}{\partial \theta}  + p(y) \frac{\partial p(x)}{\partial \theta} = 0

    p(x)p'(y)(x) + p(y)p'(x)(-y) = 0
    
Rearranging:

.. math::

    \frac{p'(x)}{p(x)(x)} = \frac{p'(y)}{p(y)(y)} = k
    
    p'(x) = k p(x) (x)

What function do we know that has itself as the derivative (with an extra factor of :math:`x`)?

.. math::

    p(x) = A e^{kx^2/2}

    p'(x) = Akx e^{kx^2/2} = kx p(x)

Since we assume that large errors are less likely than small ones, :math:`k < 0`, so we can define another constant :math:`V = - 1/k` and

.. math::

    p(x) = A e^{-x^2/2V}
    
This is the normal distribution with variance :math:`V`.

It is amazing how far we got with this argument! We assumed:

- the errors do not depend on the orientation of the coordinate system.

- errors in perpendicular directions are independent. This means that being too high doesn't alter the probability of being off to the right.

- large errors are less likely than small errors.

Notice that although we started talking about a probability distribution in two dimensions, the function we end up with is for one dimension.

James Clerk Maxwell used the same argument in three dimensions to derive his expression for the distribution of molecular velocities in a gas.

===============
Some properties
===============

.. image:: /figs/gauss3.png
   :scale: 50 %

The plot of the normal or Gaussian distribution is usually divided into sections according to :math:`x = \pm n` standard deviations.  It's an interesting fact that the first standard deviation corresponds to the inflection point of the curve.  At that point the second derivative of the function is equal to zero.  The curve has been "bending" down, and will soon be bending up, but at the moment is at an inflection point.  The rate of change of the slope of :math:`f(x)` is equal to zero.

At the end of the last section we wrote:

.. math::

    p(x) = A e^{-x^2/2V}

Now we will call the Gaussian :math:`G(x)`.  The complete form of this exponential function has two additional terms which are the mean (:math:`\mu`) and the standard deviation (:math:`\sigma`), where the latter can be expressed equivalently in terms of the variance (:math:`\sigma^2 = V`).  

The constant in front is a normalizing constant that makes the total area under the curve equal to :math:`1`.  We will determine that constant by calculating the area under the un-normalized function.  Its value will turn out to be:  :math:`\sqrt{2 \pi} \sigma`.  So now we have:
    
.. math::

    G(x) = \frac{1}{\sigma \sqrt{2 \pi}} \ exp \ \{ \ -\frac{1}{2} (\frac{x - \mu}{\sigma} )^2\ \}
    
When the exponent is complicated, it is frequently written on the same line with the base :math:`e`, which is then re-labeled as :math:`exp`, as shown.

Our goal is to show that the inflection point comes at one standard deviation above and below the mean.

Let

.. math::

    v(x) = -\frac{1}{2} (\frac{x - \mu}{\sigma} )^2

    k = \sigma \sqrt{2 \pi}

    G(x) = \frac{1}{k} \ e^v

    G'(x) = \frac{1}{k} \  v' e^v

    v' = \frac{dv}{dx} = -\frac{1}{\sigma} (\frac{x - \mu}{\sigma})

    G'(x) = - \frac{1}{k} \  \frac{1}{\sigma} (\frac{x - \mu}{\sigma}) e^v

    G''(x) = \frac{1}{k} \ (-\frac{1}{\sigma}) (\frac{x - \mu}{\sigma}) (-\frac{1}{\sigma}) (\frac{x - \mu}{\sigma}) e^v + k (\frac{1}{\sigma}) e^v

    G''(x) = \frac{1}{k} \ (\frac{1}{\sigma^2}) \ [(\frac{x - \mu}{\sigma})^2 - 1] \ e^v

We want

.. math::

    G''(x) = 0

where

.. math::

    e^v = exp \ \{ \ -\frac{1}{2} (\frac{x - \mu}{\sigma} )^2\ \}

In the limit as :math:`x \to \pm \infty`, the term :math:`e^v` approaches :math:`0`, but those are not the solutions we want.  So we need

.. math::

    (\frac{x - \mu}{\sigma})^2 - 1 = 0

    (x-\mu)^2 = \sigma^2

    x = \mu \pm \sigma

The second derivative required some bookkeeping, but it simplified in the end.

What about the constant in front?  As we said, it is there to make the sum of the area under the probability distribution, the cumulative distribution function, equal :math:`1`.  One way to solve the integral is to compute it numerically.  If you do that for :math:`e^v` as defined above (no leading constant :math:`\frac{1}{k} \ `), you find that the value is :math:`k`.  So this is a "normalizing constant", to make the whole thing equal to :math:`1`.

There is a fancy "analytical" argument by which it can be shown that the integral over the entire range is equal to:

.. math::

    \int_{-\infty}^{+\infty} \ e^{-x^2/2} \ dx = \sqrt{2 \pi}

but it requires a double integral and some other tricks and so is beyond us for the moment.

:ref:`Here <numerical-int>` I confirm that result by numerical integration.  Integration is our next big topic.