.. _diff_quotient:

###################
Difference quotient
###################

In this section we'll look at the geometric interpretation of the derivative---the beginning of calculus.  Suppose we have a curve as shown in the figure, corresponding to some function.  Let's think for a minute about the general case, :math:`f(x)`.

.. image:: /figs/diff_quotient.png
   :scale: 50 %

We pick a point :math:`P` on the curve.  The value of :math:`x` at :math:`P` is :math:`x` (of course), and the value of :math:`y` is :math:`f(x)`.  That is, the point :math:`P` has coordinates :math:`P=(x,f(x))`.  Now consider moving to a point :math:`Q` near :math:`P` but also on the curve, by adding a small amount to :math:`x`.  We could call that small amount :math:`\Delta x`, but many books use :math:`h`, a simpler notation, so we'll try that.  The value of the function at :math:`x+h` is :math:`f(x+h)` and :math:`Q=(x+h,f(x+h))`.

The slope of the line (the secant) connecting :math:`Q` and :math:`P` is

.. math::

    \frac{\Delta y}{\Delta x} = \frac{f(x+h) - f(x)}{x + h - h} = \frac{f(x+h) - f(x)}{h}

This is a famous quantity, it's called the *difference quotient*.

The goal of this part of calculus is to find the slope of the tangent to the curve at the point :math:`P`.  What we have is an expression for the slope of the line :math:`PQ`, which is close but not quite the same.  To go from the secant to the tangent, we ask "what happens to this expression as :math:`h` gets smaller and smaller and approaches zero."  In mathematical language, we say the slope of the tangent is equal to

.. math::

    \lim_{h \to 0} \ \frac{\Delta y}{\Delta x} = \frac{f(x+h) - f(x)}{h}

Let's try a couple of examples and look for a pattern.

+++++++
Example
+++++++ 

.. math::

    f(x)=x^2

Let's go without the limit sign to start with.  For this function, we write that the difference quotient is

.. math::

    \frac{(x+h)^2 - x^2}{h}

    = \frac{x^2 + 2xh + h^2 - x^2}{h}

    = \frac{2xh + h^2}{h}

Now we do the division by the denominator :math:`h`

.. math::

    = 2x + h
    
Finally, to get the slope of the tangent, we evaluate the limit

.. math::

    \lim_{h \to 0} \  2x + h = 2x

At every point on the curve :math:`y=x^2`, the slope of the tangent line to the curve is :math:`2x`.  So the slope at :math:`x=0` is :math:`0`, and the slope at :math:`x=2` is :math:`4`, and so on. We call this process of computing the difference quotient and then finding the limit as :math:`h \to 0`, "taking the derivative."  It produces an expression which is the derivative of :math:`y` with respect to :math:`x`, in this case

.. math::

    \frac{dy}{dx} = 2x

Another useful shorthand uses the :math:`f` from :math:`f(x)`, we adopt the convention that the derivative of :math:`f(x)` is can be written :math:`f'(x)`.

.. math::

    f'(x) = 2x

If we repeat this exercise with a leading constant a (that is, for :math:`f(x) = ax^2`), we find that every term in the numerator of the difference quotient will contain :math:`a`, and the final result will be :math:`2ax`.  Constants just get carried through.

+++++++
Example
+++++++

.. math::

    f(x)=\sqrt{x}, \ \ (x \ge 0)

The difference quotient for this function is

.. math::

    \frac{\sqrt{x+h} - \sqrt{x}}{h}

Clean up the numerator by multiplying by the conjugate

.. math::

    \frac{\sqrt{x+h} - \sqrt{x}}{h} \ \  \frac{\sqrt{x+h} + \sqrt{x}}{\sqrt{x+h} + \sqrt{x}}

    = \frac{x + h - x}{h \ (\sqrt{x+h} + \sqrt{x})}

    = \frac{h}{h \ (\sqrt{x+h} + \sqrt{x}) }

    = \frac{1}{\sqrt{x+h} + \sqrt{x}}

We evaluate the limit

