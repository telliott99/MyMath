.. _euler-eqn:

################
Euler's equation
################

Recall that starting from this definition

.. math::

    \frac{d}{dx} e^x = e^x

.. math::

we were able to prove that

.. math::

    \frac{d}{dx} \ln x = \frac{1}{x}

Euler said, let us consider the complex number

.. math::

    z = \cos \theta + i \sin \theta

How did he come up with this?  Because he already knew the answer, I guess.  Let's just see what we can do.  If we assume that calculus is legal with complex numbers (since :math:`i` is *just a number*), we can do the following

.. math::

    \frac{dz}{d \theta} = - \sin \theta + i \cos \theta

And since :math:`i \times i = -1`

.. math::

    \frac{dz}{d \theta} = i*i \sin \theta + i \cos \theta

    \frac{dz}{d \theta} = i(i \sin \theta + \cos \theta)

    \frac{dz}{d \theta} = iz

Rearrange

.. math::

    \frac{1}{z} dz = i d \theta

    \int \frac{1}{z} dz = \int i d \theta

    \ln z = i \theta

Exponentiate:

.. math::

    z = e^{i \theta}

    e^{i \theta} = \cos \theta + i \sin \theta

Euler's famous result, which he proved more rigorously by different approaches.

We used it to get something useful for calculus (:ref:`here <cosine_s+t>`).  

======================
Additional derivations
======================

Here are sketches of two different derivations of Euler's famous formula, both following Dunham's book about Euler.

.. math::

    e^{i\theta} = \cos \theta + i \sin \theta

And of course, if :math:`\theta = \pi`, we have

.. math::

    e^{i\pi} = -1 + 0

    e^{i\pi}+ 1 = 0

(what Feynman called "our jewel").

Using :math:`x` is a bit simpler notation, so that's what I'll do here

.. math::

    e^{ix} = \cos x + i \sin x

+++++++++++
preliminary
+++++++++++

Start with the definition of :math:`i`

.. math::

    i = \sqrt{-1}

Having :math:`i` gives us new factorizations like

.. math::

    a^2 + b^2 = (a + bi)(a - bi)

since the terms with :math:`\pm \ abi` cancel and :math:`- i^2 = 1`.  
So

.. math::

    1 = \cos^2 x + \sin^2 x

    1 = (\cos x + i \sin x) (\cos x - i \sin x)

