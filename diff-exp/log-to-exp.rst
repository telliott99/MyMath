.. _log-to-exp:

########################
Logarithm to Exponential
########################

In more advanced treatments (what the math guys call analysis), it becomes a bit harder to introduce the exponential and logarithm in a natural way. 

What they do is to investigate a particular function often called :math:`L`, and show that the function :math:`L` has all the properties of the logarithm, \emph{so it is the logarithm}.  Then we will go backwards from the logarithm to the other properties of :math:`e`, like its value, and the fact the its derivative is itself.

This approach comes straight from David Jerrison's lecture in Calculus 1 (MIT online course).  We define the logarithm function as

.. math::

    L(x) = \int_1^x \frac{dt}{t}

.. image:: /figs/inv.png
   :scale: 50 %

Naturally, we start at :math:`1`, since the function is not defined at zero.

For example, the logarithm of :math:`2` is the area under the curve above, :math:`f(x) = 1/x`, between :math:`1 \le x \le 2`.  Having defined

.. math::

    L(x) = \int_1^x \frac{dt}{t}

By the Fundamental Theorem of Calculus (part II) we have

++++++++++
Property 1
++++++++++

.. math::

    L'(x) = \frac{1}{x}

The slope of the logarithm function is always positive (:math:`x>0`), but is undefined for :math:`x=0`

.. image:: /figs/log.png
   :scale: 50 %

++++++++++
Property 2
++++++++++

.. math::

    L(1) = \int_1^1 \frac{dt}{t} = 0
    
This property is by definition.  It fits with our use of exponents, where :math:`b^0 = 1`.

++++++++++
Property 3
++++++++++

.. math::

    L''(x) = - \frac{1}{x^2}

Although the area under the curve :math:`\ln(x)` is always increasing, so the slope is always positive, the rate of increase of the slope is always decreasing, so the shape is concave down.

++++++++++
Property 4
++++++++++

.. math::

    L(e) = 1

This is by definition as well.  :math:`e` is the :math:`x`-value for which the logarithm is equal to :math:`1`.

In extending to exponents it means we can write :math:`y = ln(x) \iff e^y = x`.

++++++++++
Property 5
++++++++++

.. math::

    L(ab) = L(a) + L(b)

To show that this last statement is true involves showing that this is equivalent

.. math::

    \int_1^{ab} \frac{dt}{t} = \int_1^{a} \frac{dt}{t} + \int_a^{ab} \frac{dt}{t}

For the arguments :math:`a` and :math:`ab` we have 

.. math::

    L(ab) = \int_1^{ab} \frac{dt}{t}

    L(a) = \int_1^{a} \frac{dt}{t}

Both of these are true by definition.  The one that takes a little work is

.. math::

    L(b) = \int_a^{ab} \frac{dt}{t}

Substitute :math:`au=t`, then :math:`a \ du = dt` and

.. math::

    \int_a^{ab} \frac{dt}{t} = \int \frac{a \ du}{au} = \int \frac{du}{u}

with a change in the limits

.. math::

    t=a \Rightarrow u=1

    t=ab \Rightarrow u=b

So it's just

.. math::

    L(b) = \int_1^b \frac{du}{u}

which is again, true by definition.  So the function :math:`L` has the property that :math:`L(ab) = L(a) + L(b)`, which is one of the two major properties of logarithms.

++++++++++
Property 6
++++++++++

To see that the second is also true, start with

.. math::

    L(a^r) = \int_1^{a^r} \frac{dt}{t}

Substitute :math:`t=u^r`, so :math:`dt = ru^{r-1} du`, and the limits become 

.. math::

    t=1 \Rightarrow u=1

    t=a^r \Rightarrow u=a

    L(a^r) = \int_{t=1}^{t=a^r} \frac{dt}{t} 
    
    = \int_{u=1}^{u=a} \frac{1}{u^r} (ru^{r-1}) du 
    
    = r \int_{u=1}^{u=a}  \frac{du}{u} 
    
    = rL(a)

As Dunham says (using A for L) "these properties of the hyperbolic area---namely :math:`A(ab) = A(a) + A(b)` and :math:`A(a^r) = rA(a)`---exactly mirror the corresponding properties of logarithms.  Clearly something interesting is afoot."

=================================
Difference quotient for logarithm
=================================

As seen in Hamming's *Methods of Mathematics Applied to Calculus, Probability and Statistics*, we can also go back to the definition of the logarithm as the reverse of the exponential

.. math::

    f(x) = \log_b x

and write the difference quotient

.. math::

    f'(x) = \lim_{h \rightarrow 0}  \frac{\log_b (x + h) - \log_b x}{h}

and then rearrange it as follows:

.. math::

    =  \lim_{h \rightarrow 0} \frac{\log_b (\frac{x+h}{x})}{h}

    =  \lim_{h \rightarrow 0} \frac{\log_b (1 + \frac{h}{x})}{h}

    =  \lim_{h \rightarrow 0} \log_b \ [ \ (1 + \frac{h}{x})^{1/h} \ ]

    =  \lim_{h \rightarrow 0} \frac{1}{x}  \ [ \ ( \log_b (1 + \frac{h}{x})^{x/h}  \ ]

    =   \frac{1}{x}  \ \lim_{h \rightarrow 0}  \ [ \ ( \log_b (1 + \frac{h}{x})^{x/h}  \ ]

So it's clear that we will need to evaluate the term for which we are taking the logarithm, in the limit

.. math::

    =  \lim_{h \rightarrow 0} (1 + \frac{h}{x})^{x/h}

Let :math:`t = h/x`.  Then this becomes

.. math::

    \lim_{t \rightarrow 0} (1 + t)^{1/t}

which ought to look :ref:`familiar <exp-diff>`.  It is one of the definitions of :math:`e`.  We have then that

.. math::

    \frac{d}{dx} \log_b x = \frac{1}{x} \ \log_b e

If we use the natural logarithm, then we have

.. math::

    \frac{d}{dx} \ln x = \frac{1}{x} \ \ln e = \frac{1}{x}

There is another derivation which is essentially identical to this one in videos on Khan Academy.

=================
Reverse direction
=================

What we have shown (defined, really, in this part) is that

.. math::

    \frac{d}{dx} \ln(x) = \frac{1}{x}

We want to go backward now, to show that the derivative of the function :math:`f(x) = e^x` is itself.  Start with

.. math::

    \ln(e^x) = x

    \frac{d}{dx} \ln(e^x) = \frac{d}{dx} x = 1

but using the property we just proved and the chain rule, this is also

.. math::

    \frac{d}{dx} \ln(e^x) = \frac{1}{e^x} \ \frac{d}{dx} e^x

so these two expressions are equal and

.. math::

    \frac{1}{e^x} \ \frac{d}{dx} e^x = 1

    \frac{d}{dx} e^x = e^x

