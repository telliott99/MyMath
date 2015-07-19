.. _gauss-again:

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

There is also a way to find the area under the curve using calculus.  Let

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

Consider the "bell surface" or Gaussian surface formed by

.. math::

    z = e^{-(x^2 + y^2)/2}

It looks like this:

.. image:: /figs/gaussian-surface.png
   :scale: 50 %

We will compute the volume under the surface in two ways.  The first way is by horizontal slices perpendicular to the z-axis

.. math::

    \int_0^1 A(z) \ dz

We need to find :math:`r^2(z)` which is also :math:`x^2(z)`.  At height :math:`z` (and with :math:`y = 0`), then

.. math::

    z = e^{-x^2/2}

    x^2 = -2 \ ln z

So

.. math::

    A(z) = \pi (-2) \ ln z

    V = \int_0^1 (-2) \pi \ln z = - 2 \pi (z \ln z - z)

    = 2 \pi
  
There is one other term.  What is

.. math::

    \lim_{z -> 0+}  z \ \ln z 

By L'Hopital's rule it is zero so we have just :math:`2 \pi`.

The other way is vertical slices.  First, define

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2/2} \ dx

(:math:`I` is what we're looking for).  So again

.. math::

    z = e^{-(x^2 + y^2)/2}

The area of each slice is (with :math:`x =` const)

.. math::

    A(x) = \int_{-\infty}^{\infty} e^{-(x^2 + y^2)/2} \ dy

since :math:`x` is a constant we have

.. math::

    = e^{-x^2/2} \ \int_{-\infty}^{\infty} e^{-y^2/2} \ dy

the integral is

.. math::

    A(x) = I e^{-x^2/2}

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

