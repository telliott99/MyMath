.. _hyperbola:

#########
Hyperbola
#########

Here is a hyperbola as shown in the wikipedia article on the subject.

.. image:: /figs/hyper.png
   :scale: 50 %

Hyperbolas of this type (that open "east-west") have equations of the form

.. math::

    \frac{x^2}{a^2} - \frac{y^2}{b^2} = 1

We can see that 

.. math::

    \frac{x^2}{a^2} = 1 + \frac{y^2}{b^2}

so that the minimum value of :math:`x` occurs when :math:`y=0` and :math:`x=a`.  The conjugate hyperbola of this one is

.. math::

    \frac{x^2}{a^2} - \frac{y^2}{b^2} = -1

or equivalently 

.. math::

    -\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

opens "north-south."  And, although I want to wait to deal with this complication, we have to mention another very common hyperbola

.. math::

    xy = c

(for details see here).

where it must be true that :math:`x \ne 0` and :math:`y \ne 0`.

Another feature of hyperbolas is the asymptote, the straight line which is approached when :math:`x,y >> a,b`.  In the case of the first example

.. math::

    \frac{y^2}{b^2} = \frac{x^2}{a^2} - 1

    y^2 = \frac{b^2}{a^2} x^2 - \frac{1}{a^2}

    y^2 = \frac{1}{a^2} (b^2x^2 - 1)

but for large :math:`x` this approaches

.. math::

    \frac{b^2}{a^2} x^2

so

.. math::

    y = \pm \frac{b}{a} x
