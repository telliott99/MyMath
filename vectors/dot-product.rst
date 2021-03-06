.. _dot-product:

###########
Dot Product
###########

The *dot product* is one of two ways to "multiply" two vectors together (the other way being the *cross product*).  The dot product is easy to compute, and it measures something fundamental---the angle between the two vectors.  

Two very useful properties are first, that the dot product is zero when two vectors are orthogonal (perpendicular) to one another.  And second:  the dot product of any vector with a *unit vector* (vector of length one), measures the component of that vector that is in the same direction as the unit vector.  This works for any unit vector, not just the standard "basis".

Define two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}`:

.. math::

    \mathbf{a} = \ \langle a_1,a_2 \rangle

    \mathbf{b} = \ \langle b_1,b_2 \rangle

Geometrically, we might think of these as being one vector extending from the origin in the :math:`x,y`-plane to the point :math:`(a_1,a_2)`, and the other vector extending from the origin to :math:`(b_1,b_2)`.

The dot product is **the sum of the products of the individual terms**:

.. math::

    \mathbf{a} \cdot \mathbf{b} = a_1 b_1 + a_2 b_2

We can extend this to a pair of vectors in :math:`n`-dimensional space

.. math::

    \mathbf{a} = \ \langle a_1,a_2, \dots a_n \rangle

    \mathbf{b} = \ \langle b_1,b_2, \dots b_n \rangle

    \mathbf{a} \cdot \mathbf{b} = a_1 b_1 + a_2 b_2 + \dots + a_n b_n
    
     = \sum_i a_i b_i 

The dot product of two vectors is a number, in vector terminology it is a *scalar*.  The result may be positive, negative or even zero.

Notice that the two vectors being multiplied (whose dot product is computed) must have the same dimension, the same :math:`n`.  Also, the fact that the result of the multiplication---the dot product---is a number is in contrast to the other form of vector multiplication (the cross-product) which yields a vector as the result.

========
Examples
========

.. math::

    \mathbf{\hat{i}} = \langle 1, 0 \rangle

    \mathbf{\hat{i}} \cdot \mathbf{\hat{i}} = (1)(1) + (0)(0) = 1

    \mathbf{v} = \langle v_1, v_2 \rangle
    
    \mathbf{v} \cdot  \mathbf{\hat{i}} = (v_1)(1) + (v_2)(0) = v_1
    
    \mathbf{u} = \mathbf{\hat{i}} + \mathbf{\hat{j}} = \langle 1,1 \rangle
    

===============
Some properties
===============

The dot product obeys the same rules as operations on real numbers:  it is associative, commutative and distributive.  You can easily verify these properties by computing each term of the respective products.

**Commutative**:

.. math::

    \mathbf{a} \cdot \mathbf{b} = \mathbf{b} \cdot \mathbf{a}
    
Proof:

.. math::

    \mathbf{a} \cdot \mathbf{b} = \sum_i a_i b_i
    
    = a_1 b_1 + a_2 b_2 + \dots a_n b_n
    
    = b_1 a_1 + b_2 a_2 + \dots + b_n a_n
    
    = = \sum_i b_i a_i
    
    = \mathbf{b} \cdot \mathbf{a}

**Associative**:

Suppose

.. math::

    \mathbf{b} = \mathbf{c} + \mathbf{d}

Then 

.. math::

    \mathbf{a} \cdot \mathbf{b} =  \mathbf{a} \cdot ( \mathbf{c} + \mathbf{d}) = \mathbf{a} \cdot \mathbf{c} + \mathbf{a} \cdot \mathbf{d}

Proof:

.. math::

    \mathbf{c} + \mathbf{d} = \ \langle c_1 + d_1, c_2 + d_2, \ \dots c_n + d_n \rangle 

    \mathbf{a} \cdot (\mathbf{c} + \mathbf{d}) = a_1 (c_1 + d_1) + a_2(c_2 + d_2) + \dots + a_n (c_n + d_n) 

    =  a_1 c_1 + a_1 d_1 + a_2 c_2 + a_2 d_2 + \dots + a_n c_n + a_n d_n

    =  a_1 c_1 + a_2 c_2 + \dots + a_n c_n + a_1 d_1 + a_2 d_2 + \dots + a_n d_n

    = \mathbf{a} \cdot \mathbf{c} + \mathbf{a} \cdot \mathbf{d}

A last example that we will need below is

.. math::

    ( \mathbf{a} -  \mathbf{b}) \cdot ( \mathbf{a} -  \mathbf{b}) =  \mathbf{a} \cdot \mathbf{a} -  \mathbf{a} \cdot \mathbf{b} -  \mathbf{b} \cdot \mathbf{a} +  \mathbf{b} \cdot \mathbf{b}
    
    = \mathbf{a} \cdot \mathbf{a} + \mathbf{b} \cdot \mathbf{b} - 2 \ \mathbf{a} \cdot \mathbf{b}
    
Proof:

.. math::

    ( \mathbf{a} -  \mathbf{b}) = \langle a_1 - b_1, a_2 - b_2, \ \dots a_n - b_n \rangle
    
    ( \mathbf{a} -  \mathbf{b}) \cdot ( \mathbf{a} -  \mathbf{b}) = (a_1 - b_1)^2 + (a_2 - b_2)^2 + \dots + (a_n - b_n)^2 
    
    = a_1^2 - 2a_1b_1 + b_1^2 + a_2^2 - 2a_2b_2 + b_2^2 + \dots + a_n^2 - 2a_nb_n + b_n^2
    
    = a_1^2 + a_2^2 + \dots + a_n^2 + b_1^2 + b_2^2 + \dots + b_n^2 - 2 (a_1 b_1 + a_2 b_2 + \dots + a_n b_n)
    
    = \mathbf{a} \cdot \mathbf{a} +  \mathbf{b} \cdot \mathbf{b}  - 2 \ \mathbf{a} \cdot \mathbf{b}

=====================
Relation to the angle
=====================

Now for the main idea of the dot product.  Suppose we draw two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}` in :math:`\mathbb{R}^2` with their tails at the same point.  Designate the angle between them as :math:`\theta` and the vector representing the side opposite as :math:`\mathbf{c}`. 

