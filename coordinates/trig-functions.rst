six_functions

#############
Six_functions
#############

Consider a unit circle with radius :math:`r=1` and :math:`y/r = sin\ \theta` and :math:`x/r = cos\ \theta`.  Extend the radius with the angle :math:`\theta` and then draw the vertical connector :math:`a` and horizontal connector :math:`b`.  The original triangle with sides :math:`x,y,r` is similar to the triangle with sides :math:`r,a,OP`, and both are similar to the triangle with sides :math:`b,r,OQ`.

.. math::

    x,y,r \sim r,a,OP, \sim b,r,OQ 


By similar :math:`\triangle`

.. math::

    a/r = y/x = tan \ \theta 


But :math:`r=1` so

.. math::

    a = tan \ \theta 


If you imagine a point moving around the circle :math:`a` will get very large as :math:`\theta \to \pi/2`, and in fact, becomes :math:`\infty` there.

\vspace {2 mm}

\noindent The segment :math:`OP` is (by similar :math:`\triangle`) to :math:`a` as

.. math::

    OP/a = r/y = 1/y = 1/cos\ \theta = sec\ \theta 


The horizontal from the y-axis to Q is :math:`b`.  Consider :math:`\theta` near the top of the figure.  By similar :math:`\triangle`, the relations we had were

.. math::

    x,y,r \sim r,a,OP, \sim b,r,OQ 


    r/b = y/x = tan \ \theta  


since :math:`r = 1`

.. math::

    b = r/tan \ \theta = 1/tan \ \theta = cot \ \theta 


%\[ b/OQ = cos\  \theta \]

Finally

.. math::

    r/OQ = 1/OQ = sin \ \theta 


    OQ = 1/sin \ \theta = csc\ \theta 


.. image:: /figs/sixfuncs1.png
   :scale: 50 %

.. image:: /figs/sixfuncs2.png
   :scale: 50 %

Note:  the above diagram has an error, sine and cosine are switched.  I have to find the original figure (or redraw) to change this.
