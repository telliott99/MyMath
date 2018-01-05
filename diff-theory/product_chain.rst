.. _product_chain:

###########################
Product Rule and Chain Rule
###########################

============
Product Rule
============

In previous work, we found out how to differentiate (find the derivative of) polynomial functions of :math:`x`.  The power rule is:

.. math::

    f(x) = x^n
    
    f'(x) = nx^{n-1}

We also saw that constants just come along with the result 

.. math::

    f(x) = ax^n
    
    f'(x) = anx^{n-1}

You already know

.. math::

    f(x) = a
    
    f'(x) = 0

That one actually follows the power rule:

.. math::

    f(x) = ax^0
    
    n = 0
    
    f'(x) = nx^{n-1} = 0

The slope of :math:`y = a` where :math:`a` is a constant, is just 0.

We saw that the power rule extends to at least some negative and rational exponents (and we will prove that it extends to all :ref:`here <frac_powers>`).

.. math::

.. math::

    f(x) = \frac{1}{x} = x^{-1}
    
    f'(x) = -\frac{1}{x^2} = -x^{-2}

and

.. math::

    f(x) = \sqrt{x} = x^{1/2}
    
    f'(x) = \frac{1}{2\sqrt{x}} 
    
    = \frac{1}{2} x^{-1/2}

We also calculated these using the difference quotient :ref:`here <diff_quotient>`.

We will need to prove these last assertions for the general case, later.

Finally, we saw that for a sum of two functions

.. math::

    f(x) + g(x)
    
    ( f(x) + g(x) ) \ ' = f'(x) + g'(x)

This leads naturally to the  question, what about a product of functions?

.. math::

    f(x) \ g(x)
    
    ( f(x) \ g(x) ) \ ' = \ ? 

It's kind of embarrassing, but originally Leibnitz published that this derivative is equal to :math:`f'(x) g'(x)`.

The product rule is

.. math::

    [ \ f(x) \ g(x) \ ] \ ' = f(x) \ g'(x) + f'(x) \ g(x)

You want to see a proof?  See the supplementary material :ref:`product rule proof<proof-product-rule>`.  Here is a nice picture:

.. image:: /figs/product_rule.png
   :scale: 50 %
  
(from *Mooculus*)

https://mooculus.osu.edu

Written with differentials and different letters :math:`u` and :math:`v` this is the same as

.. math::

    u = f(x), v = g(x)

    \frac{d}{dx}(uv) = \frac{du}{dx} v + \frac{dv}{dx} u

which is frequently abbreviated as

.. math::

    (uv)' = u'v + uv'

I find this form particularly easy to remember, but don't forget what :math:`v'` means.  It means :math:`dv/dx` (or some other variable).

Actually I have to say that I learned it another way:  "this times the derivative of that plus that times the derivative of this", where "this" is :math:`u` and "that" is :math:`v`.

But I have come to write it this way (stating with :math:`u'`), because then the quotient rule will involve only a sign change in the numerator---see below.

Let's do some examples

.. math::

    f(x) = x^2 = x \ x
    
    (x \ x)' = x (1) + (1) x = 2x

The answer must match what we already know to be true!  This point is crucial for any new technique.

+++++++
Example
+++++++

.. math::

    f(x) = \sqrt{x} \sqrt{x}
    
    f'(x) = (\sqrt{x} \sqrt{x})' 
    
    = \frac{1}{2\sqrt{x}} \sqrt{x} + \sqrt{x} \frac{1}{2\sqrt{x}} 
    
    = \frac{1}{2} + \frac{1}{2} = 1

+++++++
Example
+++++++

.. math::

    f(x) = ax
    
    (ax)' = a \ (1) + (0) x = a

+++++++
Example
+++++++

A last one that we already know.  Suppose 

.. math::

    f(x) = (x+3)(2x-2) 
    
    = 2x^2 + 4x - 6

by the power rule:

.. math::

    f'(x) = \frac{d}{dx} 2x^2 + 4x - 6 = 4x + 4

by the product rule:

.. math::

    f'(x) = \frac{d}{dx} (x+3)(2x-2) 
    
    = (x+3)(2) + (1)(2x-2) 
    
    = 4x + 4

It is worth while to play around with some examples, once we know the trig function derivatives, and add the exponentials when we get there.

==========
Chain Rule
==========