.. image:: /figs/dot1.png
   :scale: 50 % 

The orientation of  :math:`\mathbf{c}` doesn't matter for the argument that follows.  As shown

.. math::

    \mathbf{b} + \mathbf{c} = \mathbf{a}

    \mathbf{c} = \mathbf{a} - \mathbf{b}

Compute the dot product of :math:`\mathbf{c}` with itself

.. math::

    \mathbf{c} \cdot \mathbf{c} = ( \mathbf{a} -  \mathbf{b}) \cdot ( \mathbf{a} -  \mathbf{b})

Recalling the result from above, this is equal to

.. math::

    \mathbf{c} \cdot \mathbf{c} = \mathbf{a} \cdot \mathbf{a} +  \mathbf{b} \cdot \mathbf{b}  - 2 \ \mathbf{a} \cdot \mathbf{b}

Since 

.. math::

    |\mathbf{a}|^2 = \mathbf{a} \cdot \mathbf{a} = a^2

and so on, we have that

.. math::

    \mathbf{c} \cdot \mathbf{c} =  \mathbf{a} \cdot \mathbf{a} +  \mathbf{b} \cdot \mathbf{b}  - 2 \ \mathbf{a} \cdot \mathbf{b}

    c^2 =  a^2 + b^2  - 2  \ \mathbf{a} \cdot \mathbf{b}

Does this remind you of the *Law of Cosines*?  (See :ref:`here <law-of-cosines>`).

In ordinary trigonometry, we designate the lengths of a triangle's sides as :math:`a,b,c` and the angle between sides :math:`a` and :math:`b` as :math:`\theta` and the law says that

