# Planned symbol replacements

Every symbol replacement, grouped by the chapter file that has to be edited. A
row marked `change` needs an edit in that chapter. A row marked `keep` is
listed so the reason for leaving it alone is on record.

`symbol_replacements.tex` is a reading copy of this file. Any change made here
has to be made there too.

---

## `chapters/internal_tide_eddy.tex`

| Current | Proposed | Meaning | Status |
|---|---|---|---|
| `\alpha` | `\AR` | ratio of buoyancy to inertial frequency, `N/f`, fixed at 20 | change |
| `\ell` | `\ell` | filtering length scale, with `k_\ell = 2\pi/\ell` | keep |
| `L` | `L` | horizontal length scale | keep |
| `H` | `H` | vertical length scale | keep |
| `\omega`, `\omega_0`, `\omega_c` | same | wave frequency, tidal forcing frequency, slow-fast cut-off | keep |
| `\Omega` | `\Omega` | rotation rate of the Earth | keep |
| `N` | `N` | buoyancy frequency | keep |
| `\vec{v}` | `\vec{v}_{\rm 2D}` | horizontal fluid velocity `(u,v)` | change |
| `\bm{u}` | `\vec{u}` | three-dimensional velocity. Every chapter now writes the fluid velocity `\vec{u}` | change |
| `U` | `U` | horizontal velocity scale | keep |
| `p` | `\mathcal{P}` | pressure | change |
| `D` | `V` | domain of integration | change |
| `D`, `\hat{D}(k_h,t)` | same | net flow dissipation. The letter is free once the domain becomes `V`. The `\epsilon` of the other chapters is dissipation per unit mass, a different quantity | keep |
| `T`, `T_i` | same | nonlinear energy transfer | keep |
| `\varphi` | `\varphi` | cumulative flux fraction | keep |
| `\xi` | `\varXi` | placeholder field whose flux fraction is computed | change |
| `\nu` | `\nu_{\rm hyp}` | hyperviscosity multiplying `\Delta^8` | change |
| `w` | `w` | vertical velocity | keep |
| `\theta`, `\theta_{k_h}` | same | latitude, azimuthal angle in wavenumber space | keep |
| `E`, `\hat{E}(k_h,t)` | same | domain-integrated energy and horizontal spectrum | keep |
| `\Pi`, `\Pi_\ell` | same | spectral flux, physical-space flux at scale `\ell` | keep |
| `\vec{F}_{\vec{v}}`, `F_w`, `F_b`, `\hat{F}` | same | forcing terms and power input spectrum | keep |
| the hat accent | same | a Fourier amplitude here, as in `\hat{u}`, `\hat{E}(k_h)`. The chapter's own `\widehat` redefinition stays | keep |
| the overbar | same | a time average. The other chapters keep angle brackets | keep |

## `chapters/thermalization.tex`

| Current | Proposed | Meaning | Status |
|---|---|---|---|
| `H` | `\mathbb{H}` | Hamiltonian | change |
| `\mathcal{H}` | `\mathcal{H}` | helicity | keep |
| `\Omega`, `\Omega_\infty` | `\mathcal{Z}`, `\mathcal{Z}_\infty` | enstrophy | change |
| `N` | `N_g` | collocation points per direction | change |
| `N_{\rm G}` | `N_{\rm G}` | number of retained modes. Upright against the italic `N_g` of the collocation points, so the two are told apart by shape as well as case | keep |
| `\mathbf{v}` | `\mathbf{u}` | Galerkin-truncated velocity. It becomes a `u` so that both fields carry the same letter | change |
| `\mathbf{u}` | `\vec{u}` | untruncated Euler velocity. Upright marks the truncated field, italic the untruncated one | change |
| `P` | `\mathcal{P}` | pressure | change |
| `\mathcal{P}_{\mathbf{K}_{\rm G}}` | `\mathbb{P}_{\mathbf{K}_{\rm G}}` | Galerkin projector, moved aside to free `\mathcal{P}` | change |
| `\mathbf{p}`, `\mathbf{q}` | same | wavevectors in the convolution sum. Bold upright, against the bold italic `\vec{p}` that `polydisperse_lucky_drops` uses for linear momentum. Every spectral quantity here carries a hat, so the bare bold letters read as wavevectors | keep |
| `T(k)` | `T(k)` | transfer term | keep |
| `t_b` | `t_b` | birth time of the oscillatory structures | keep |
| `t_c` | `t_{\rm cas}` | cascade completion time | change |
| `t_*` | `t_*` | preshock time of the inviscid Burgers equation | keep |
| `\gamma` | `\gamma` | spectral slope | keep |
| `\delta t`, `\Delta_0 E`, `\Delta_0\mathcal{H}` | same | time step and relative errors | keep |
| `\epsilon` | `\epsilon` | effective dissipation per unit mass, which is why it is not the `D` of `internal_tide_eddy` | keep |
| `\nu`, `\nu_{\rm eff}` | same | kinematic and eddy viscosity | keep |
| `E`, `E(k)` | `\mathbb{E}`, `\mathbb{E}(k)` | kinetic energy per unit mass and its isotropic spectrum. The blackboard letter marks energy per unit mass, as against the domain-integrated `E` in `internal_tide_eddy` | change |
| `\Pi(k)` | `\Pi(k)` | kinetic energy flux | keep |
| the hat accent | same | a Fourier amplitude here, as in `\hat{\mathbf{v}}_{\mathbf{k}}` | keep |
| `\langle\cdot\rangle` | same | averaging | keep |

