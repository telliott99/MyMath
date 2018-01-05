.. _exp-diff:

###################################
Difference quotient for exponential
###################################

We'll start the calculus of the exponential by looking at what happens to an exponential function when we vary :math:`x` by a small amount :math:`h`.  The difference quotient is

.. math::

    \lim_{h \rightarrow 0} \frac{b^{x+h} - b^x}{h}
    
for some base :math:`b`.  We can rewrite this as

.. math::

    \lim_{h \rightarrow 0} \frac{b^{x}b^{h} - b^x}{h}

    \lim_{h \rightarrow 0} \frac{b^{x}(b^{h}-1)}{h}

Now, the thing is that :math:`b^x` does not depend on :math:`h`, so it doesn't change as we go to the limit, and thus we have

.. math::

    b^x \lim_{h \rightarrow 0} \frac{b^{h}-1}{h}

We don't know what the term under the limit is equal to yet, but it is not dependent on :math:`x`, so it is a constant.  Therefore, the slope of the exponential

.. math::

    y = b^x

for some base :math:`b` is

.. math::

    y' = cb^x = cy

The slope is the same as the function, up to a constant.  (It turns out that if :math:`b=e`, then :math:`c=1` and we will have:

.. math::

    y = e^x

    y' = e^x

The function :math:`e^x` is its own derivative, which leads to all of its amazing properties.  We can easily calculate the value of the limit

.. math::

    \lim_{h \rightarrow 0} \frac{b^{h}-1}{h}

Set :math:`h=0.00001` and use Python.  For the following values of :math:`b` I get:

    >>> h = 0.00001
    >>> (2**h - 1)/h
    0.6931495828199629
    >>> from math import e
    >>> (e**h - 1)/h
    1.000005000006965
    >>>

.. math::

    b=2  \rightarrow 0.693

    b = 2.71828 = e \rightarrow 1.000

    b = 10 \rightarrow 2.302

This is one *definition* of :math:`e`.

It will not surprise you to learn that these values correspond to the natural logarithm of the base.

So :math:`e` is the value for which

.. math::

    \lim_{h \rightarrow 0} \frac{e^{h}-1}{h} = 1

We can rearrange the limit as follows:

.. math::

    \lim_{h \rightarrow 0} e^{h} = 1 + h

    \lim_{h \rightarrow 0} e = (1 + h)^{1/h}

This can also be written as

.. math::

    \lim_{x \rightarrow \infty} e = (1 + \frac{1}{x})^{x}

This can be calculated, but it doesn't converge so fast.  For :math:`x=100000`, I get :math:`e = 2.718168`, which is only correct to :math:`4` places.

====================
Evaluating the limit
====================

We can use the binomial theorem to evaluate 

.. math::

    \lim_{x \rightarrow \infty} e = (1 + \frac{1}{x})^{x}

and show that it is equivalent to

.. math::

    e = \frac{1}{0!} + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \cdots

which is yet another one of the equivalent definitions for :math:`e`.  The first three terms are :math:`1 + 1 + 1/2`, which is reasonably close. After six terms, we have :math:`e = 2.718`.  The series converges rapidly because the inverse factorials get small very quickly.  (See below).

We will do that (:ref:`here <exp-binomial>`), but as an alternative, I saw an interesting approach in the book *Mooculus*.  

https://mooculus.osu.edu

We use :ref:`L'Hopital's Rule<LHopital>`.  We're looking for

.. math::

    \lim_{x \rightarrow \infty} \ (1 + \frac{1}{x})^x

the first thing is to rewrite this as the exponential

.. math::

    1 + \frac{1}{x} = e^{\ln(1 + 1/x)}

and then

.. math::

    (1 + \frac{1}{x})^x =  (e^{\ln(1 + 1/x)})^x = \ e^{x \ln(1 + 1/x)}

To evaluate the limit, we need to evaluate the limit of the exponent

.. math::

    \lim_{x \rightarrow \infty} x   \ln (1 + \frac{1}{x})

At first, it doesn't look like we can use L'Hopital's Rule (there is no quotient), but there is a standard trick for these situations.  Just rearrange like so

.. math::

    = \lim_{x \rightarrow \infty} \frac{ \ln (1 + 1/x)}{1/x}
    
Both the top and the bottom limits are easily evaluated to be equal to :math:`0`.  So now we will differentiate.  The derivative of the numerator is (by the chain rule)

.. math::

    f'(x) = \frac{-x^{-2}}{1 + 1/x}

while the denominator is just

.. math::

    g'(x) = -x^{-2}

So we need to evaluate

.. math::
    
    \lim_{x \rightarrow \infty} \frac{f'(x)}{g'(x)}

The factor of :math:`-x^{-2}` cancels from both top and bottom, leaving

.. math::

    = \lim_{x \rightarrow \infty} \frac{1}{1 + 1/x} = 1

Substituting back

.. math::

    \lim_{x \rightarrow \infty} \ (1 + \frac{1}{x})^x

    = \lim_{x \rightarrow \infty} \  e^{x \ln(1 + 1/x)}

    = e^1 = e

Pretty cool, eh?