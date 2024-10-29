# Jupiter_CZonly

To all Jupiter enthusiasts named Matt, Geoff, and Nic:

In this Github repository, I am in the process of compiling some results based on the convection-zone only Jupiter models I’ve been running. I’m going to start with just one model (so there is something to look at before the end of today, 02/27) but I have a whole grid of cases. These have several common attributes:

Aspect ratio (r_in/r_out = 0.9, r_in = 9, r_out = 10)
3 density scale heights across the layer
Adiabatic, hydrostatic background polytrope with n = 2 (rho ~ T^2)
Constant thermal conductivity and kinematic viscosity (Pr = nu/kappa = 1)
One spherically symmetric, time-independent heating layer at the base and similarly one cooling layer at the top (equal and opposite volume integrals), each of width 0.1x the shell depth. 

The results are reported nondimensionally, with 
Length scale = shell depth (call the dimensional shell depth H)
Time scale = viscous diffusion time (tau = H^2/nu)
Velocity scale = H/tau
Reference state profiles scaled by their values at the inner radius
Pressure perturbation scale = dynamic pressure (rho_in * H^2/tau^2)
Entropy perturbation scale = (Delta S) = F_in * H / (rho_in * T_in * kappa_in)
…where F_in = L/(4*pi*r_in^2) is the effective heat flux of the bottom heating layer and L is the dimensional volume integral of the bottom heating layer (i.e., the luminosity from below). 

The control parameters that are varied are only the Rayleigh number Ra and convective Rossby number Ro_c (defining a 2D grid). These are defined as follows:

Ra = (Delta S/C_p) * g_in H^3 / (nu * kappa)

Ek = nu / (2*Omega*H^2) (with Omega being the frame rotation rate, note the 2)

Ro_c = sqrt(Ra*Ek^2/Pr) = sqrt [ (Delta S/C_p) * g_in / (H * 4 * Omega^2)  ]

So far I have run 12 cases in various stages of equilibration, covering

Ro_c in [0.05, 0.10, 0.15, 0.25]
Ra in [10^4, 10^5, 10^6]

The subfolders containing plots and info about each run are labeled

Roc[###]_Ra[###]
….where the hashtags denote the values of Ro_c and Ra. 