Using :math:`f'(x)` is sometimes not as nice as the :math:`dy/dx` differential notation, because the latter invites us to do algebraic manipulation of the differentials.  If :math:`y=x^2` (for example), we write

.. math::

    y = f(x) = x^2

Then

.. math::

    \frac{dy}{dx} = f'(x) = 2x

It is perfectly OK to move the :math:`dx` to the other side

.. math::

    \frac{dy}{dx} dx = dy = 2x \ dx

Imagine that :math:`x` is some function of another variable, like time :math:`t`.  Then :math:`y` will also be a function of :math:`t` (through its dependence on :math:`x`), and it will also be true that

.. math::

    \frac{dy}{dt} = \frac{dy}{dx} \ \frac{dx}{dt}
    
    \frac{dy}{dt} = 2 x \ \frac{dx}{dt}

and this makes sense because

.. math::

    \frac{dy}{dx} = 2x

Suppose we are given :math:`y = f(x)`, and :math:`x = f(t)` and asked to calculate :math:`dy/dt`.  The way we get it is:

.. math::

    \frac{dy}{dt} = \frac{dy}{dx} \ \frac{dx}{dt}
    
Here is a nice picture:

.. image:: /figs/chain_rule.png
   :scale: 50 %
  
(from *Mooculus*)

https://mooculus.osu.edu

+++++++
Example
+++++++

Suppose we have

.. math::

    y = x^2, \ \ \ \ x = 3t

    \frac{dy}{dx} = 2x, \ \ \ \ \frac{dx}{dt} = 3
    
    \frac{dy}{dt} = \frac{dy}{dx}\ \frac{dx}{dt} 
    
    = 6x = 18t

which we can easily confirm by just substituting into :math:`y=x^2`

.. math::

    y = x^2 = (3t)^2 = 9t^2
    
    \frac{dy}{dt} = 18t

This is called the chain rule.

Here is a :ref:`proof <proof-chain-rule>`)

+++++++
Example
+++++++

Another example will give a glimpse of how useful it can be.  Suppose we are given

.. math::

    y = \sqrt{(1+x^2)}

What is :math:`dy/dx`?

We can make a "substitution"

.. math::

    u = 1 + x^2, \ \ \ \  \frac{du}{dx} = 2x

    y = \sqrt{u}
    
    \frac{dy}{du} = \frac{1}{2\sqrt{u}}

    \frac{dy}{dx} = \frac{dy}{du} \ \frac{du}{dx} 
    
    = \frac{1}{2\sqrt{u}}  2x 
    
    = \frac{x}{\sqrt{(1+x^2)}}

=============
Quotient Rule
=============

There is one more rule to cover, and that is the quotient rule.  If we have 

.. math::

    \frac{f(x)}{g(x)}

or more simply

.. math::

    \frac{u}{v}

where :math:`u` is really :math:`u(x)` and :math:`v` is really :math:`v(x)`, what is 

.. math::

    \frac{d}{dx} (\frac{u}{v}) = ?

There is a clever derivation of the quotient rule that I saw in David Jerison's lectures.  

We use the known value for :math:`\frac{d}{dx} v^{-1} = (-1/v^2) \ v\ '` (chain rule), as well as the product rule

.. math::

    \frac{d}{dx} (\frac{u}{v}) = \frac{du}{dx} \ (\frac{1}{v} )  +   u \frac{d}{dx} (\frac{1}{v})
    
    = \frac{u'}{v} - u \frac{v'}{v^2} 
    
    = \frac{u'v}{v^2} - \frac{uv'}{v^2} 
    
    = \frac{u'v - uv'}{v^2}

+++++++
Example
+++++++

We check by using it on a simple known example

.. math::

    y = \frac{1}{x}
    
    y' = \frac{u'v - uv'}{v^2}

    = \frac{ (0)(x) - (1)(1)}{x^2} 
    
    = -\frac{1}{x^2}

So that's why I always write :math:`u'` as the first half of the first term of the product rule

Again

.. math::

    y = \frac{x}{1}
    
    y' = \frac{u'v - uv'}{v^2}

    = \frac{ (1)(1) - (0)(x)}{1^2} 
    
    = 1

Perhaps those were too easy.  How about

.. math::

    y = \frac{x}{x^2}

    y' = \frac{u'v - uv'}{v^2}
    
    = \frac{ (1)(x^2) - (2x)(x)}{x^4} 
    
    = -\frac{x^2}{x^4} 
    
    = -\frac{1}{x^2}