.. math::

    c^2 = a^2 + b^2 - 2 a b \cos \theta

Comparing the two equations, we see that

.. math::

    \mathbf{a} \cdot \mathbf{b} = a b \ \cos \theta
    
    = |\mathbf{a}| \ |\mathbf{b}| \ \cos \theta

This relationship is extremely useful because it allows us to compute the cosine of the included angle via the dot product.  Even more important, two vectors which are perpendicular will have :math:`\cos \theta = 0`, so their dot product is zero.  And although we haven't proved it, this result extends to vectors in :math:`\mathbb{R}^n`.

For example, suppose I have the vector

.. math::

    \mathbf{u} = \ \langle p,q \rangle

How can I find a vector :math:`\mathbf{v}` perpendicular to :math:`\mathbf{u}`?  Simple

.. math::

    \mathbf{v} = \ \langle q,-p \rangle

:math:`\mathbf{v}` is perpendicular to :math:`\mathbf{u}` because

.. math::

    \mathbf{u} \cdot \mathbf{v} = pq + -qp = 0

In disguise, this is the rule from Algebra I that a perpendicular line has slope which is the negative inverse of m:  :math:`\frac{1}{4}` has negative inverse :math:`-4`.  If we have the equations for two lines

.. math::

    y = \frac{p}{q} x + b

    y = -\frac{q}{p} x + c

We know these two lines are perpendicular to one another.

How to find a vector in :math:`\mathbb{R}^5` perpendicular to :math:`\langle 1,1,1,1,0 \rangle`?

Any vector of the form :math:`\langle 0,0,0,0,k \rangle` will do, where :math:`k` is some real number.

For more about the angle, go back to elementary geometry:

.. math::
    
    \mathbf{u} = \mathbf{\hat{i}} + \mathbf{\hat{j}} = \langle 1,1 \rangle
    
    u = | \mathbf{u} | = \sqrt{2}
    
    \mathbf{u} \cdot \mathbf{i} = 1 = u \cos \theta
    
    \cos \theta = \frac{1}{\sqrt{2}}
    
similarly

.. math::
    
    \mathbf{w} = \langle 1, \sqrt{3} \rangle
    
    w = | \mathbf{w} | = \sqrt{4} = 2
    
    \mathbf{w} \cdot \mathbf{i} = 1 = w \cos \theta
    
    \cos \theta = \frac{1}{2}

=======================================
Alternate derivation of the dot product
=======================================

Here is another approach which doesn't depend on knowing the law of cosines, but instead requires the rule for subtraction of cosines

.. math::

    \cos (\theta - \phi) = \cos \theta \cos \phi + \sin \theta \sin \phi

Go back to the previous figure

.. image:: /figs/dot1.png
   :scale: 50 % 

but now imagine that the vector :math:`\mathbf{a}` forms an angle :math:`\theta_a` with the :math:`x`-axis and similarly, :math:`\mathbf{b}` forms an angle :math:`\theta_b` with the :math:`x`-axis.

If we turn the vector :math:`\mathbf{a}`, then the component of :math:`\mathbf{a}` that lies along the :math:`x`-axis is :math:`a \cos \theta_a` (where :math:`a` is the length of :math:`\mathbf{a}`).  And in a similar vein

.. math::

    a_x = a \cos \theta_a

    b_x = b \cos \theta_b

    a_y = a \sin \theta_a

    b_y = b \sin \theta_b

We said that the definition of the dot product is

.. math::

    \mathbf{a} \cdot \mathbf{b} = a_x b_x + a_y b_y

    = a \cos \theta_a b \cos \theta_b + a \sin \theta_a b \sin \theta_b

    = ab (\cos \theta_a \cos \theta_b + \sin \theta_a \sin \theta_b)

using the subtraction rule this is just

.. math::

    = ab \cos (\theta_a - \theta_b)

but since :math:`\theta = \theta_a - \theta_b`

.. math::

    \mathbf{a} \cdot \mathbf{b} = ab \cos \theta
