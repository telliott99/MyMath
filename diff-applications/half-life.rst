.. _half-life:

#########
Half-life
#########

A sample of radioactive phosphate containing the isotope :sup:`32`\ P decays with a half-life of just over :math:`14` days (:math:`14.29`, to be more precise).  

If you want to solve a problem where you are given a certain amount of some unstable isotope :math:`N_o` at time-zero (:math:`t=0`), and you are asked for the amount at time :math:`t`, what do you do?  If the time is an even multiple of the half-life, it's easy.  For one half-life, multiply by :math:`\frac{1}{2}`, for two half-lives multiply by :math:`\frac{1}{4}`, for :math:`n` half-lives multiply by :math:`(\frac{1}{2})^n`.

If the time is not an even multiple of the half-life, you need two equations (where :math:`T` is the half-life and :math:`k` is a rate constant)

.. math::

    kT = \ln 2  = 0.693

    N = N_o \ e^{-kt}

I want to show where these equations come from.  When studying the exponential function in calculus, we learn two equivalent definitions.  The first is that :math:`\frac{d}{dx} \ e^x = e^x`.  The second is that :math:`\frac{d}{dx} \ \ln(x) = \frac{1}{x}`, or 

.. math::

    \int \frac{1}{x} \ dx = \ln(x)

In radioactive decay, each atom has a fixed probability of disintegrating in the next short time interval :math:`dt`.  This is the crucial feature as far as the math is concerned:  the change during a short period is proportional to the number of molecules present (:math:`N`).

The probability varies for different types of radioactive nucleus (:sup:`3`\ H, :sup:`14`\ C, :sup:`238`\ U, etc.), but for each phosphorus atom in our sample of :sup:`32`\ P it is the same.  As a result, the number of atoms :math:`dN` that will disintegrate or decay in the short time :math:`dt` is proportional to :math:`N`, the number currently present.  A fixed fraction of all the atoms will be transformed.  We write

.. math::

    dN = k N dt

Rearrange and integrate

.. math::

    \int \frac{dN}{N} = \int k \ dt

The answer is just

.. math::

    \ln(N) = kt + C_0

Form the exponential on both sides

.. math::

    N = Ce^kt

(:math:`C = e^{C_0}`).  We evaluate the constant :math:`C` by setting :math:`t=0` and find that :math:`C = N_o` so

.. math::

    N = N_o \ e^{kt}

Finally, for decay problems it is usual to let :math:`k` be positive and introduce a minus sign

.. math::

    N = N_o \ e^{-kt}

The other equation given above was

.. math::

    kT = \ln 2 = 0.693

This is very useful to remember, because frequently we are given a half-life :math:`T` and asked to compute using the  equation with :math:`e^{-kt}`.  It will save time to convert :math:`T` to :math:`k` quickly.  

The derivation is as follows.  By definition, after one half-life has elapsed, when the time :math:`t = T`, :math:`N = N_o/2`.

.. math::

    \frac{N_o}{2} = N_o \ e^{-kT}

    \frac{1}{2} =  \ e^{-kT}

    2 =  \ e^{kT}

    \ln 2 =  \ kT

Equations for the growth of populations work similarly, with 

.. math::

    N = N_o \ e^{kt}

and again, if the problem gives you an even number of doublings, or generations, just use that.