## `chapters/inertial_caustics.tex`

| Current | Proposed | Meaning | Status |
|---|---|---|---|
| `\alpha` | `\alpha` | density parameter, `2\rho/(2\rho+1)` | keep |
| `\ell` | `\mathfrak{l}` | inner region size, `\mathfrak{l}^2 = \tau\sqrt{3\alpha-2}` | change |
| `L` | `L` | flow length scale | keep |
| `\mathscr{L}` | `\mathscr{L}` | angular momentum per unit mass | keep |
| `\mb{A}` | `\mathbb{A}` | fluid velocity gradient tensor, `St\,\nabla\vec{u}`, already `\mathbb`, nothing to do. The plain letter A for avoider particles stands apart, the fonts differ | keep |
| `\mb{S}` | `\mathbb{S}` | strain tensor, already `\mathbb`, nothing to do | keep |
| `\mb{Z}` | `\mathbb{Z}` | particle velocity gradient tensor, already `\mathbb` | keep |
| `\omega` | `\zeta` | vorticity | change |
| `\vec{v}` | `\vec{v}` | particle velocity | keep |
| `\vec{u}` | `\vec{u}` | background fluid velocity at the particle | keep |
| subscript `p` | subscript `p` | particle quantities, `\vec{x}_p`, `\rho_p`, `\tau_p` | keep |
| `D/Dt` | `D/Dt` | material derivative | keep |
| `T`, `T_c` | `\mathcal{T}`, `\mathcal{T}_c` | rescaled inner time and caustics time in inner units | change |
| `t_b` | `t_{\rm thresh}` | time when `-\mb{Z}^2` starts to dominate | change |
| `\mb{Z}_b` | `\mb{Z}_{\rm thresh}` | the tensor at that time | change |
| `\zeta` | `\chi` | auxiliary root of the quartic, in the appendix | change |
| `t_c` | `t_c` | caustics time | keep |
| `r_c` | `r_c` | caustics radius | keep |
| `\mathcal{R}_{c0}` | `\mathcal{R}_{c0}` | critical initial radius | keep |
| `\gamma` | `\gamma_\epsilon` | linear drag coefficient, see point 2 | change |
| `\sigma`, `\sigma_s`, `\sigma_n` | same | net, shear, and normal strain | keep |
| `\xi` | `\xi` | `1-\alpha` | keep |
| `\delta` | `\delta` | trace of `\mb{Z}` | keep |
| `\epsilon` | `\varepsilon` | separation between two particle rings | change |
| `\nu` | `\nu` | kinematic viscosity | keep |
| `\theta`, `\theta_v` | `\vartheta`, `\vartheta_v` | polar angle, angle between particle velocity and the strain eigendirections | change |
| `\hat{\theta}`, `\hat{e}_\pm`, `\hat{v}` | `\boldsymbol{e}_\vartheta`, `\boldsymbol{e}_\pm`, `\boldsymbol{e}_v` | unit vectors. Every unit vector takes the `\boldsymbol{e}` form, which frees the hat for Fourier amplitudes alone | change |
| `f_\omega` | `F_\zeta` | flow forcing. The subscript follows the vorticity to `\zeta` | change |
| `Q` | `Q` | Okubo-Weiss parameter, `-\mathrm{Tr}(\mathbb{A}^2)/2`. `active_caustics` keeps its own `\mathcal{W}` | keep |
| `\Gamma` | `\Gamma` | circulation of the point vortex. `active_caustics` keeps `\tilde{\Gamma} = \Gamma/2\pi` | keep |
| `k_f` | `k_f` | forcing wavenumber of the two-dimensional flow | keep |
| `\langle\cdot\rangle` | same | averaging | keep |

