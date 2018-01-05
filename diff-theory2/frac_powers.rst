.. _frac_powers:

#################
Fractional Powers
#################

An amazing fact about the power rule is that it applies not only to the positive integers :math:`n=1,2,\dots` it also applies to the negative integers, and it even applies to rational exponents (powers) :math:`m/n`.

.. math::

    \frac{d}{dx} x^{m/n} = \frac{m}{n} \  x^{m/n - 1}

The original proof is by Newton's extension of the binomial.  Unfortunately, Newton never actually proved that the binomial extends to rational exponents, he just showed that it works in many situations.  The proofs I've found are either complicated, or seemed flawed.

This short chapter gives two alternative proofs for the power rule with fractional powers---the first uses the chain rule and the derivative of :math:`e^x`.

For simpler notation, start by letting :math:`r = m/n` so that :math:`x^{m/n} = x^r`.  Then write the definition of the natural logarithm of :math:`x`

.. math::

    x^r = e^{\ln(x^r)}

Take derivatives on both sides

.. math::

    \frac{d}{dx} \ x^r = \frac{d}{dx} \  e^{\ln(x^r)}

The left-hand side is what we seek.  Just apply the chain rule on the right

.. math::

    \frac{d}{dx} \  e^{\ln(x^r)} = e^{\ln(x^r)} \ \frac{d}{dx} \ \ln(x^r)

Reversing the original substitution, the right-hand side becomes

.. math::

    x^r  \ \frac{d}{dx} \ \ln(x^r)

But

.. math::

    \ln(x^r)  =  r \ln(x)

Now we've turned the rational exponent into a constant.  We know how to deal with that.

.. math::

    \frac{d}{dx} \ r \ln(x) = r \frac{d}{dx} \ln(x) = \frac{r}{x}

Putting it all together

.. math::

    \frac{d}{dx} \  x^r  = x^r  \ \frac{r}{x} = r x^{r-1}

Very nice.

==============================
Using implicit differentiation
==============================

Yet another way is the following trick that is also a special piece of mathematics.  I saw this in David Jerison's Calculus lectures.

.. math::

    y = x^{\frac{m}{n}}

    y^n = x^m

Differentiate implicitly

.. math::

    ny^{n-1} \ dy = mx^{m-1} \ dx

    \frac{dy}{dx} = \frac{m}{n} \ x^{m-1} \ \frac{1}{y^{n-1}}

Looking at the right-hand side and ignoring the factor of :math:`m/n` for the moment, we have:

.. math::

    x^{m-1} \ \frac{1}{y^{n-1}} = x^{m-1} \ y^{1-n}

    = x^{m-1} \ x^{m/n(1-n)}
    
    = x^{m-1} \ x^{m/n-m)}

Adding up the exponents of :math:`x` on the right-hand side:

.. math::

    m - 1 + \frac{m}{n} - m = \frac{m}{n} - 1

which gives finally

.. math::

    \frac{dy}{dx} = \frac{m}{n} \  x^{m/n - 1}

We've shown that powers of x with rational exponents obey the power rule.  In fact irrational powers like :math:`f(x) = x^\pi` also obey the power rule, but we don't need to prove that here.
