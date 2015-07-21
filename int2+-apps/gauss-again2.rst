.. _gauss-again2:

###########################
Gaussian distribution: more
###########################

Previously, we saw a derivation of the Gaussian (normal) distribution from first principles (:ref:`here <gauss>`):

.. math::

    p(x) = A e^{-x^2/2V}
    
This is the normal distribution with variance :math:`V` and standard deviation :math:`s^2 = V`.

For :math:`p(x)` to be a probability distribution the total area under the curve must be equal to :math:`1`.  

We adjust ("normalize") to get this result by finding the proper value of :math:`A` as the inverse of the integral:

.. math::

    \int_{-\infty}^{\infty} e^{-x^2/2V} \ dx
    
We will call this value (which is after all just a number), :math:`I`.

Now, no one has found a way to evaluate the integral analytically by finding :math:`F(x)` such that

.. math::

    F'(x) = e^{-x^2/2V}

Nevertheless, we can proceed in two ways.  One way is to perform :ref:`numerical integration <numerical-int>`.

If you do that (setting :math:`V=1`) you will find that:

.. math:: 

    \int_{-10}^{10} e^{-x^2/2} = 2.50662827463
    
(Essentially all the density is between :math:`-4` and :math:`4`, so we have gone way beyond that).

Now, :math:`2.5066` is not a familiar number.  Nevertheless (using Python to calculate) we see that:

>>> from math import pi, sqrt
>>> sqrt(2*pi)
2.5066282746310002
>>>

And this cannot be an accident!

It turns out there is also a way to find the area under the curve using calculus.  (The next section repeats what we did before :ref:`here <gauss-again>`, but we will extend it below).  

As we said, we have defined:

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2/2V} \ dx
    
The trick (admittedly a bit suspicious) is to look at the following expression:

.. math::

    I^2 = [ \ \int_{-\infty}^{\infty} e^{-x^2/2V} \ dx \ ] \ [ \  \int_{-\infty}^{\infty} e^{-y^2/2V} \ dy \ ]
    
where we have used both :math:`x` and :math:`y`, and we say that they are independent.  
    
There is some discussion on this point here:

http://math.stackexchange.com/questions/1312498/how-is-this-step-justified-into-calculating-gaussian-integral

https://en.wikipedia.org/wiki/Fubini%27s_theorem

Because of independence, we may combine the integrands and integrate over the plane in :math:`\mathbb{R}^2`, so

.. math::

    I^2 = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} e^{-x^2/2V} \ e^{-y^2/2V} \ dx \ dy

    = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} e^{-(x^2+y^2)/2V} \ dx \ dy

Now it's easy.  Because if we switch to polar coordinates:

.. math::

    = \int_{0}^{2 \pi} \int_{0}^{\infty} e^{-r^2/2V} r \ dr \ d\theta
    
we've picked up a factor that allows us to integrate:

.. math::

    = 2 \pi \ [ \ -V  e^{-r^2/2V}  \ ] \ \bigg |_{0}^{\infty}
    
    = 2 \pi V

So

.. math::
     
    I^2 = 2 \pi V
    
    I = \sqrt{2 \pi V}
    
    = \sqrt{2 \pi \sigma^2}
    
    = \sqrt{2 \pi} \sigma

and

.. math::

    p(x) = \frac{1}{\sqrt{2 \pi} \sigma} e^{-x^2/2\sigma^2}

This is the standard formula of the Gaussian.

In addition, centering :math:`x` by subtracting a constant (the mean) doesn't change anything.

+++++
Note:
+++++

In the following section, we will compute the volume of a two-dimensional Gaussian "bell" by both disks and slices (with equal variance in both :math:`x` and :math:`y`).  Thinking about this volume may allow you to see what the above manipulation is about.  What we have really done is to take a *surface* in :math:`\mathbb{R}^3` defined by:

.. math::

    z = e^{-(x^2 + y^2)/2}

and find the volume under the surface by integrating:

.. math::

    V = \int z \ dA

where the *shadow* of the surface, over which we integrate in :math:`\mathbb{R}^2` is the entire plane (:math:`x,y = -\infty \rightarrow \infty`).

.. math::

    \text{Volume} = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} e^{-(x^2 + y^2)/2V} \ dA

and our "trick" consists of a change of variable to polar coordinates.  The entire plane becomes

.. math::

    \text{Volume} = \int_0^{2 \pi} \int_{0}^{\infty} e^{-r^2/2V} \ r \ dr \ d \theta 

