.. _taylor:

#############
Taylor Series
#############

Some functions that arise in applications (like physics) can be difficult to handle.  They may be hard to evaluate the value of :math:`f(x)` at :math:`x=a`, or they may be a pain to integrate.  Thus, we seek a way of constructing functions that approximate the value of a given function.  In particular, we seek polynomial functions of the form:

.. math::

    g(x) = c_0 + c_1 x + c_2 x^2 + c_3 x^3 + \dots

Suppose we start work in the region near :math:`x=0`.  There, we want to match the value of the function :math:`f(x)` at :math:`x=0` which is:

.. math::

    f(0) = c_0 + c_1 x + c_2 x^2 + c_3 x^3 + \dots
    
    f(0) = c_0

The next step is to make the tangent to the curve :math:`g(x)` equal to the tangent to the curve :math:`f(x)` at :math:`x=0`.  We do this by making the first derivatives match:

.. math::

    g'(x) = c_1 + (2)c_2 x + (3)c_3 x^2 + \dots
    
    f'(0) = c_1

We also want the curvature to be the same, so we we make the second derivatives match:

.. math::

    g''(x) = (2)c_2 + (2)(3) c_3 x + \dots
    
    f''(0) = 2 c_2

    c_2 = \frac{f''(0)}{2}

When we continue to the third derivative, notice that we pick up a factor of :math:`2 \times 3 = 3!`, so the general formula for the coefficients is

.. math::

    c_n = \frac{f^n(0)}{n!}

(where :math:`f(n)` is the nth derivative of :math:`f`), and the function :math:`g(x)` is

.. math::

    g(x) =  \sum_0^{\infty} \frac{f^n(0)}{n!} x^n

We take as many terms as we need in order to have a good approximation.

+++++++
Example
+++++++

Consider :math:`f(x) = \sin x`.  The coefficients are:

.. math::

    c_0 = f(0) = \sin 0 = 0
    
    c_1 = f'(0) = \cos 0 = 1
    
    c_2 = f''(0) = - \sin 0 = 0
    
    c_3 = f'''(0) = - \cos 0 = -1

and then it repeats.  Combining with the powers of :math:`x` we obtain

.. math::

    \sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!}

The *small angle* approximation for :math:`\sin x` equals :math:`x`, when :math:`x` is close to :math:`0`.

Here is a comparison plot of the sine function versus various series.  The curve in purple ("plum") corresponds to the equation just above.  It matches the sine very well for an entire period of :math:`\pi`.

.. image:: /figs/taylor.png
   :scale: 50 %


The equivalent series for cosine is:

.. math::

    \cos x = 1 - \frac{x^2}{2!} + \frac{x^2}{2!} - \frac{x^2}{2!}

This approximation for :math:`x \approx 0` is called the Maclaurin series.

.. math::

    g(x) = \sum_{n=0}^{n=\infty} \frac{f^n(0)}{n!} (x)^n

The general approach for :math:`x \approx a` is the Taylor series.  Here is the formula:

.. math::

    g(x) = \sum_{n=0}^{n=\infty} \frac{f^n(a)}{n!} (x-a)^n

=================
Professor Shankar
=================

Here is an outline of the introduction to Taylor series from Dr. Shankar.

Suppose we have a function :math:`f(x)`, but 

    "imagine that you don't have access to the whole function.  You cannot see the whole thing.  You can only zero-in on a tiny region."
    
around :math:`f(0)`, where you know the value.  So the question is, what do we guess the function will do near :math:`f(0)`?  The first approximation is that

.. math::

    f(x) \approx f(0)

We really can't say anything more.  But now suppose we know the slope of the function at :math:`0`, :math:`f'(0)`.  Then, since :math:`\Delta y = f'(0) \Delta x = f'(0) x`, we can get a better approximation as

.. math::

    f(x) \approx f(0) + f'(0)\ x + \dots

For most functions, there will be more terms.  If :math:`f` is not a linear function, then the slope won't be constant.  So 

    "the rate of change itself has a rate of change .. the second derivative."  
    
The term we are going to add is

.. math::

    f''(0)\ \frac{x^2}{2}

so

.. math::

    f(x) \approx f(0) + f'(0)\ x + f''(0)\ \frac{x^2}{2}  + \dots

A simple way to see why we have :math:`x^2/2` is to take derivatives on both sides.  The terms like :math:`f'(0)` and :math:`f''(0)` are constants, they have been evaluated at :math:`x=0`. So the first derivative is

.. math::

    f'(x) \approx  f'(0) + f''(0)\ x  + \dots

We evaluate at :math:`x=0` and the term :math:`f''(0)\ x` goes away because of the :math:`0` multiplying the constant :math:`f''(0)`.  So we have just

.. math::

    f'(x) \approx  f'(0) 

and that matches. Now take the second derivative

.. math::

    f''(x) \approx  f''(0)

and that matches too.  We can see a pattern here.  The next term is

.. math::

    f(x) \approx f(0) + f'(0)\ x + f''(0)\ \frac{x^2}{2!}  + f'''(0)\ \frac{x^3}{3!} + \dots

You might not be expecting the factorial which snuck in there.  But if you go back to the exercise above, where we evaluated derivatives, you can see why it works.  When we take the first derivative 

