.. _cosine_s+t:

###############
Cosine of s + t
###############

========
Overview
========

There is a close relationship between formulas for sine and cosine of two angles added together or subtracted---the "addition" formulas---and formulas for rotation of coordinates and vectors around the origin.  In this section, we will look at some derivations:

- find the addition formulas using a geometrical approach from Strang (:ref:`next <strang-sum-angles>`)

- use the addition formulas to derive a formula for rotation of coordinates (:ref:`here <rotation>`)

- show an easy to remember proof of the addition formula starting from Euler (:ref:`here <euler-addition>`)

- show a proof of the addition formulas using vectors (:ref:`here <matrix-proof>`)

- compare rotation from a matrix and vector perspective (:ref:`here <rotate-vectors>`)

In the supplementary material:

- a brief introduction to matrix multiplication (:ref:`here <vectors-matrices>`)

- a geometric approach with stacked triangles (:ref:`next <stacked-triangles>`)

- an alternative geometric derivation of the sum formulas (:ref:`here <rotate-alt>`)

- an alternative way to go from the cosine addition formula to one for sine (:ref:`here <cosine-to-sine-alt>`)

========
Notation
========

The formulas relating the sine and cosine of a sum of angles, :math:`\theta + \phi`, to the individual angles :math:`\theta` and :math:`\phi` are incredibly useful and pop up all over calculus.

The one for cosine of added angles is:

.. math::

    \cos (\theta + \phi) = \cos \theta \cos \phi - \sin \theta \sin \phi

I like the look of those Greek letters, and it is a classic presentation in mathematics to employ them for angles, but here we will switch to use :math:`s` and :math:`t` instead, because they are easier to type and perhaps, a little easier on the eyes.

.. math::

    \cos (s + t) = \cos s \cos t - \sin s \sin t

Also, we will get rid of the parentheses, we just have to remember that the left-hand side is the cosine of the *sum of angles*:

.. math::

    \cos s + t = \cos s \cos t - \sin s \sin t

Once we have the formula for :math:`s + t` we can find one for the difference of angles easily by substituting :math:`t = -u`:

.. math::

    \cos s + (- u) = \cos s \cos (-u) - \sin s \sin (-u)

Recall that 

.. math::

    \sin (- \theta) = - \sin \theta

    \cos (- \theta) = \cos \theta

Although it's not a proof, just visualize what happens near :math:`\theta = 0` and then when :math:`\theta` becomes negative).  Or, remember that the sine is an odd function :math:`f(x) = - f(-x)` :

.. image:: /figs/sine_cosine_wikipedia.png
   :scale: 50 % 

while the cosine is an even function :math:`f(x) = f(-x)`:  cosine is symmetric about the :math:`y`-axis.

So

.. math::

    \cos s + (- u) = \cos s \cos (-u) - \sin s \sin (-u)

    \cos s - u = \cos s \cos u + \sin s \sin u

but of course, it doesn't matter if we use :math:`u` or :math:`t`, so switch back

.. math::

    \cos s - t = \cos s \cos t + \sin s \sin t

I like this form because it's easy to verify that, for *any* :math:`s`, if :math:`t=s`, then we have 

.. math::

    \cos 0 = 1 = \cos^2 s + \sin^2 s = 1
    
which is the most famous and useful trig identity.