where we use that :math:`r^2 = x^2 + y^2` and pick up the factor of :math:`r` from the polar area element (see :ref:`here <polar-area>`).

The inner integral over :math:`r` gives:

.. math::

    -V  e^{-r^2/2V} \ \bigg |_0^{\infty}

which evaluates to :math:`V` at the lower bound.  Thus, it was essential that in switching to polar coordinates we have a lower bound of :math:`0` for :math:`r`.

We end up with just :math:`2 \pi V` for the entire volume.

It remains to relate the volume integral to the integral.  I'll leave that for the second part of the next section.  There it will become clear that this is the square of 

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2/2V} \ dx
    
    I^2 = 2 \pi V

=================
Alternative proof
=================

Here is another way of thinking about the calculation that arrives at the answer we have from above in a different way.  It's fun because it's different, and because it doesn't have that one step that caused trouble above.

http://www.math.uconn.edu/~kconrad/blurbs/analysis/gaussianintegral.pdf

Consider the "bell surface" or Gaussian surface formed by the (unnormalized) function.  For this section we will take :math:`V=1`.

.. math::

    z = e^{-(x^2 + y^2)/2}

It looks like this:

.. image:: /figs/gaussian-surface.png
   :scale: 50 %

It's a real bell!

We compute the volume under the surface in two ways.  The first way is by horizontal slices perpendicular to the :math:`z`-axis.

++++++++++
Horizontal
++++++++++

.. math::

    \int_0^b A(z) \ dz

We need an expression for the area of horizontal slices *as a function of the height* :math:`z`.  What we have now is the inverse function:

.. math::

    z = e^{-(x^2 + y^2)/2}

So let's do it:

.. math::

    x^2 + y^2 = -2 \ \ln z

The horizontal cross-sections (at :math:`z = c`, where :math:`c` is a constant), are circles of radius :math:`r`: where

.. math::

    r^2 = x^2 + y^2 = -2 \ \ln z

We will fix the upper bound as follows:  the maximum value of :math:`z` occurs when :math:`x=y=0` and the exponential is equal to :math:`1`, otherwise the value is less than :math:`1`, so we have that 

.. math::

    z = e^{-(x^2 + y^2)/2} = e^0 = 1

So finally, the integral we need to calculate starts with :math:`A = \pi r^2`:

.. math::

    A(z) = \pi \ (-2) \ \ln z

    V = -2 \pi \int_0^1 \ln z \ dz
    
Now (leaving the factor of :math:`-2 \pi` aside for now) that is just:

.. math::

    \int \ln z \ dz = z \ln z - z

which is easily verified by differentiating the result.

We need to evaluate this expression between the bounds we set above (:math:`z=0 \rightarrow 1`).

At the lower bound of :math:`z=0`, clearly the second term is zero.
  
The first term is :math:`z \ \ln z`.  To evaluate:

.. math::

    \lim_{z \rightarrow 0+}  z \ \ln z 

we use L'Hopital's :ref:`rule <LHopital>`.  

.. math::

    z \ \ln z = \frac{z}{1/\ln z}

As :math:`z \rightarrow 0+`, the numerator is just zero and the denominator is :math:`1/-\infty = 0` so by the rule, we compute the derivatives:

.. math::

    \frac{1}{1/(1/z)} = z

And this limit is equal to zero so we have just zero for the whole expression at the lower bound.

At the upper bound, the first term is zero and the second is equal to :math:`-1`.

Remembering the extra factor, we have finally just :math:`(-2 \pi)(-1) = 2 \pi`.

++++++++
Vertical
++++++++

The other way is vertical slices.  First, recall our definition:

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2/2} \ dx

