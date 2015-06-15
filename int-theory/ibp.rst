.. _ibp:

####################
Integration By Parts
####################

Integration by parts comes from the product rule.  If we have two functions :math:`f(x)` and :math:`g(x)` and multiply them together, then the derivative is:

.. math::

    \frac{d}{dx} \ f(x) \ g(x) = f'(x) \ g(x) + f(x) \ g'(x)

A simple shorthand notation for the same result is:

.. math::

    (uv)' = v \ du +  u \ dv
    
The idea is that when we integrate this we will have

.. math::

    \int (uv)' = uv = \int v \ du +  \int u \ dv

Rearranging, we obtain

.. math::

    \int u \ dv = uv - \int v \ du

Just to be clear, with an explicit independent variable :math:`x` this is:

.. math::

    \int u \frac{dv}{dx} \ dx = uv - \int v \frac{du}{dx} \ dx

========
Examples
========

As a first example, take 

.. math::

    \int x \ e^x \ dx

If this were

.. math::

    \int x \ e^{x^2} \ dx

there would be no problem, because upon differentiating :math:`x^2` using the chain rule, we will get the :math:`x` that we see in the example.  For the first problem, write

.. math::

    u = x

    du = dx

    dv = e^x \ dx

    v = \int e^x \ dx = e^x

:math:`u \ dv` is what we have.  Now let's see how this simplifies things

Using the formula

.. math::

    \int u \ dv = uv - \int v \ du

    uv = xe^{x}

    \int v \ du = \int e^{x} \ dx = e^{x}

So

.. math::

    \int x e^x \ dx =  xe^{x} - e^{x}

Check

.. math::

    \frac{d}{dx} \ [ \ xe^{x} - e^{x}\ ]  = xe^{x}

It is clear that the extra term in the answer is there to eliminate an extra term in the derivative.  This pattern is generally true with integration by parts.

Our old friend :math:`\cos^2x` can be solved by this method.  See :ref:`cosine_sq`.

Now, consider 

.. math::

    \int \ln x \ dx

It looks easy until you remember that you know the derivative, rather than the integral of :math:`\ln(x)`.  So let

.. math::

    u = \ln x

    du = \frac{1}{x} \ dx

    dv = dx

Brilliant!  Then

.. math::

    v = \int \ dx = x

    \int u \ dv = uv - \int v \ du

    uv = x \ln x

    \int v \ du = \int x \ \frac{1}{x}  dx = x

We have

.. math::

    \int \ln x \ dx = x \ \ln x - x

And again, when checking by differentiation, we see that the second term in the result is there to cancel one term from the product rule.

Here is one last elementary one.  Start by differentiating 

.. math::

    \frac{d}{dx} \ x \sin x = x \cos x + \cos x

So, what will we do when faced with 

.. math::

    \int x \cos x \ dx

Can you see that :math:`x \sin x` is the integral of :math:`x \cos x` except for the extra term?  If not, do this using our new method.

.. math::

    u = x

    du = dx

    dv = \cos x \ dx

Then

.. math::

    v = \int dv = \sin x

Using the formula

.. math::

    \int u \ dv = uv - \int v \ du

    \int x \cos x \ dx = x \sin x - \int \sin x \ dx

    = x \sin x + \cos x

=======
Summary
=======

The way I think about this technique is I try to group the integral into terms that will be :math:`dv` and terms that will be :math:`u`.  If :math:`du` is simpler than :math:`u`, and if I can do the integral :math:`\int dv = v`, then integration by parts is the way to go.  Here is a picture from Strang you may find illuminating

.. image:: /figs/ibp.png
       :scale: 25%

More (and harder) problems here:  :ref:`ibp_more`.