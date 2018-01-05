.. _nice:

#########
Functions
#########

=============
Nice function
=============

What does it take to be "nice"?  The function :math:`f` must be continuous over the closed interval :math:`[a,b]` and differentiable over the open interval :math:`(a,b)`.

=====================
Domain, range, target
=====================

A function is a rule that given a value :math:`x`, comes up with a value :math:`f(x)`, which is usually assigned to :math:`y = f(x)`.  A fundamental requirement for a function is that feeding the function any particular :math:`x` results in a unique value :math:`f(x)`.

A function's **domain** is the set of allowed :math:`x`-values, which may be all real numbers but could be more restricted, (or more expansive in multi-variable calculus).  The domain of

.. math::

    f(x) = \frac{1}{x}

does not include :math:`x = 0`, because division by zero is not defined.

A function's **range** is the set of all values :math:`f(x)` which correspond to the values of :math:`x` in the domain.  If the domain is the set :math:`D`, then the range :math:`R` is

.. math::

    R = { f(x) \ \forall \ x \in D }

Sometimes, the range may be too difficult to specify.  Stewart gives this example:

.. math::

    f(x) = \sqrt{x!}

For this reason, people will talk about the **target** :math:`T` of :math:`f`, where T contains every element in :math:`R`, but is more easily specified.

.. math::

    R \subset T

In math-speak, one might describe a function as:

.. math::

    f:D \rightarrow T

for some sets :math:`D` and :math:`T`.
    
For the example above, we might specify :math:`T` as the real numbers :math:`> 1`.

.. math::

    y | y \in \mathbb{R} and y \ge 1

An amusing example that Stewart gives is:

.. math::

    f(x) = \ln (\ln (\sin x))

The domain of :math:`\sin x` is the real numbers, but the range is

.. math::

    R = -1 \le x \le 1

Of the numbers produced by the sine function, only those :math:`> 0` are in the domain of the logarithm.  

Furthermore, the range of the nested (inside) logarithm is :math:`\le 0` for that set of inputs.  

But that range is not within the domain of the logarithm, so the function is meaningless, it cannot produce any output.

=========
Injection
=========

The question of whether a function has an inverse (is reversible) comes up naturally in the study of techniques of integration.  Consider this triangle

.. image:: /figs/arcsin4.png
   :scale: 50 %

We have constructed the triangle so that the sine of the angle :math:`t` is equal to :math:`x/1`:

.. math::

    \sin t = x 

The inverse of sine is the function :math:`\arcsin` (or :math:`\sin^{-1}`):

.. math::

    \sin^{-1} x = t 

Read this as:  arcsine (inverse sine) of :math:`x` is equal to :math:`t`.  Alternatively, we can say that :math:`t` is the angle whose sine is equal to :math:`x`.  It doesn't really matter that there is no technique for computation other than trying different values for :math:`x`, calculating :math:`\sin x`, and comparing that with the :math:`t` we are given.

Now, by the Pythagorean Theorem, the third side of the triangle has length :math:`\sqrt{1-x^2}`, and in terms of angle :math:`t`, we have that

.. math::

    \cos t = \sqrt{1-x^2} 

This becomes useful where we have an integral like:

.. math::

    \int \frac{1}{\sqrt{1-x^2}} \ dx 

We cannot just substitute for :math:`1-x^2` because we don't have the derivative (we don't have an :math:`x` on top).  But doing a trigonometric substitution, we have that

.. math::

    \frac{1}{\sqrt{1-x^2}} = \frac{1}{\cos t} 

To complete the substitution, we need to find :math:`dx` in terms of :math:`dt`:

.. math::

    x = \sin t 

    dx = \cos t \ dt 

So that gives:

.. math::

    \int \frac{1}{\cos t} \  \cos t \ dt 

which simplifies nicely to:

.. math::

    \int dt = t 

To complete the solution, we need to switch back to the original variable :math:`x`.

.. math::

    t = \sin^{-1} x 

Thus:

.. math::

    \int \frac{1}{\sqrt{1-x^2}} \ dx = \sin^{-1} x + C 

It may seem strange at first that this integral in Cartesian coordinates (:math:`xy`-"land") gives a result in terms of the angle :math:`t`, but consider that the equation of the unit circle is

