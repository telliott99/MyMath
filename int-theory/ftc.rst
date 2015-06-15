.. _ftc:

###
FTC
###

.. image:: /figs/FTC_geometric2.png
   :scale: 50 %

The big picture view of the fundamental theorem of calculus (FTC) is that if we consider that the area :math:`A` under the graph of a function :math:`f(x)` as being itself a function :math:`A(x)` (the left-hand boundary for the area is fixed), then

.. math::

    A' = f(x)

After the discussion in the previous chapter :ref:`here <circles>`, this should come as no surprise.  For a circle we asked:

    "how does the area grow with a small change in radius", the answer is that it grows like the circumference :math:`2 \pi r`, times the small change in radius :math:`dr`.

Now we ask:

    How does :math:`A(x)` grow with a small change in :math:`x`?  It grows like :math:`f(x) \times dx`.

and we can find the area function :math:`A` as one of the family of *anti-derivatives* of :math:`f`.  

Now, there are conditions, namely that :math:`F` must be continuous on the interval :math:`[a,b]` and differentiable on :math:`(a,b)`, and we agree to only look at :math:`x` values contained in the interval :math:`(a,b)`.  In other words, the function :math:`F` and its derivative :math:`f` have to be "nice."  

There are two formal statements of the FTC, that turn out to be equivalent.

Normally we might write:

.. math::

    F(x) = \int_a^b f(x) \ dx

but here we are going to let the upper bound of the integral be a variable (:math:`x`), so we will write the equation in terms of a different "dummy" variable :math:`t`:

.. math::

    \int_a^b f(t) \ dt

then we write :math:`x` for the upper bound:

.. math::

    F(x) = \int_a^x f(t) \ dt
    
and then

.. math::

    F'(x) = \frac{d}{dx} \ \int_a^x f(t) \ dt = f(x)

The expression :math:`\int_a^x f(x) \ dx` is a *number*, a function of :math:`x`, which gives a different result (usually) for each value of :math:`x`.

The area under the curve :math:`y=f(x)` between the left-hand boundary :math:`a` and the right-hand boundary :math:`x` grows at the rate :math:`f(x)` as :math:`x` changes by a little bit.  The derivative of the area function is :math:`f(x)`.  This is obvious from the figure shown above.

The second version (FTC2) gives us a method to calculate what the number is, i.e. a way to evaluate integrals:

.. math::

    \int_a^b f(x) \ dx = F(b) - F(a)

where :math:`F` and :math:`f` are the same as before, namely :math:`F'(x) = f(x)`.

If we can find a function :math:`F` whose derivative is equal to :math:`f` then we can evaluate the integral as shown.  An example:

.. math::

    f(x) = x^2 \ dx

    F(x) = \frac{1}{3}x^3

    \int_1^2 x^2 \ dx = \frac{1}{3}x^3 \ \bigg |_1^2 = \frac{1}{3}(8-1) = \frac{7}{3}

The area under the curve :math:`f(x) = x^2` between :math:`x=1 \rightarrow 2` is just :math:`7/3`.

A simple-minded view of the FTC is that it says that integration and differentiation are the reverse processes for each other.  In fact, this connection is the fundamental insight of Newton and Leibnitz.

However, it is important to emphasize that **the FTC is not the definition of integration, but the opposite**.  Integration is defined as the limit of Riemann sums of the interval.  What the FTC does is to provide a process that comes to the same answer as the sum method, but without the pain.

(see Bressoud from p. 104 in the AP Calculus handout).