.. math::

    m = \lim_{h \to 0} \  \frac{1}{\sqrt{x+h} + \sqrt{x}} = \frac{1}{2\sqrt{x}}

+++++++
Example
+++++++

.. math::

    f(x)=1/x, \ \ (x \ne 0)

.. math::

    \frac {  \frac{1}{x+h} - \frac{1}{x}  }  {h}

Clean up the numerator

.. math::

    \frac {  \frac{1}{x+h} - \frac{1}{x}  }  {h} \ \  \frac{(x)(x+h)}{(x)(x+h)}

    = \frac {x - (x+h)}  {h\ (x) \ (x+h)}

    = \frac {-h}  {h\ (x) \ (x+h)}

    = -\frac {1}  {(x) \ (x+h)}

We evaluate the limit:

.. math::

    \lim_{h \to 0} \  -\frac {1}  {(x) \ (x+h)} = - \frac{1}{x^2}

=======
Summary
=======

There's a pattern here.  We will use the notation :math:`f'(x)` to indicate the slope of the curve :math:`f(x)` at :math:`x`, obtained as

.. math::

    \lim_{h \to 0} \ \frac{f(x+h) - f(x)}{h}

    f(x) = x^2 \ \ \Rightarrow \ \  f'(x) = 2x

    f(x) = \sqrt{x} = x^{1/2}\ \ \Rightarrow \ \  f'(x) = \frac{1}{2}x^{-1/2}

    f(x) = \frac{1}{x} = x^{-1} \ \ \Rightarrow \ \  f'(x) = -\frac{1}{x^2} = -x^{-2}

The general formula is

.. math::

    f(x) = x^n \ \ \Rightarrow \ \  f'(x) = nx^{n-1}

This is easily proved using the binomial expansion for :math:`(x + h)^n` for integral :math:`n` (:math:`n \in 1,2, \dots`).  The first three terms are:

.. math::

    (x + h)^n = x^n + n x^{n-1} h + (n-1)x^{n-2} h^2 + \dots

The key point is that the last term shown and all subsequent terms contain powers of :math:`h^2` or higher.  

After division by :math:`h`, for each of these terms there will remain one or more terms of :math:`h`, and in the limit :math:`\lim_{h \to 0}` these become zero.

.. math::

    \lim_{h \to 0} \ \frac{(x+h)^n - x^n}{h}
    
    = \lim_{h \to 0} \ \frac{x^n + n x^{n-1} h + (n-1)x^{n-2} h^2 + \dots - x^n}{h}
    
    = \lim_{h \to 0} \ \frac{n x^{n-1} h + (n-1)x^{n-2} h^2 + \dots}{h}

    = \lim_{h \to 0} \ n x^{n-1} + (n-1)x^{n-2} h + \dots
    
    = n x^{n-1}

Another question is what to do with a sum or difference of polynomials, such as 

.. math::

    f(x) + g(x)

If you write out the difference quotient in the second case

.. math::

    \frac{ f(x+h) - f(x) + g(x+h) - g(x)}{h}

everything can be exactly as before, just grouping all :math:`f(x)` and those from :math:`g(x)` separately. 

.. math::

    [f(x) + g(x)]' = f'(x) + g'(x)

++++
Note
++++

We showed above by computing the difference quotient directly that

.. math::

    f(x) = \sqrt{x}
    
    f'(x) = \frac{1}{2\sqrt{x}}

Here is another approach to the same problem:

.. math::

    \frac{dy}{dx} \ \frac{dx}{dy} = 1
    
Write:

.. math::
    
    y = x^2
    
    \frac{dy}{dx} = 2x
    
Write:

.. math::

    x = \sqrt{y}
    
    \frac{dy}{dx} \ \frac{dx}{dy} = 1
    
    2 x \ \frac{dx}{dy} = 1
    
    \frac{dx}{dy} = \frac{1}{2x} =\frac{1}{2 \sqrt{y}}

Here, just remember that in the last part, :math:`y` is the *independent* variable, so if we switch back to our usual notation we have:

.. math::

    \frac{dy}{dx} =\frac{1}{2 \sqrt{x}}

