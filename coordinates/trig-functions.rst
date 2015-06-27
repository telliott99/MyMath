.. _trig-functions:

##################
Six trig functions
##################

Consider a unit circle with radius :math:`r=1` and :math:`y = r \sin \theta` and :math:`x = r \cos \theta`.  

Extend the radius through :math:`P` to :math:`Q`, and then draw the vertical connector :math:`a` and horizontal connector :math:`b`.  

.. image:: /figs/sixfuncs1.png
   :scale: 50 %

The drawing contains three similar triangles.  The first is the triangle contained within the circle, with sides :math:`x,y,r`.

Next is the triangle with sides :math:`r,a,OP`, third is the triangle with sides :math:`b,r,OQ`.

.. math::

    x,y,r \sim r,a,OP, \sim b,r,OQ 

By similar :math:`\triangle`

.. math::

    \frac{a}{r} = \frac{y}{x} = \tan \theta 

For the unit circle :math:`r=1` so

.. math::

    a = tan \theta 

This will become important in determining the derivative of the sine function (:ref:`here <lim_x_sinx>`).

If you imagine a point moving around the circle :math:`a` gets very large as :math:`\theta \to \pi/2`, and in fact, becomes :math:`\infty` there.

The segment :math:`OP` is (by similar :math:`\triangle`) to :math:`r` as

.. math::

    \frac{OP}{r} = \frac{r}{x} = \frac{1}{x} 
    
    OP = \frac{1}{\cos \theta}
    
    OP = \sec \theta

The horizontal from the y-axis to Q is labeled :math:`b`.  Consider :math:`\theta` near :math:`Q` at the top of the figure.  By similar :math:`\triangle`

.. math::

    \frac{b}{r} = \frac{x}{y} = \frac{1}{\tan \theta}

since :math:`r = 1`

.. math::
    
    b = \cot \theta 

Finally

.. math::

    \frac{r}{OQ} = \frac{x}{r} = \sin \theta 

    OQ = \csc \theta 


.. image:: /figs/sixfuncs2.png
   :scale: 50 %
