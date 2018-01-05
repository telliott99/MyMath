.. _Dirac_delta:

###########
Dirac_delta
###########

"The Dirac delta function :math:`\delta(x)` is not really a 'function'. It is a mathematical entity called a distribution which is well defined only when it appears under an integral sign.	 It has the following defining properties:"

.. math::

    \delta(n) =
    \begin{cases}
    0, & \text{if } x \ne 0 \\
    \infty, & \text{if } x = 0
    \end{cases}

.. math::

    \int_a^b \delta(x) \ dx = 1 \ \ \ a < 0 < b 

http://www.math.oregonstate.edu/BridgeBook/book/math/deltaintro

Going on, they say that by definition, a third property is that (evaluated at :math:`x=0`):

.. math::

    x \delta(x) \equiv 0 

Kind of like rock-paper-scissors. 
:math:`x=0` trumps :math:`\delta(0)=\infty`.

Consequences include the following:

.. math::

    \int_{-\infty}^{\infty} f(x) \delta(x) dx 

since :math:`\delta(x)` is zero everywhere other than :math:`x=0`, this is

.. math::

    = \int_{-\infty}^{\infty} f(0) \delta(x) dx = 

but :math:`f(0)` is a constant so

.. math::

    f(0) \int_{-\infty}^{\infty} \delta(x) dx 

    = f(0) 

The Dirac Delta function "picks out" the value of the function at :math:`0`.  

+++++
Shift
+++++

It can be shifted easily by using :math:`\delta(x-a)`

.. math::

    \int_{-\infty}^{\infty} f(x) \delta(x-a) dx = f(a) 

For *any* :math:`\epsilon > 0`:

.. math::

    \int_{a-\epsilon}^{a + \epsilon} f(x) \delta(x-a) \ dx = f(a)
