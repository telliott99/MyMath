.. _exp-limit:

##################################
Exponential:  evaluating the limit
##################################

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

We do that :ref:`here <exp-binomial>`, but as an alternative, I saw an interesting approach to this in the book *Mooculus*.  

https://mooculus.osu.edu

We will use L'Hopital's Rule.  We're looking for

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

    = \lim_{x \rightarrow \infty} \frac{ \ln (1 + \frac{1}{x})}{\frac{1}{x}}
    
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

===========
Another way
===========

Another version (showing that :math:`e` is equal to a limit):

In this section, we demonstrate that the number :math:`e` is equivalent to a limit:

.. math::

    \lim_{n \rightarrow \infty} (1 + \frac{1}{n})^n

I am simply following the proof as I found it online 

http://aleph0.clarku.edu/~djoyce/ma122/elimit.pdf

We start with a different definition of :math:`e` and show that it is equivalent.  We begin with this as a *definition* of the natural logarithm:

.. math::

    \ln x = \int_1^x \frac{1}{t} \ dt

We have worked through some consequences (__link__) following David Jerrison's MIT lecture.  It can be shown fairly easily that this function has all the properties of the natural logarithm.

In addition to that definition, we need two more properties, first:

.. math::

    \ln 1 = \int_1^1 \frac{1}{t} \ dt = 0

fairly obvious, since the upper and lower bounds are equal, and then second, our definition of :math:`e`.  It is the number such that

.. math::

    \ln e = \int_1^e \frac{1}{t} \ dt = 1

So here's the proof.  Let :math:`t` be any number in an interval :math:`[1, 1 + 1/n]`.  We're interested in what happens as :math:`n` gets large.  We have that

.. math::

    1 \le t \le 1 + \frac{1}{n}

If we invert each term, then :math:`\le` becomes :math:`\ge`, but we will instead rearrange the terms:

.. math::

    \frac{1}{1 + \frac{1}{n}} \le \frac{1}{t} \le 1

The only tricky step is this one:  for each of the above, we integrate the variable :math:`t` between the endpoints :math:`1` and :math:`1 + 1/n`, remembering that :math:`n` is just a number and so is :math:`1 + 1/n`, so we have

.. math::

    \int_1^{1 + 1/n} \frac{1}{1 + \frac{1}{n}} \ dt \le \int_1^{1 + 1/n} \frac{1}{t} \ dt \le \int_1^{1 + 1/n}  1 \ dt

The first integral is a constant times :math:`t` evaluated between :math:`1 + 1/n` and :math:`1` which is equal to the constant times :math:`1/n`:

.. math::

    [ \ \frac{1}{1 + \frac{1}{n}} \ ] \  \frac{1}{n} = \frac{1}{1 + n}

The second one is :math:`\ln (1 + 1/n)` by the definition of the logarithm, and the third is the same integral as the first but without the constant, so we have that:

.. math::

    \frac{1}{1 + n} \le \ln (1 + \frac{1}{n} ) \le \frac{1}{n}

From here on, we just rearrange things a bit.  Exponentiating each term doesn't change the inequality:

.. math::

    e^{1/1 + n} \le 1 + \frac{1}{n} \le e^{1/n}

The left-hand inequality can be raised to the power :math:`(n+1)` giving:

.. math::

    e \le (1 + \frac{1}{n})^{n + 1}

and divide by :math:`(1 + \frac{1}{n})`

.. math::

    \frac{e}{1 + 1/n} \le (1 + \frac{1}{n})^{n}

We notice that, in the limit as :math:`n \rightarrow \infty`, this becomes 

.. math::

    e \le  \lim_{n \rightarrow \infty} (1 + \frac{1}{n})^n

Similarly for the right-hand inequality, raise to the power :math:`n` giving:

.. math::

    (1 + \frac{1}{n})^{n} \le e

and in the limit as :math:`n \rightarrow \infty`, this becomes

.. math::

    \lim_{n \rightarrow \infty} (1 + \frac{1}{n})^{n} \le e

Call the limit :math:`L`.

The only way that :math:`e \le L` and :math:`L \le e` can both be true is if :math:`e` is equal to the limit in question.  This is the squeeze theorem.  Hence

.. math::

    e = \lim_{n \rightarrow \infty} (1 + \frac{1}{n})^n