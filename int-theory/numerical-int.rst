.. _numerical-int:

#####################
Numerical integration
#####################

It has been shown that some important integrals cannot be "solved" analytically.  For example, the normal distribution (with mean and standard deviation both equal to :math:`1`) is described by this probability density function:

.. math::

    f(x) = \frac{e^{-x^2/2}}{\sqrt{2 \pi}}

(for a derivation, see :ref:`here <gauss>`).

To find the expected value or probability that the value lies between bounds :math:`a` and :math:`b` we should compute:

.. math::

    \int_a^b f(x) \ dx

However, there is no function :math:`F(x)` such that :math:`F'(x) = f(x)`, so we cannot solve the equation in the normal way (by computing :math:`F(b) - F(a)`).

To compute the integral, we fall back on Riemann sums.  Divide the closed range :math:`[a,b]` into :math:`N` rectangles whose individual height is the value :math:`f(x)` somewhere in the rectangle, and then compute the sum of :math:`\Delta x \times f(x)` over the whole interval.  A simple approach uses rectangles of constant width (equal to :math:`b-a/N`).

Using Python:

`script.py`

.. sourcecode:: python

    from math import e, pi, sqrt

    def get_xvalues(a,b,N):
        dist = 1.0*b - 1.0*a
        dx = dist/N
        half = dx/2.0
        R = [(a + dx * n + half) for n in range(N)]
        return R, dx

    def integrate(a,b,f,N=100):
        '''integrate function f over [a,b]'''
        L, dx = get_xvalues(a,b,N)
        values = [f(x) for x in L]
        print sum(values) * dx

    def f(x):
        return x**2

    integrate(0,1,f)
    integrate(1,2,f)

    def g(x):
        exp = -0.5*x**2
        norm = sqrt(2*pi)
        return e**(exp) / norm

    for b in [2,4,6,8,10]:
        print str(b).rjust(2),
        integrate(-b,b,g)

The script generates this output:

.. sourcecode:: bash

    > python script.py 
    0.333325
    2.333325
     2 0.954514133023
     4 0.999936942329
     6 0.99999999807
     8 1.0
    10 1.0
    >

I hope the flow is clear.  The function `get_xvalues` generates a list of :math:`x`-values starting from the middle of the first step past :math:`a` and continuing to the last step just before :math:`b`.  `integrate` simply computes `f(x)` for each :math:`x`-value, sums all of those values, and adjusts for the width of the steps (rectangles).

We integrate :math:`f(x) = x^2` over the ranges :math:`[0,1]` and :math:`[1,2]` and obtain the expected results (:math:`1/3` and :math:`7/3`).

We also integrate the normal probability density function over ranges :math:`[-2,2]` to :math:`[-10,10]`.  With standard deviation equal to :math:`1`, we obtain the expected result that :math:`95 \%` of the density lies within two standard deviations of the mean.  Essentially all of the density lies within four standard deviations of the mean.

And finding that the total area equals :math:`1` confirms that the normalization factor :math:`1/\sqrt{2 \pi}` is correct.  That is, the value of the unnormalized integral is equal to :math:`\sqrt{2 \pi}`.

===========
Refinements
===========

Classically, the major improvement to be made to this algorithm is to make a more accurate estimation of the area for each small rectangle.  This is not so important with fast computers.  For example, with a million steps rather than 100, I obtain 

.. sourcecode:: bash

    > python script.py 
    0.333333333333
    2.33333333333
    >

for the first two integrations, in about two seconds.

In the calculation above I used the *midpoint rule*, where :math:`f(x)` is simply evaluated at the midpoint of the range.  The step size is computed and used to generate a list of values where each rectangle starts, then half the step is added to give the midpoint.  

If we think of :math:`a` and :math:`b` as the bounds for each small rectangle, then the average of :math:`a` and :math:`b` is the midpoint:

.. math::

    m = (a+b)/2

We evaluate :math:`f(m)`, the function at the midpoint, and then multiply by the width:

.. math::

    M = (b-a) \ f(m)

*Simpson's rule* is a more sophisticated approach that uses:

.. math::

    \frac{b-a}{6} \ [ \ f(a) + 4f(m) + f(b) \ ]

We sample once each from :math:`a` and :math:`b`, and four times from :math:`m`, and average those samples.

The *trapezoidal rule* is

.. math::

    T = \frac{b-a}{2} \ (f(a) + f(b))

Simpson's rule is really just a combination of the other two rules, namely, it is equal to :math:`(2M + T) / 3`.  It weights the value at each endpoint as :math:`1 \times` and then the midpoint as twice the combined values at the endpoints.

Essentially, Simpson fits a parabola to the points :math:`a,m,b` and then computes the area.  This is really Archimede's result (:ref:`quadrature <quadrature>`) in disguise.

Consider the parabola :math:`y = -x^2 + 1` between :math:`x=-1 \rightarrow 1` (the points where it crosses the :math:`x`-axis on its way down).  Our task is to find the correct :math:`y`-value to use as the average height of the function in this region.  Inverting the standard result for the area under :math:`y=x^2`, the area under this parabola is :math:`2/3` of the area above it.  The result we seek is :math:`2/3`.

So a quadratic approximation to the area samples four times at the vertex plus once each at :math:`x= \pm 1`.   We sample because we understand that the curve is probably not exactly quadratic.