.. math::

    \frac{d}{dx} (f'''(0)\ \frac{x^3}{3!}) =  f'''(0)\ \frac{x^2}{2!}

the :math:`3` comes down from the power and then turns :math:`3!` in the denominator into :math:`2!`.  The next derivative will bring down the :math:`2`.  So everything cancels properly.  If you like :math:`\Sigma` notation, we can write

.. math::

    f(x) = \sum_{n=0}^{\infty} f^n(0) \frac{x^n}{n!}

with the understanding that :math:`0! = 1`.  The approximation is better the closer :math:`x` is to :math:`0`, and the more terms the better as well.  There is one final wrinkle to this derivation.  The  series can be modified deal with :math:`x` near any value :math:`a`, not just near :math:`0`.  The modification is

.. math::

    f(x) = \sum_{n=0}^{\infty} f^n(a) \frac{(x-a)^n}{n!}

The series near :math:`a=0` is known as the Maclaurin series.

+++++++
Example
+++++++

The first example is

.. math::

    f(x) = \frac{1}{1-x}

We know the answer to this.

.. math::

    \frac{1}{1-x} = 1 + x + x^2 + x^3
    
Proof:

.. math::

    1 = (1-x)(1 + x + x^2 + x^3)

Multiplying by :math:`1`, the second term :math:`x` is matched by :math:`-x` from the first term in the multiplication by :math:`-x`, and so on.  The whole thing vanishes, leaving just :math:`1`.

We want to evaluate :math:`f(x)` near :math:`0`, let's say, at :math:`x=0.1`.  The correct value of the function is

.. math::

    f(x) = \frac{1}{0.9} = 1.11111 \dots

.. math::

Let's try to approximate using the series.  We need derivatives

.. math::

    f(x) = \frac{1}{1-x}

    f'(x) = \frac{1}{(1-x)^2} = (1-x)^{-2}

    f'(0) = 1

so the linear approximation is

.. math::

    f(x) \approx 1 + 1x = 1.1

For the next term we obtain

.. math::

    f''(x) = 2(1-x)^{-3}

    f''(0)\ \frac{x^2}{2} = x^2 = 0.01

And I think we can see where this one is going.

Another very useful series is the binomial.

.. math::

    f(x) = (1 + x)^n

    f(0) = 1

    f'(0) = n(1 + x)^{n-1} = n
    
    f''(0) = n(n-1)(1 + x)^{n-2} = n(n-1)

So the series is

.. math::

    (1 + x)^n \approx 1 + nx + n(n-1) \frac{x^2}{2}

A nice application is relativistic energy

.. math::

    E = mc^2 f

    f =  1/\sqrt{1-\frac{v^2}{c^2}}

This is, in disguise, a binomial with :math:`n=-1/2` and :math:`x=-v^2/c^2` so the expansion is

.. math::

    f  \approx 1 + nx = 1 + \frac{v^2}{2c^2}

so the energy is 

.. math::

    E \approx mc^2 (1 + \frac{v^2}{2c^2} )

And we see that the second term is just the kinetic energy, :math:`mv^2/2`.

+++++++++++++
More examples
+++++++++++++

Let's take a look at :math:`e^x`.  The nice thing about :math:`e^x` is the first derivative, in fact all the derivatives, are just :math:`e^x`, and since we're evaluating them at :math:`0`, all those factors become :math:`1`.  So the series is just

.. math::

    e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots

Let's try sine and cosine.  Cosine first

.. math::

    f'(0) = -\sin(x) \bigg |_{x=0} = 0

    f''(0) = -\cos(x) \bigg |_{x=0} = -1

    f'''(0) = \sin(x) \bigg |_{x=0} = 0

    f''''(0) = \cos(x) \bigg |_{x=0} = 1

So the pattern is, every other term, with alternating signs.

.. math::

    \cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} + \dots

The sine function loses the first term (because :math:`\sin 0 = 0`), then we have the same pattern of every other term and alternating sign.

.. math::

    \sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} + \dots

Finally, we'll sneak in an oddball.  Suppose we consider

.. math::

    f(x) = e^{ix}

where :math:`i = \sqrt{-1}`.  Let's just follow the rules and see where we get to.  First of all, the derivatives look like this

.. math::

    f'(x) = ie^{ix}

    f''(x) = i^2e^{ix} = -e^{ix}

    f'''(x) = i^3e^{ix} = -ie^{ix}

    f''''(x) = i^4e^{ix} = e^{ix}

Evaluated at :math:`x=0`, the exponentials become :math:`1` and we are left with the pattern :math:`1, i, -1, -i \dots`.  So our series is

.. math::

    e^x = 1 + ix - \frac{x^2}{2!} - i\frac{x^3}{3!} + \frac{x^4}{4!} + i\frac{x^5}{5!} - \frac{x^6}{6!} - i \frac{x^7}{7!} \dots

    = \cos x + i \sin x

These series then lead to definitions of the sine and cosine in terms of the exponential:

.. math::

    e^{ix} = \cos x + i \sin x

    e^{-ix} = \cos (-x) + i \sin (-x) = \cos x - i \sin x

Add

.. math::

    e^{ix} + e^{-ix} = 2 \cos x

or subtract

.. math::

    e^{ix} - e^{-ix} = 2i \sin x

So

.. math::

    \frac{d}{dx} (2 \cos x) = \frac{d}{dx} ( e^{ix} + e^{-ix}) = i( e^{ix} - e^{-ix}) = i(2i \sin x) = - 2 \sin x

    \frac{d}{dx} (2i \sin x) = \frac{d}{dx} ( e^{ix} - e^{-ix}) = i( e^{ix} + e^{-ix}) = i(2 \cos x)
