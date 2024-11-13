# Jupiter initial ("Wulff") results

To all Jupiter enthusiasts named Matt, Geoff, Nic, Adrian VK, and Neil (others are welcome, but you likely won't know about this repository):

In this Github repository, I am in the process of compiling the main results of the global Jupiter models I’ve been running. I am starting with just two models to get us going (especially since Geoff needs plots by tomorrow, 13 November 2024). 

All models in this "Wulff" suite have:

Aspect ratio (r_in/r_out = 0.8, r_in = 4, r_out = 5)
1.2 density scale heights across the convection zone (CZ): density contrast of 
Adiabatic, hydrostatic background polytrope with n = 2 (rho ~ T^2)
Constant thermal conductivity and kinematic viscosity (Pr = nu/kappa = 1/2)
For models with a weather layer (WL), the simulation extends into a stable layer atop the CZ. This stable layer has:
Aspect ratio of 1/4, or (r_out - r_0)/(r_0 - r_in) = 0.25, where r_0 is the boundary between CZ and WL
Transition in N^2 of width 0.05*H, where H is the CZ thickness. 

Most models (including the weather layer models) have one spherically symmetric, time-independent heating layer at the base of the convective layer and similarly one cooling layer at the top (equal and opposite volume integrals), each of width 0.1x the shell depth. 

To make contact with the original Wulff et al. 2022 results, there are also two CZ-only cases run with a distributed heating across the CZ and either a fixed entropy (FE) top or fixed flux (FF) top. 

The results are reported nondimensionally, with 
Length scale = shell depth (call the dimensional shell depth H)
Time scale = viscous diffusion time (tau = H^2/nu)
Velocity scale = H/tau
Reference state profiles scaled by their values at the inner radius
Pressure perturbation scale = dynamic pressure (rho * H^2/tau^2)
Entropy perturbation scale = (Delta S) = F * H / (rho * T * kappa)
…where F is the heat flux conduction and convection must carry in equilibrium (i.e., any flux NOT associated with the heating layers). F, rho, and T, etc. are the volume averages over the CZ only. 

The control parameters that are varied are only the Rayleigh number Ra and convective Rossby number Ro_c (defining a 2D grid). These are defined as follows:

Ra = (Delta S/C_p) * g_in H^3 / (nu * kappa)

Ek = nu / (2*Omega*H^2) (with Omega being the frame rotation rate, note the 2); note that Ek is only varied tangentially as part of varying Ra and Ro_c

Ro_c = sqrt(Ra*Ek^2/Pr) = sqrt [ (Delta S/C_p) * g_in / (H * 4 * Omega^2)  ]

For the other control parameters,

Pr = 0.5

and

sigma = 3 (this implies N ~ 8 \Omega). 

The subfolders containing plots and info about each run are labeled

Roc[###]_Ra[###]

For the original Wulff case (interpreting her paper), it was 

Ro_c = 0.14
Ra = 4.9 x 10^6

Note that Loren messed up nondimensionalization along the way, and so the only current simulation pair with both a CZ-only case and WL counterpart has

Ro_c = 0.20
Ra = 10^7

This is not truly a Wulff analogue but so far what we have to work with. 

Some helpful conversions of timescales:
1 viscous diffusion time = 0.11 x Ra^(1/2) / Ro_c rotations
E.g., for Ra = 4.9 x 10^6, Ro_c = 0.14, 1 VDT = 1,740 rotations

1 thermal diffusion time = 1/2 VDT (since Pr = 1/2). For above, 1 TDT = 870 rotations
