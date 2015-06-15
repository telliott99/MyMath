.. _cosine_s+t:

###############
Cosine of s + t
###############

===================
Starting from Euler
===================

There are several very useful formulas that follow from knowing how to compute the sine or cosine of the sum and difference of two angles, which might be labeled :math:`\theta` and :math:`\phi`, or :math:`\alpha` and :math:`\beta`, but which I usually just call :math:`s` and :math:`t`.

A particularly quick and simple derivation depends on :ref:`Euler's equation<euler-eqn>`, which you may have seen before.

.. math::

    e^{i\theta} = \cos \theta + i \sin \theta

The right-hand side is clear enough---this is a point in the "complex plane", indexed by the cosine and sine of an angle :math:`\theta` formed by a ray to the point from the origin, and the real (:math:`x`-axis).  

Without worrying too much about how that could possibly equal :math:`e^{i\theta}`, if we substitute :math:`s + t` for :math:`\theta`:

.. math::

    e^{i(s+t)} = \cos (s+t) + i \sin (s+t)

But by the standard rules for exponents

.. math::

    e^{i(s+t)} = e^{is+it} = e^{is} e^{it}
    
    = ( \cos s + i \sin s ) ( \cos t + i \sin t )
    
    = \cos s \cos t - \sin s \sin t + i \sin s \cos t + i \sin t \cos s 
    
The cool thing about this is that for two complex numbers to be equal, *both the real and the imaginary parts must be equal*.  Thus it's two identities for one formula:

.. math::

    \cos (s+t) = \cos s \cos t - \sin s \sin t

    \sin (s+t) = \sin s \cos t + \sin t \cos

This is by far the easiest and best way to reconstruct the addition formulas.

===============
Geometric proof
===============

Suppose we consider a right triangle, with one of the angles labeled :math:`s`.  We can scale this triangle to any size we like, and all the different scaled triangles will be similar to each other, having the third angle complementary to :math:`s`, with sum :math:`s + t` equal to :math:`\pi/2`.

Now construct another right triangle containing angle :math:`t`, and scale it so that the base adjacent to angle :math:`t` is just as long as the hypotenuse of the triangle containing angle :math:`s`, and then draw them next to each other as shown:

.. image:: /figs/sum_angle2.png
       :scale: 25%

The joined triangles are then scaled so that the hypotenuse of the second triangle has unit length.

In addition to this construction, our second crucial insight is to draw vertical and horizontal dotted lines as shown.  Since the vertical line makes a right angle with the base, we have that:

.. math::

    s + t + u = \frac{\pi}{2} =  t + u + v

    s = v

Since I already know the result I am looking for, I write

.. math::

    \cos s + t = \cos s \cos t - \sin s \sin t

By :math:`\cos s + t` is really meant :math:`\cos (s + t)`, but with the parentheses  left off.

Our goal is to verify this eternal truth, using the diagram.  We add some labels to the sides of the triangles and substitute into the above equation, using the figure for reference:

.. image:: /figs/sum_angle.png
       :scale: 25%

From the figure

.. math::

    \cos s = \frac{a+b}{g}; \ \ \ \cos t = \frac{g}{1}; \ \ \ \cos s \cos t = a + b

    \sin s = \frac{b}{h}; \ \ \ \sin t = \frac{h}{1}; \ \ \ \sin s \sin t = b

We calculate:

.. math::

    \cos s \cos t - \sin s \sin t = (a + b) - b

Reading directly from the figure

.. math::
 
    \cos s + t = a = (a + b) - b

    = \cos s \cos t - \sin s \sin t

So we have verified the formula, working backward from it to true statements based on the figure.

As a quick check we can ask what happens to the formula 

.. math::

    \cos s + t = \cos s \cos t - \sin s \sin t

when :math:`t = 0`.  Then the first term is the cosine of :math:`s`, and the second term is equal to :math:`0`.

==================
Extension to minus
==================

The first extension is to the difference :math:`\cos s - t`.  We have

.. math::

    \cos s + (-t) = \cos s \cos (-t) - \sin s \sin (-t)

Now, recall that :math:`\cos -t = \cos t` and :math:`\sin -t = - \sin t`.  

Although it's not a proof, just visualize what happens near :math:`\theta = 0` and then when :math:`\theta` becomes negative).  Or, remember that the sine is an odd function :math:`f(x) = - f(-x)` and the cosine is an even function :math:`f(x) = f(-x)`---cosine is symmetric about the :math:`y`-axis.  Thus

.. math::

    \cos s -t = \cos s \cos t + \sin s \sin t

I like this form because it's easy to verify that if :math:`s=t` then we have :math:`\cos 0 = 1 = \cos^2 s + \sin^2 s = 1`, which is the most famous and useful trig identity.

=================
Extension to sine
=================

Referring back to the diagram 

.. image:: /figs/sum_angle.png
       :scale: 25%

(and again, with our goal clearly in mind)

.. math::

    \sin s =  \frac{c}{g} \ \ \ \  \cos t = \frac{g}{1} \ \ \ \  \sin s \cos t = c

    \sin t = \frac{h}{1} \ \ \ \  \cos s = \frac{d}{h} \ \ \ \ \sin t \cos s = d

But

.. math::

    \sin s + t = c + d =  \sin s \cos t +  \sin t \cos s

Using the even/odd function rules, we obtain

.. math::

    \sin s - t = c - d =  \sin s \cos t -  \sin t \cos s

You should commit all the formulas to memory.  They can easily be used to derive other formulas, like the double-angle formula.

=============================
Alternative extension to sine
=============================

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

I find this formulation extremely hard to remember.

============
Matrix proof
============

I have another easy derivation for you, if you know something about multiplying a matrix times a vector.  

Multiplication by the following matrix rotates any vector :math:`\mathbf{a} = \ \langle x,y \rangle` by :math:`\theta` degrees in the counter-clockwise direction to give vector :math:`\mathbf{b} = \ \langle u,v \rangle`

.. math::
    
    T =
    \begin{bmatrix}
    \cos \theta && -\sin \theta \\
    \sin \theta && \cos \theta
    \end{bmatrix}

For the specific case of rotation by :math:`\theta = \pi/2`, we have

.. math::
    
    T =
    \begin{bmatrix}
    0 && -1 \\
    1 && 0
    \end{bmatrix}

    T \times \langle x,y \rangle = \langle -y, x \rangle

which is indeed rotation by :math:`90` degrees counterclockwise.

If we multiply by the matrix for :math:`\theta` and then multiply again by the matrix for :math:`\phi`, it amounts to rotation by a single matrix for :math:`\theta + \phi`.  That is

.. math::

    \begin{bmatrix}
    \cos \theta &&  -\sin \theta \\
    \sin \theta && \cos \theta
    \end{bmatrix}
    \times
    \begin{bmatrix}
    \cos \phi &&  -\sin \phi \\
    \sin \phi && \cos \phi 
    \end{bmatrix}
    =
    \begin{bmatrix}
    \cos \theta + \phi &&  -\sin \theta + \phi \\
    \sin \theta + \phi && \cos \theta + \phi
    \end{bmatrix}
    
Following the rules for matrix multiplication (row :math:`\times` column)

.. image:: /figs/mm1.png
       :scale: 25%

From this we can deduce all four equations, as one example:

.. math::

    \cos \theta \cos \phi - \sin \theta \sin \phi = \cos \theta + \phi