.. math::

    x^2 + y^2 = 1 

so

.. math::

    y = + \sqrt{1 - x^2} 

is the equation of the top half of the circle (above the :math:`x`-axis).  The integral that we have computed is the area under this curve, under the right limits it is the area of the unit circle, so naturally this result involves :math:`\pi`.

Another way to approach this (which involves the same relationships) is to use differentials

.. math::

    x = \sin t 

    dx = \cos t \ dt 

    \frac{dt}{dx} = \frac{1}{\cos t} 

    \frac{d}{dx} t =  \frac{1}{\cos t} 

    \frac{d}{dx} \sin^{-1} x =  \frac{1}{\sqrt{1-x^2}} 

    \int \frac{d}{dx} \sin^{-1} x \ dx = \int \frac{1}{\sqrt{1-x^2}} \ dx 

    \sin^{-1} x =  \int \frac{1}{\sqrt{1-x^2}} 

In working with reverse functions, we have to consider carefully the domain and range of each. (more)

We also have to consider whether a given function even has an inverse.  Consider (following Koblitz)

.. math::

    f = x^3; \ \ \ g = x^{1/3} 

For these two functions to qualify as inverses we require that

.. math::

    x = f(g(x)) 

and

.. math::

    x = g(f(x)) 

However, this is not true of the square root function

.. math::

    f = x^2; \ \ \ g = x^{1/2} 

because there are two real numbers that satisfy :math:`x^2 = 2` for example, but when we take the square root, we define the positive root as the result of the function :math:`g`.

=========
Injective
=========

In the language of set theory, consider (the set of) all real numbers that are in the domain of :math:`f`---call that set :math:`A`, and then call the corresponding values of :math:`f(x)` the set :math:`B`.  :math:`B` is range of :math:`f`.

If and only if each of these numbers yields a \emph{different} value in :math:`B`, then it may be possible to come up with an inverse function :math:`g` which maps from the range back to the domain.

Such a function is described as \emph{injective}.  On the other hand, if two different values :math:`a_1, a_2` in the domain of :math:`f` yield the same value :math:`f(a_1) = f(a_2)`, then the function is non-injective.

Koblitz:

Let :math:`A` and :math:`B` be sets and let :math:`f:  A \rightarrow B` be a function.  We say that :math:`f` is injective or one-to-one if :math:`f(x) = f(y)` implies that :math:`x = y`.  See the wikipedia figure, upper-left panel.

.. image:: /figs/injective.png
   :scale: 50 %

==========
Surjective
==========

Surjective is a statement about the range and co-domain of :math:`f`.  If there numbers in the co-domain that do not correspond to :math:`f(x)` for \emph{any} :math:`x` in the range of :math:`f`, then :math:`f` is not surjective.  See the upper-right panel.

Koblitz:

We say that :math:`f` is surjective or onto if for every :math:`b \in B` there is an :math:`a \in A` such that :math:`f(a) = b`.

If :math:`f` is both injective and surjective, then :math:`f` is bijective or one-to-one and onto.

A simple test is the \textbf{horizontal line test}.  If a horizontal line intersects the graph of :math:`f(x)` at more than one point, the function is not injective and not reversible.  (Those two points are different values of :math:`x` which share the same value :math:`y = f(x)`).

The function :math:`f(x) = x^2` is a parabola and it fails the horizontal line test.  On the other hand, the graph of :math:`f(x) = x^3` is:

.. image:: /figs/y=x^3.png
   :scale: 50 %

and it passes the test.  (However :math:`x^3 - x^2` fails).

Let's look at the graph of the arcsin and arccosine functions.

.. image:: /figs/arcsin4.png
   :scale: 50 %

These graphs are simply plots of the more familiar sine and cosine that have been rotated counter-clockwise by 90 degrees, and also flipped left-to-right (to make :math:`x`-values increase to the right, as usual.

By definition, a function assigns a unique value of :math:`y` for each value of :math:`x`.  Since these functions repeat, we limit the domain appropriately.  For arcsin, the domain is :math:`y = -\pi/2 \rightarrow \pi/2`, while for arccose it is :math:`y = 0 \rightarrow \pi`.
