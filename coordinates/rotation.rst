.. _rotation:

#######################
Rotation of Coordinates
#######################

Since we have established the sum of cosines formula in the :ref:`previous section <cosine_s+t>`:

.. math::

    \cos s + t = \cos s \cos t - \sin s \sin t

We could, at this point, directly extend that to yield the sum of sines formula as shown :ref:`here <cosine-to-sine-alt>`, but the extension is a little awkward.  I have nice proofs :ref:`here <euler-addition>` and :ref:`here <stacked-triangles>`, but I want to defer them for the moment and just state the result for now:

.. math::

    \sin s + t = \sin s \cos t + \cos s \sin t

Given this, we can proceed with a very nice derivation of the formula for rotation of coordinates, as found in Stewart's *Calculus* (and Varberg, and others ..).

.. image:: /figs/min_rotation3.png
       :scale: 25%

Here, we have the standard :math:`x,y`-coordinates in black.  The rotated :math:`u,v`-coordinate system is in red, with a rotation angle :math:`\theta` in the counter-clockwise direction.

The ray to the point :math:`P` has length :math:`r`.  Notice that :math:`u` and :math:`v` are naturally expressed in terms of :math:`\phi`:

.. math::

    u = r \cos \phi
    
    v = r \sin \phi

while :math:`x` and :math:`y` are naturally expressed in terms of the combined angle :math:`\theta + \phi`.  Here is

.. math::

    x = r \cos (\theta + \phi)

Now, use the sum formula for cosine:
    
.. math::

    x = r \cos \theta \cos \phi - r \sin \theta \sin \phi

But

.. math::

    u = r \cos \phi

    v = r \sin \phi

So

.. math::

    x = u \cos \theta - v \sin \theta

In the same way:

.. math::
    
    y = r \sin (\theta + \phi)
    
    = r \sin \theta \cos \phi + r \cos \theta \sin \phi
    
    = u \sin \theta + v \cos \theta

=================
Solve for u and v
=================

To convert these formulas to functions :math:`u = f(x,y)` and :math:`v = f(x,y)`, do this:

.. math::

    x = u \cos \theta - v \sin \theta

so

.. math::

    x \cos \theta = u \cos^2 \theta - v \sin \theta \cos \theta
    
and

.. math::

    y = u \sin \theta + v \cos \theta
    
so

.. math::

    y \sin \theta = u \sin^2 \theta + v \sin \theta \cos \theta
    
adding:

.. math::

    x \cos \theta + y \sin \theta = u

similarly:

.. math::


    x \sin \theta = u \sin \theta \cos \theta - v \sin^2 \theta
    
    y \cos \theta = u \sin \theta \cos \theta + v \cos^2 \theta
    
add minus the first to the second:

.. math::

    - x \sin \theta + y \cos \theta = v
    
It *is* easier when you know where you're going.  In summary:

.. math::

    u =  x \cos \theta + y \sin \theta

    v = - x \sin \theta + y \cos \theta
    
and the original pair:

.. math::

    x = u \cos \theta - v \sin \theta

    y = u \sin \theta + v \cos \theta

==========
Small test
==========

Rotation of coordinates counter-clockwise (:math:`x,y` to :math:`u,v`) gives :math:`- \sin` in the formula for the vertical component :math:`v`), whereas clockwise rotation (:math:`u,v` to :math:`x,y`) gives :math:`- \sin` in the formula for the horizontal component :math:`x`.

One way to see that this is correct is to substitute from the :math:`u,v` formulas into the :math:`x,y` ones:

.. math::

    x = (x \cos \theta + y \sin \theta) \cos \theta - (- x \sin \theta + y \cos \theta) \sin \theta
    
Can you see that if this is multiplied out, we will get :math:`x (\cos^2 \theta + \sin^2 \theta) = x` and the terms with :math:`y` will just cancel?

A similar thing happens with the other one:

.. math::

    y = (x \cos \theta + y \sin \theta) \sin \theta + (- x \sin \theta + y \cos \theta) \cos \theta = y


