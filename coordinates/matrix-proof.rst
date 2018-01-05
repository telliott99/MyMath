.. _matrix-proof:

############
Matrix proof
############

I have another easy derivation for you, if you know something about multiplying a matrix times a vector.  If you want some review, there is a chapter in the supplementary material :ref:`here <vectors-matrices>`.

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
    
Following the rules for matrix multiplication (row :math:`\times` column, :ref:`here <vectors-matrices>`), we can deduce all four equations:

.. math::

    \cos \theta + \phi = \cos \theta \cos \phi - \sin \theta \sin \phi

    \cos \theta - \phi = \cos \theta \cos \phi + \sin \theta \sin \phi

    \sin \theta + \phi = \sin \theta \cos \phi + \cos \theta \sin \phi

    \sin \theta - \phi = \sin \theta \cos \phi - \cos \theta \sin \phi
