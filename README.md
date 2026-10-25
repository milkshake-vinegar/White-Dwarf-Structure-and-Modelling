This repository contains methods to generate Mass-Radius relations and compute the structure for white dwarfs, stellar remnants that form after the death of low-mass and Sun-like stars. 

The main report of this investigation with the code and plots are contained in this repository. Mass-Radius curves for various equations of state are generated using the equation of state of electron degenerate gas by solving various initial conditions using solve_ivp. We also that the Coulomb correction term plays significant role in softening the curve lowering the mass for a given radius and vice versa. However by solving the  Tolman-Oppenheimer-Volkoff equation, the Chandrasekhar limit can be uncovered revealing a peak at around 1.4 Solar Masses which is later refined by Coulomb correction. A figure summarizing the discussion is shown below,

<img width="846" height="699" alt="MR_degenerate_white_dwarfs" src="https://github.com/user-attachments/assets/305211c8-1d72-496d-8e40-d86c035326c4" />

Incorporating the finite temperature involves approximating the Fermi Dirac integrals to write the pressure and number density in an infinite series. The most dominant temperature correction term is taken and involves numerical computation by SymPy to compute numerically compute functions and derivatives. This leads to a curve where a white dwarfs puff up have a greater radius for a given mass albeit only noticeable at temperatures close to the Fermi temperature of the system. This also involves a non-degenerate envelope that transitions out of a fermi gas at a boundary.

<img width="846" height="699" alt="finite_temp_5e7K_white_dwarf_MR" src="https://github.com/user-attachments/assets/27d65ed7-3b3e-472e-8e06-488736f08e7e" />

In deeper depths of the star where density increases rapidly, the electrons begin to combine with protons in the nuclei releasing neutrons known as inverse beta decay. This transforms the nuclei allowing much higher neutron numbers for a certain atomic number. To tackle this case and obtain an equation of state, the energy density consisting of the mass of the nucleus and the energy of electrons must be minimized. By using the liquid drop model, an equilibrium configuration at atomic and mass numbers (Z,A) exists at given density. The mass of the nuclei contributes to the mass density and we can plot the equation of state at the full range of densities keeping in mind that below a neutronization threshold, no minimization of energy density is required.

<img width="691" height="626" alt="nuclear_eq_of_state" src="https://github.com/user-attachments/assets/8d8a392f-2fa6-4d36-b34e-073e62882fb9" />

The final goals are to structure the white dwarf into three layers (nuclear, isothermal core, non-degenerate surface layer) in order to acquire a MR curve. 

References:

Padmanabhan, T. (2000). Theoretical astrophysics: Vol. 1. Astrophysical processes. Cambridge University Press.

Padmanabhan, T. (2001). Theoretical astrophysics: Vol. 2. Stars and stellar systems. Cambridge University Press.