## `chapters/active_caustics.tex`

| Current | Proposed | Meaning | Status |
|---|---|---|---|
| `\alpha` | `\alpha_{\rm act}` | Jeffery-type response parameter | change |
| `\ell`, and `\lambda` in one place | `l` | polar flow-alignment length | change |
| `L` | `\mathscr{L}` | angular momentum per unit mass | change |
| `\mathcal{H}` | `\mathbb{H}` | effective Hamiltonian of the inner solution | change |
| `\textbf{A}` | `\mathbf{A}` | antisymmetric part of the velocity gradient, font made uniform | change |
| `\textbf{S}`, one `\sf{S}`, `\tilde{S}` | `\mathbf{S}`, `\tilde{\mathbf{S}}` | strain-rate tensor, font made uniform | change |
| `\textbf{Z}` | `\mathbf{Z}` | particle gradient tensor, font made uniform | change |
| `\omega` | `\zeta` | vorticity in the Okubo-Weiss parameter | change |
| `N` | `N_p` | number of particles | change |
| `\mathbf{v}` | `\vec{v}` | particle velocity, brought in line with the other chapters | change |
| `\mathbf{U}` | `\vec{u}` | background flow field, brought in line with the other chapters | change |
| `U_0` | `U_0` | scale of the background flow | keep |
| `p` | `p_r` | radial momentum per unit mass, `d\tilde{r}/d\tilde{t}` | change |
| `D` | `D_\eta` | noise strength in `\sqrt{2D}\,\bm{\eta}` | change |
| `D_t` | `D_t` | fluid material derivative | keep |
| `t^*` | `t^*` | matching time for the outer boundary conditions | keep |
| `r_c` | `\mathcal{R}_{c0}` | critical initial radius beyond which caustics never form | change |
| `\delta_i`, `\delta_o` | same | spatial stretching factors | keep |
| `\epsilon_i`, `\epsilon_o` | `\varepsilon_i`, `\varepsilon_o` | temporal stretching factors | change |
| `\nu` | `\nu` | kinematic viscosity | keep |
| `\mathbf{w}`, `w_0` | `\mathbf{w}`, upright `w` for the scalar | end-to-end extension of the dimer | change |
| `\mu` | `\mu` | Stokesian mobility of the particle | keep |
| `\mu` | `\mu_E` | Ekman friction of the background flow, split off from the mobility | change |
| `\theta` | `\vartheta` | polar angle of the point-vortex coordinates | change |
| `\hat{\theta}` | `\boldsymbol{e}_\vartheta` | unit vector. Every unit vector takes the `\boldsymbol{e}` form | change |
| `\mathbf{\hat{r}}` | `\boldsymbol{e}_r` | radial unit vector | change |
| `\textbf{I}` | `\mathbb{I}` | identity tensor | change |
| `q` | `k_f` | forcing wavenumber, written `q` in the text and `k_f` in the table of spectral parameters | change |
| `\vec{F}`, `\vec{F}_{\rm eff}`, `F_0` | same | external force, effective force, forcing amplitude | keep |
| `\mathcal{W}` | `\mathcal{W}` | Okubo-Weiss parameter from dimensional gradients. It differs from the `Q` of the other chapters by a positive constant and by `St^2` | keep |
| `\tilde{\Gamma}` | `\tilde{\Gamma}` | circulation, `\tilde{\Gamma} = \Gamma/2\pi` | keep |
| `\tilde{O}` | `\tilde{\mathbf{O}}` | fluid velocity gradient tensor, `\tau\nabla\vec{u}`, the counterpart of `\mathbb{A}` in `inertial_caustics` | change |
| `\Delta r` | `\Delta r` | separation between two neighbouring particle rings | keep |
| `\langle\cdot\rangle` | same | averaging | keep |

