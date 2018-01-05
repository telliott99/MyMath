.. _cosine-to-sine-alt:

##########################
Connecting sine and cosine
##########################

Recall that the graphs of the sine and cosine follow the same pattern, just shifted in phase.  If we think of the angle :math:`\theta` as changing in time, the sine curve is delayed compared to the cosine.

.. image:: /figs/sine_cosine_wikipedia.png
   :scale: 50 %

The cosine reaches its maximum value of :math:`1` at integer multiples of :math:`2n \pi`, including :math:`0`, while the sine reaches its maximum value at the same values, plus :math:`\pi/2`.

.. math::

    1 = \cos 0 =  \sin \frac{\pi}{2}

or more generally, because the pattern is identical

.. math::

    \cos (\theta - \frac{\pi}{2}) = \sin \theta

On the other hand, if the angle is :math:`\theta = -\pi/2`, then :math:`\sin \theta` is a minimum. The cosine was in the same position when the angle was :math:`-\pi`

.. math::
    
    -1 =  \sin -\frac{\pi}{2} = \cos -\pi

or more generally

.. math::

    \sin (\theta - \frac{\pi}{2}) = \cos (\theta - \pi) =  -\cos \theta

These derivations are the hard part.

Returning to our result for the sum of the cosine, we had

.. math::

    \cos (s + t) = \cos s \cos t - \sin s \sin t

Substitute :math:`t - \pi/2` for :math:`t` and obtain for the left-hand side

.. math::

    \cos (s + t - \frac{\pi}{2} ) = \cos \ [ \ (s + t )- \frac{\pi}{2} \ ] \ = \sin (s + t )

(think of :math:`s+t` as :math:`\theta` and compare with the first formula derived above).  So if we do another manipulation on the right-hand side we can obtain an expression for :math:`\sin s + t`.  

The first term on the right is easy, using the same formula it is just

.. math::

    \cos s \cos (t - \frac{\pi}{2}) = \cos s \sin t

For the second term we have (using the second formula)

.. math::

    - \sin s \sin (t - \frac{\pi}{2}) = - \sin s (- \cos t) = \sin s \cos t

We have now

.. math::

    \sin s + t  = \cos s \sin t + \sin s \cos t

I confess that I find this formulation hard to remember.
