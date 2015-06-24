.. _complex2:

###########
Computation
###########

Fitzpatrick's book on Mechanics (Chapter 7) uses complex numbers in differentiation of the position vector :math:`\mathbf{r}` for a particle.  Define a unit vector :math:`\mathbf{e}_r` in the direction of :math:`\mathbf{r}`

.. math::

    \mathbf{r} = r \mathbf{e}_r 

    \mathbf{v} = \dot{\mathbf{r}} = \dot{r} \mathbf{e}_r + r \dot{\mathbf{e}_r} 

and the question is, what is :math:`\dot{\mathbf{e}_r}`?

The use of complex numbers to evaluate this is, he says, "a famous trick."  The idea is to think of \[ e^{i\theta} = \cos \theta + i \sin \theta \]

as representing the radial unit vector :math:`\mathbf{e}_r`.  It's a unit vector because the rule for evaluation is that the length is

.. math::

    |\mathbf{v} | = \sqrt{\cos^2 \theta + \sin^2 \theta} 

We require :math:`\mathbf{e}_{\theta} \perp  \mathbf{e}_r`.  Well, if

.. math::

    \mathbf{e}_{\theta} = i \mathbf{e}_r 

    \mathbf{e}_{\theta} = ie^{i\theta} = i\cos \theta - \sin \theta 

it is still unit length and looking at his diagram

.. image:: /figs/Fitzpatrick1.png
   :scale: 50 %

it's clear that they are orthogonal.  If you do the dot product

.. math::

    \mathbf{e}_{\theta} \cdot  \mathbf{e}_r = (\cos \theta + i \sin \theta) \cdot ( i\cos \theta - \sin \theta) 

and, as long as you think of the :math:`i` as part of the unit vector, it works.

So now we have some position vector

.. math::

    z = r e^{i \theta} 

we differentiate and obtain

.. math::

    \dot{z} = \dot{r} e^{i\theta} + r \dot{\theta} i e^{i \theta} 

    = \dot{r} \mathbf{e}_r +  r \dot{\theta} \mathbf{e}_{\theta} 

what this means is that the velocity has two components, the radial velocity

.. math::

    \mathbf{v}_r = \dot{r} \mathbf{e}_r  

and the tangential velocity

.. math::

    \mathbf{v}_{\theta} =  r \dot{\theta} = r \omega 

Just so you are not thinking this is no big deal (see UCM) the great thing here is that we have not assumed that the velocity is perpendicular to the position vector.  It is a general result.  And in the case where :math:`\dot{r} = 0`, we get the standard results.

Furthermore, we can do the acceleration in an analogous way.

.. math::

    \dot{z} = \dot{r} e^{i\theta} + r \dot{\theta} i e^{i \theta} 

    \ddot{z} = \dot{r}(\frac{d}{dt} e^{i\theta} ) +  \ddot{r}  e^{i\theta} + \dot{r} \dot{\theta} i e^{i \theta} +  r \ddot{\theta} i e^{i \theta} +  r \dot{\theta} i (\frac{d}{dt} e^{i\theta} )    

    = \dot{r} \dot{\theta} i e^{i \theta}  +  \ddot{r}  e^{i\theta} + \dot{r} \dot{\theta} i e^{i \theta} +  r \ddot{\theta} i e^{i \theta} +  r \dot{\theta} i  \dot{\theta} i e^{i \theta}    

    = (\ddot{r} - \dot{r} \dot{\theta}^2) e^{i\theta} + (2 \dot{r} \dot{\theta}  + \dot{r} \ddot{\theta}) i e^{i \theta}  

In other words, the acceleration has two components, the radial component

.. math::

    \mathbf{a}_r = (\ddot{r} - \dot{r} \dot{\theta}^2) e^{i\theta} = (\ddot{r} - \dot{r} \dot{\theta}^2) \mathbf{e}_r = \ddot{r} - r \omega^2 

and the tangential component

.. math::

    \mathbf{a}_{\theta} =  \dot{r} \ddot{\theta} + 2 \dot{r} \dot{\theta} = r \dot{\omega} + 2 \dot{r} \omega  

For UCM, then :math:`\dot{r} = 0` and

.. math::

    \mathbf{a}_r = - r \omega^2 

    \mathbf{a}_{\theta} =  r \dot{\omega}  
