.. _strang-sum-angles:

###########################
Stand-alone geometric proof
###########################

Here is a proof from Strang's *Calculus*.

.. image:: /figs/strang-sum.png
   :scale: 50 % 

It is simple and geometric, but does not require a fancy setup.

In the left panel of the figure we have angle :math:`t` and angle :math:`s`, while the red triangle is drawn containing the angle which is the difference :math:`s-t`.

Also shown are two points, one has coordinates :math:`\cos s, \sin s` and the other has coordinates :math:`\cos t, \sin t`, as well as the distance between them :math:`d` which is computed as :math:`d^2`:

.. math::

    d^2 = (\cos s - \cos t)^2 + (\sin s - \sin t)^2
    
    = \cos^2 s - 2 \cos s \cos t + \cos^2 t + \sin^2 s - 2 \sin s \sin t + \sin^2 t
    
    = 2 - 2 \cos s \cos t - 2 \sin s \sin t

In the right panel, the triangle has been rotated, preserving the same relationships, but now we see that the point labeled :math:`x,y` is :math:`\cos (s-t), \sin (s-t)`.  And the distance :math:`d` is now the distance from that point to :math:`(1,0)`.  So 

.. math::

    d^2 = (\cos (s-t) - 1)^2 + \sin^2 (s-t)
    
    = \cos^2 (s-t) - 2 \cos (s-t) + 1 + \sin^2 (s-t)
    
    = 2 - 2 \cos (s-t)
    

It's the same distance :math:`d` in both figures so we can equate them

.. math::

    2 - 2 \cos (s-t) = 2 - 2 \cos s \cos t - 2 \sin s \sin t
    
    \cos (s-t) = \cos s \cos t + \sin s \sin t