(Of course, we could switch sine and cosine here, but this is the convention.

Now

.. math::

    1 = e^{ix} \ e^{-ix}

So combining:

.. math::

    e^{ix} \ e^{-ix} = 1 = (\cos x + i \sin x) (\cos x - i \sin x)
    
which, while not a proof, is certainly suggestive.

Below, we will need the above plus one more identity involving :math:`i`:

.. math::

    -i^2 = 1

so

.. math::

    u = - i^2 u

    \frac{u}{i} = - i u

+++
one
+++

Start with the inverse sine function:

.. math::

    x = \sin^{-1} y

    y = \sin x

    dy = \cos x \ dx

Then the side adjacent to :math:`y` is :math:`\sqrt{1-y^2}` and so

.. math::

    \cos x = \sqrt{1-y^2}

We're interested in the integral

.. math::

    \int \frac{1}{\sqrt{1-y^2}} \ dy

which is just

.. math::

    = \int \frac{1}{\cos x} \ \cos x \ dx = x

Now, Euler makes a complex change of variable

.. math::

    y = iz

    \frac{1}{1-y^2} = \frac{1}{1+z^2}

    x = \int \frac{1}{1 - y^2} \ dy

    = \int \frac{1}{\sqrt{1 + z^2}} \ i \ dz

we have converted the integral to having a plus sign under the square root and the answer is

.. math::

    = i \ln \ (\sqrt{{1 + z^2}} + z)

(I will justify this at the end of this chapter---it's a standard trig substitution but a bit tricky ).

Now, just undo the substitution:

.. math::

    z = \frac{y}{i} = \frac{ \sin x}{i}

    \sqrt{1 + z^2} = \sqrt{1 - y^2} = \cos x

Hence our previous result

.. math::

    x = i \ln \ (\sqrt{{1 + z^2}} + z)

is equivalent to

.. math::

    x = i \ln \ (\cos x + \frac{\sin x}{i})

Recall our two identities involving :math:`i`.  The first one was

.. math::

    \frac{u}{i} = - i u

So when we had:

.. math::

    x = i \ln \ (\cos x + \frac{\sin x}{i})

    x = i \ln \ (\cos x - i \sin x)

    ix = - \ln \ (\cos x - i \sin x)

    = \ln \ \frac{1}{(\cos x - i \sin x)}

again

.. math::

    \frac{1}{\cos u - i \sin u} = \cos u + i \sin u

so

.. math::

    ix = \ln \ \frac{1}{(\cos x - i \sin x)}  = \ln \ (\cos x + i \sin x)

Just exponentiate:

.. math::

    e^{ix} = \cos x + i \sin x

+++
two
+++

Suppose we try this multiplication:

.. math::

    (\cos s + i \sin s) (\cos t + i \sin t)

    = \cos s \cos t + i \sin s \cos t + i \cos s \sin t - \sin s \sin t

    = (\cos s \cos t - \sin s \sin t) + i (\sin s \cos t + \cos s \sin t)

    = \cos (s+t) + i \sin(s + t)

set :math:`s=t`

.. math::

    (\cos s + i \sin s)^2 = \cos 2s + i \sin 2s 

In fact, Euler showed that it works for fractional :math:`n` but I'll assume that part.

.. math::

    (\cos s + i \sin s)^n = \cos ns  + i \sin ns

Now multiply the difference rather than the sum:

.. math::

    (\cos s - i \sin s) (\cos t - i \sin t) 

    = (\cos s \cos t - \sin s \sin t ) - i (\sin s \cos t + \sin t \cos s)

    = \cos(s+t) - i (\sin (s + t))

again, with :math:`s=t`

.. math::

    ( \cos s - i \sin s)^2 = \cos 2s - i sin 2s
    
    \cos s - i \sin s)^n = \cos ns - i sin ns

Restate the two results:

.. math::

    (\cos s + i \sin s)^n = \cos ns  + i \sin ns

    ( \cos s - i \sin s)^n = \cos ns - i sin ns

Add them

.. math::

    2 \cos ns = (\cos s + i \sin s)^n + ( \cos s - i \sin s)^n

=======================
where the magic happens
=======================

Let 

.. math::

    s = \frac{x}{n}

As :math:`n \rightarrow \infty`, :math:`s \rightarrow 0`, and 

.. math::

    \sin s \rightarrow s

    \cos s \rightarrow 1

    \cos x  = \cos ns

    = \frac{1}{2} \ [ \  (\cos s + i \sin s)^n + ( \cos s - i \sin s)^n \ ]

    = \frac{1}{2} \  [ \ (1 + i s)^n + (1 - i s)^n \ ]

    = \frac{1}{2} \ [ \ (1 + \frac{ix}{n})^n + (1 - \frac{ix}{n})^n \ ]

but

.. math::

    e^{ix} = (1 + \frac{ix}{n})^n

hence

.. math::

    \cos x  = \frac{1}{2} \ [ \ e^{ix} + e^{-ix} \ ]

By very similar manipulation to what's in the first part we can also obtain an expression for the sine:

.. math::

    2i \ \sin(ns) = (\cos s + i \sin s)^n - (\cos s - i \sin s)^n

which will lead to

.. math::

    \sin x = \frac{1}{2i} \ (e^{ix} - e^{-ix})

Adding together

.. math::

    2(\cos x + i \sin x) = e^{ix} + e^{-ix} + e^{ix} - e^{-ix}

    \cos x + i \sin x = e^{ix}

+++++
check
+++++

Before quitting, we should check the formula.  One way is to notice the connection between infinite series expansions for :math:`e^x`:

.. math::

    e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}  =  1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} \dots

