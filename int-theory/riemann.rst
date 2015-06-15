.. _riemann:

############
Riemann Sums
############

The standard introduction to the technique of integration is to consider the problem of calculating the area bounded by a curve.

Our first example is to calculate the area under the curve :math:`f(x)=x^2`.  The plan is to add up the areas of many small rectangles to form the sum. Although any rectangle can only be an approximation to a curved surface, if we use many skinny rectangles the approximation will be very good, and in the limit as we use an infinite number of rectangles, it will be exactly right.

We start with :math:`x^2`.  It is the simplest power curve, and we actually know the answer due to work by Archimedes, called the :ref:`quadrature`.

Consider the region bounded by the :math:`x`-axis, the :math:`y`-axis, the line :math:`x=1`, and the curve :math:`y=x^2`.  

We partition the region on the :math:`x`-axis between :math:`x=0` and :math:`x=1` into :math:`N` segments.  Each segment will contain a tall, thin rectangle that extends from the :math:`x`-axis up to the curve.  

One question is precisely where to draw the tops of the rectangles, since the height might be set equal to the value of the function at *any* point along the top edge.

Here is a figure that illustrates the basic idea.  We have divided the region between :math:`0` and :math:`1` into :math:`10` segments, so the width of each segment is :math:`0.1`.  In the left panel, the blue rectangle shown is the sixth segment;  its left and right bounds are :math:`x = 0.5` and :math:`x = 0.6`.  The height is :math:`x^2 = 0.6^2 = 0.36`.  The right panel is the same, except the height corresponds to the value at the left-hand bound :math:`x^2 = 0.5^2`.

.. image:: /figs/riemann.png
       :scale: 25%

We compute the area (using the first set of rectangles) as

.. math::

    A = 0.1 (0.1^2 + 0.2^2 + 0.3^2 + 0.4^2 + 0.5^2 + 0.6^2 + 0.7^2 + 0.8^2 + 0.9^2 + 1.0^2)
    
    = 0.1 (0.01 + 0.04 + 0.09 + 0.16 + 0.25 + 0.36 + 0.49 + 0.64 + 0.81 + 1.0)
    
    = 0.1 (3.85) = 0.385

This is obviously an over-estimate of the area (as it will be for a function that increases over the interval), but the trick is that *as the number of rectangles becomes very large*, the result will converge to the exact area we want.

If we divide the region into :math:`N` intervals, each interval has width :math:`1/N`.  The height of the first interval is :math:`(1/N)^2` and that of the :math:`kth` interval is :math:`(k/N)^2`.  The total area is:

.. math::

    \sum_{k=1}^N (\frac{k}{N})^2 \times \frac{1}{N} 

Since :math:`N` is a constant, it can be pulled out from the summation:

.. math::

    \frac{1}{N^3} \sum_{k=1}^N k^2

So now we need an expression for the sum of the squares of the first :math:`N` integers.  :ref:`sum_n^2`

.. math::

    \sum_{k=1}^N k^2 = \frac{N(N+1)}{2} \ \frac{2N + 1}{3}

We plug that expression into the Riemann Sum:

.. math::

    = \frac{1}{N^3} \frac{N(N+1)}{2} \ \frac{2N + 1}{3}

Each of the terms in :math:`N(N+1)(2N+1)` is grouped with one of the :math:`N`'s in the denominator at the left

.. math::

    = \frac{1}{6} \ \frac{N}{N} \ \frac{(N+1)}{N} \ \frac{(2N + 1)}{N}

In the limit as :math:`N` gets very large.

.. math::

    \lim_{N \rightarrow \infty}\frac{N}{N} = 1
    
    \lim_{N \rightarrow \infty} \frac{N+1}{N} = \lim_{N \rightarrow \infty} 1 + \frac{1}{N} = 1

    \lim_{N \rightarrow \infty} \frac{2N + 1}{N} = \lim_{N \rightarrow \infty} 2 + \frac{1}{N} = 2

Thus, the final answer is :math:`1/3`, which agrees with Pythagoras.