(Again, :math:`I` is what we're looking for.  It is *just a number*).  So

.. math::

    z = e^{-(x^2 + y^2)/2}

If we take slices perpendicular to the :math:`x`-axis (with :math:`x =` constant for any particular slice), the area of each slice is

.. math::

    A(x) = \int_{-\infty}^{\infty} e^{-(x^2 + y^2)/2} \ dy

since :math:`x` is a constant we have

.. math::

    = e^{-x^2/2} \ \int_{-\infty}^{\infty} e^{-y^2/2} \ dy = e^{-x^2/2} \ I

Now we add up all the little slices to find the volume, which is

.. math::

    V =  \int_{-\infty}^{\infty} I e^{-x^2/2} \ dx

but :math:`I` is *just a number*, so

.. math::

    =  I \int_{-\infty}^{\infty} e^{-x^2/2} \ dx

    = I^2

Now we have two different expressions for the same volume, which must be equal to each other.  Thus:

.. math::

    2 \pi = I^2

    I = \sqrt{2 \pi}

There are eight other proofs in the reference given above.  I'd like to do one more.

==============
Gamma function
==============

The Gamma function is:

.. math::

    \Gamma(x) = \int_0^{\infty} t^{x-1} e^{-t} \ dt

A bit more about it :ref:`here <gamma>` and here:

https://en.wikipedia.org/wiki/Gamma_function

For integer :math:`n`

.. math::

    \Gamma(n) = (n-1)!

Here is one important property of the gamma function that is easily proved using integration by parts:

.. math::

    \Gamma (x+1) = x \Gamma(x)

So this function is like the factorial, but it generalizes to non-integer values of :math:`x`, and it's offset by :math:`1`.

A second property that I got from the reference above, but have to investigate in more detail is:

.. math::
    
    \frac{\Gamma(x) \Gamma(y)}{\Gamma (x+y)} = \int_0^1 t^{x-1}(1-t)^{y-1} \ dt

++++++++++++++++++
Trick with x = 1/2
++++++++++++++++++

In any case, using this last equation, set

.. math::

    x = y = \frac{1}{2}

then

.. math::

    [ \ \Gamma(\frac{1}{2}) \ ]^2 = \int_0^1 \frac{1}{\sqrt{t(1-t)}} \ dt

Now, from the standard gamma function definition:

.. math::

    \Gamma(x) = \int_0^{\infty} t^{x-1} e^{-t} \ dt
    
    \Gamma(\frac{1}{2}) = \int_0^{\infty} \frac{1}{\sqrt{t}} e^{-t} \ dt

Substitute :math:`\sqrt{t} = x`, so then :math:`t = x^2` and :math:`dt = 2 x \ dx`, and

.. math::

    \Gamma(\frac{1}{2}) = \int_0^{\infty} \frac{1}{x} e^{-x^2} \ 2 x \ dx
    
    = 2 \int_0^{\infty} e^{-x^2} \ dx

++++++++++
Defining J
++++++++++

This integral is related to what we called :math:`I` before.  

Recall:

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2/2} \ dx

Two differences are the bounds on the integral and the factor of :math:`1/2` in the exponent.  Define 

.. math::

    J = \int_{-\infty}^{\infty} e^{-x^2} \ dx

And since :math:`J` is an *even* function, we have that

.. math::

    J = 2 \int_{0}^{\infty} e^{-x^2} \ dx

which is exactly what we had above.  Therefore:

.. math::

    \Gamma(\frac{1}{2}) = J
    
    [ \ \Gamma(\frac{1}{2}) \ ]^2 = J^2

So then

.. math::
    
    J^2 = \int_0^1 \frac{1}{\sqrt{t(1-t)}} \ dt

+++++++++++++++
Second integral
+++++++++++++++

To do this last integral, substitute:

.. math::

    t = \sin^2 \theta
    
    dt = 2 \sin \theta \cos \theta \ d \theta
    
    \sqrt{t(1-t)} = \sqrt{t} \ \sqrt{1-t} = \sin \theta \cos \theta
    
So the integral is simply :math:`2 \theta` (!!!)  What are the bounds?

.. math::

    t = 0 \Rightarrow \sin^2 \theta = 0 \Rightarrow \theta = 0
    
    t = 1 \Rightarrow \sin^2 \theta = 1 \Rightarrow \theta = \frac{\pi}{2}
    
The final value is just :math:`\pi`.  So:

.. math::

    J^2 = \int_0^1 \frac{1}{\sqrt{t(1-t)}} \ dt = \pi
        
    J = \sqrt{\pi}

++++++++++++++++
Relating I and J
++++++++++++++++

To finish up, we need to determine the relationship between:

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2/2} \ dx

and

.. math::
    
    J = \int_{-\infty}^{\infty} e^{-x^2} \ dx

We just do a simple substitution:

.. math::

    u = \frac{x}{\sqrt{2}}
    
    \sqrt{2} \ du = dx
    
    I = \int_{-\infty}^{\infty} e^{-u^2} \ \sqrt{2} \ du
    
    = \sqrt{2} \ J

Hence:

.. math::

    I = \sqrt{2} \ J = \sqrt{2} \ \sqrt{\pi} = \sqrt{2 \pi}

Note:  in the reference they define :math:`J` as the integral from :math:`0 \rightarrow \infty`.  Since :math:`J` is also an even function, this :math:`J` is twice theirs.


    