## `chapters/polydisperse_lucky_drops.tex`

| Current | Proposed | Meaning | Status |
|---|---|---|---|
| `\omega`, `\omega_{\rm rms}` | `\zeta`, `\zeta_{\rm rms}` | vorticity, through the threshold `\omega > 2\omega_{\rm rms}` | change |
| `N` | `N_g` | grid resolution | change |
| `N_b`, `\dot{N}_c` | same | number of lucky drops, collision rate | keep |
| `\vec{v}`, `\vec{v}_s`, `\vec{v}_b` | same | particle velocity, small and big droplets | keep |
| `\vec{u}` | `\vec{u}` | background fluid velocity at the particle | keep |
| `\vec{p}`, `P(m,t)`, `P_{cc}` | same | linear momentum, mass density, collision-coalescence probability | keep |
| `D/Dt` | `D/Dt` | material derivative | keep |
| `\gamma` | `\lambda_s`, `\alpha_g` | depletion rate of small droplets, and the fitted growth exponent `t^{\alpha_g}` | change |
| `m` | `m` | droplet mass | keep |
| `m`, `k_m` | `\mathrm{m}`, `k_{\mathrm{m}}` | parameter setting the Kolmogorov length, `\eta_s = \mathrm{m}/k_{\mathrm{m}}`, made upright to part it from the mass | change |
| `\sigma`, `\sigma_2`, `\sigma_3` | `\varsigma`, `\varsigma_2`, `\varsigma_3` | collision cross-section in two and three dimensions. The chapter gives two disagreeing forms, and `\varsigma_3 = \pi(a_s+a_b)^2` is the correct one | change |
| `\varphi_s`, `\varphi_b`, `\varphi` | `c_s`, `c_b`, `c` | volume fraction of the small droplets, the big ones, and either | change |
| `Q_{rms}` | `Q_{\rm rms}` | root mean square of the Okubo-Weiss parameter | change |
| `\delta`, `\delta t` | same | Dirac delta and time step | keep |
| `\epsilon`, `\varepsilon` | `\epsilon` | mean energy dissipation rate of the cloud | change |
| `\nu` | `\nu` | kinematic viscosity | keep |
| `\mu`m | `\mu`m | micrometre prefix only | keep |
| `Q` | `Q` | Okubo-Weiss parameter, same form as in `inertial_caustics` | keep |
| `\langle\cdot\rangle` | same | averaging | keep |

---

## Notes

1. `\lambda_s` for the depletion rate and `\alpha_g` for the growth exponent in
   `polydisperse_lucky_drops` free `\gamma` so it means the spectral slope in
   `thermalization` alone. `\beta` was ruled out because `active_caustics`
   already uses it for the swimming rate.
2. `\gamma_\epsilon` is proposed for the drag in `inertial_caustics` while
   `\epsilon` in that chapter becomes `\varepsilon`.
3. `\mathbb{H}` is proposed for the `thermalization` Hamiltonian and for the
   `active_caustics` effective Hamiltonian. Both are Hamiltonians, so this is
   probably intended, but it should be stated rather than assumed.
4. `\AR` comes from the `ar` package, which `preamble.tex` does not load. It
   has to be added before the replacement is made.
5. `N_g` means collocation points in `thermalization` and grid resolution in
   `polydisperse_lucky_drops`. These are the same quantity, so the reuse looks
   deliberate.
6. In `chapters/inertial_caustics.tex` the tensors are written `\mb{A}`,
   `\mb{S}`, `\mb{Z}`, and `\mb` is defined in `preamble.tex:157` as
   `\mathbb`. In `chapters/active_caustics.tex` the same tensors are written
   `\textbf{A}`, `\textbf{S}`, `\textbf{Z}`, with one stray `\sf{S}`.

 All changes should only be symbolic. You cannot add any new lines or texts. 