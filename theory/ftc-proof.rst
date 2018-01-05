.. _ftc-proof:

###############################
Fundamental Theorem of Calculus
###############################

David Joyce has proofs of the FTC which we will follow, here:

http://aleph0.clarku.edu/~ma120/FTCproof.pdf

There are actually two statements involved, which he calls the FTC and :math:`FTC^{-1}` (inverse FTC).  If :math:`F` is an antiderivative of :math:`f`, then:

.. math::

    \int_a^b f(x) \ dx = F(b) - F(a)

Our requirement for :math:`f` will be that it is continuous on :math:`[a,b]`.  (This isn't necessary in the higher theory of integration, but it is for a Riemann integral).

This theorem is what we use when we evaluate definite integrals.  

The inverse statement is:

.. math::

    \frac{d}{dx} \ \int_a^x f(t) \ dt = f(x)

for :math:`x \in [a,b]`.