and sine:

.. math::

    \sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} \dots

and cosine:

.. math::

    \cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} \dots

These can almost be added together to give what we seek, except for the problem of the alternating signs.  What happens with :math:`e^{ix}`?

.. math::

    e^{ix} =  1 + ix + \frac{i^2x^2}{2!} + \frac{i^3x^3}{3!} + \frac{i^4x^4}{4!} \dots
    
    = 1 + ix - \frac{x^2}{2!} - i  \frac{x^3}{3!} + \frac{x^4}{4!} \dots

The pattern is 

.. math::

    \sum_{n=0}^{\infty} i^n = 1 + i - 1 - i + 1 \dots

And we're there.  We just have to recognize that the pattern with :math:`e^{ix}` has :math:`i \sin x` so as we said

.. math::

    e^{ix} = \cos x + i \sin x

====================================
Exponential forms of sine and cosine
====================================

.. math::

    e^{i \theta} = \cos \theta + i \sin \theta

Now

.. math::

    e^{-i \theta} = \cos -\theta + -i \sin \theta

    = \cos \theta + -i \sin \theta

By addition, then

.. math::

    e^{i \theta} + e^{-i \theta} = 2 \cos \theta
 
    \frac{1}{2}(e^{i \theta} + e^{-i \theta}) = \cos \theta

And by subtraction

.. math::

    e^{i \theta} - e^{-i \theta} = 2i \cos \theta

    \frac{1}{2i}(e^{i \theta} - e^{-i \theta}) = \sin \theta

All of the familiar relationships hold.  In particular

.. math::

    \frac{d}{d\theta} \ \cos \theta = \frac{d}{d\theta} \ \frac{1}{2}(e^{i \theta} + e^{-i \theta})

    = \frac{1}{2}i(e^{i\theta} - e^{-i \theta}) = -\frac{1}{2i}(e^{i\theta} - e^{-i \theta}) = - \sin \theta

    \frac{d}{d\theta} \ \sin \theta = \frac{d}{d\theta} \ \frac{1}{2i}(e^{i \theta} - e^{-i \theta})

    = \frac{1}{2}(e^{\theta} + e^{-i \theta}) = \cos \theta

Finally, (since :math:`e^{i \theta} e^{-i \theta} = 1`):

.. math::

    \sin^2 \theta = -\frac{1}{4}(e^{i \theta} - e^{-i \theta})^2 = -\frac{1}{4}(e^{2i \theta} - 2 + e^{-2i \theta} )

    \cos^2 \theta = \frac{1}{4}(e^{i \theta} + e^{-i \theta})^2 = \frac{1}{4}(e^{2i \theta} + 2 + e^{-2i \theta} )

If you follow the signs carefully, you will see that summing the last two equations just gives :math:`1`.

========
Integral
========

A fact we needed in deriving Euler's formula was the value of a particular integral:

.. math::

    \int \frac{1}{\sqrt{1 + x^2}} \ dx

Let :math:`x/1 = \tan t`, then the hypotenuse is 

.. math::

    \sqrt{1 + x^2} = \sec t
    
and 

.. math::

    dx = \sec^2 t \ dt
    
the integral is then

.. math::

    \int \sec t \ dt
    
    = \ln |\sec t + \tan t|
    
    = \ln |x + \sqrt{1 + x^2}|

Check by differentiating the answer:

.. math::
    
    \frac{d}{dx} \ln |x + \sqrt{1 + x^2}|
    
    = \frac{1}{x + \sqrt{1 + x^2}} (1 + \frac{2x}{2 \sqrt{1 + x^2}})
    
    = \frac{1}{x + \sqrt{1 + x^2}}  (1 + \frac{x}{\sqrt{1 + x^2}})

    =  \frac{1}{x + \sqrt{1 + x^2}}  (\frac{\sqrt{1 + x^2} + x}{\sqrt{1 + x^2}})
    
    = \frac{1}{\sqrt{1 + x^2}}

which is correct.