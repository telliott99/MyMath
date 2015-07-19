.. _gauss-again2:

###########################
Gaussian distribution: more
###########################

Back :ref:`here <gauss>`, we saw a derivation of the Gaussian (normal) distribution from first principles:

.. math::

    p(x) = A e^{-x^2/2V}
    
This is the normal distribution with variance :math:`V`.

For this to be a probability distribution the total area under the curve must add up to :math:`1`.  We adjust to get this result by finding the proper value of :math:`A`.  

There isn't a way to evaluate this integral analytically to find :math:`F(x)` such that

.. math::

    F'(x) = e^{-x^2/2V}

Nevertheless, we can proceed in two ways.  One way is to perform :ref:`numerical integration <numerical-int>`.

If you do this you will find that:

.. math:: 

    \int_{-10}^{10} e^{-x^2/2} = 2.50662827463

which is not a familiar number.  Nevertheless

.. math::

    \sqrt{2 \pi} = 2.50662827463

There is also a way to find the area under the curve using calculus.  (This part repeats what we did before :ref:`here <gauss-again>`, but we will extend it below).  

Let

.. math::

    A = \frac{1}{K} 
    
and

.. math::

    K = \int_{-\infty}^{\infty} e^{-x^2/2V} \ dx

Then :math:`p(x)` will be a normalized probability density.

The trick (admittedly a bit suspicious) is to say that

.. math::

    K^2 = [ \ \int_{0}^{\infty} e^{-x^2/2V} \ dx \ ] \ [ \  \int_{0}^{\infty} e^{-y^2/2V} \ dy \ ]
    
where :math:`x` and :math:`y` are independent.  
    
There is some discussion on this point:

http://math.stackexchange.com/questions/1312498/how-is-this-step-justified-into-calculating-gaussian-integral

https://en.wikipedia.org/wiki/Fubini%27s_theorem

Because of independence, we may combine the integrands so

.. math::

    = \int_{0}^{\infty} \int_{0}^{\infty} e^{-x^2/2V} \ e^{-y^2/2V} \ dx \ dy

    = \int_{0}^{\infty} \int_{0}^{\infty} e^{-(x^2+y^2)/2V} \ dx \ dy

Now it's easy.  Just switch to polar coordinates:

.. math::

    = \int_{0}^{2 \pi} \int_{0}^{\infty} e^{-r^2/2V} r \ dr \ d\theta

So

.. math::

    = 2 \pi \ [ \ -V  e^{-r^2/2V}  \ ] \ \bigg |_{0}^{\infty}
    
    = 2 \pi V

Since

.. math::

    K^2 = 2 \pi V
    
    K = \sqrt{2 \pi V}

where :math:`V = \sigma^2` (the square of the standard deviation).  Hence

.. math::

    K = \sqrt{2 \pi} \sigma

and

.. math::

    p(x) = \frac{1}{\sqrt{2 \pi} \sigma} e^{-x^2/2\sigma^2}

Centering :math:`x` by subtracting a constant (the mean) doesn't change anything.

#################
Alternative proof
#################

Here is another way of thinking about it that justifies what we did above by doing it with a twist:

http://www.math.uconn.edu/~kconrad/blurbs/analysis/gaussianintegral.pdf

Consider the "bell surface" or Gaussian surface formed by the (unnormalized) function:

.. math::

    z = e^{-(x^2 + y^2)/2}

It looks like this:

.. image:: /figs/gaussian-surface.png
   :scale: 50 %

It looks like a real bell!

We will compute the volume under the surface in two ways.  The first way is by horizontal slices perpendicular to the :math:`z`-axis.

==========
Horizontal
==========

.. math::

    \int_0^b A(z) \ dz

We need to find area of horizontal slices *as a function of the height* :math:`z`.  What we have is the inverse function:

.. math::

    z = e^{-(x^2 + y^2)/2}

    x^2 + y^2 = -2 \ \ln z

The cross-sections are circles of radius :math:`r`: where

.. math::

    r^2 = x^2 + y^2 = -2 \ \ln z

We find the upper bound as follows:  the maximum value of :math:`z` occurs when :math:`x=y=0` so we have that 

.. math::

    z = e^{-(x^2 + y^2)/2} = e^0 = 1

So

.. math::

    A(z) = \pi (-2) \ \ln z

    V = -2 \pi \int_0^1 \ln z \ dz
    
Now the integral is:

.. math::

    \int \ln z \ dz = z \ln z - z

which is easily verified by differentiating the result.  Remembering the extra factor, we have:

.. math::

    = - 2 \pi (z \ln z - z)

We need to evaluate this between the bounds (:math:`z=0 \rightarrow 1`).

At the lower bound of :math:`z=0`, clearly the second term is zero.
  
The first term is :math:`z \ \ln z`.  To evaluate:

.. math::

    \lim_{z \rightarrow 0+}  z \ \ln z 

we use L'Hopital's :ref:`rule <LHopital>`.  The result is zero so we have just zero for the whole thing at the lower bound.

At the upper bound, the first term is zero and the second is equal to :math:`-1` so we have finally just :math:`(-2 \pi)(-1) = 2 \pi`.

========
Vertical
========

The other way is vertical slices.  First, define

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2/2} \ dx

(:math:`I` is what we're looking for).  So again

.. math::

    z = e^{-(x^2 + y^2)/2}

If we take slices perpendicular to the :math:`x`-axis (with :math:`x =` const), the area of each slice is

.. math::

    A(x) = \int_{-\infty}^{\infty} e^{-(x^2 + y^2)/2} \ dy

since :math:`x` is a constant we have

.. math::

    = e^{-x^2/2} \ \int_{-\infty}^{\infty} e^{-y^2/2} \ dy = I e^{-x^2/2}

Now we need the volume, which is

.. math::

    V =  \int_{-\infty}^{\infty} I e^{-x^2/2} \ dx

but :math:`I` is a constant, so

.. math::

    =  I \int_{-\infty}^{\infty} e^{-x^2/2} \ dx

    = I^2

So we have that:

.. math::

    2 \pi = I^2

    I = \sqrt{2 \pi}

