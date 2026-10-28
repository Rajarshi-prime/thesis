# Figures that may need remaking after the symbol rename

A large symbol rename was applied to the five chapter files and to
`chapters/appendix.tex`, following `symbol_replacements.md`. The captions in the
`.tex` files were renamed along with the prose. The axis labels, colourbar
labels, legends and panel annotations inside the figure files were **not**,
because 64 of the 65 files under `chapters/figures/` are raster or compiled
vector images whose text cannot be edited. Those plots have to be redrawn from
the original plotting scripts.

**How this list was made, and how far to trust it.** I did not open a single
image. For every `\includegraphics` and `\import` call I read the caption, the
paragraph around it, and the file name, and from those I worked out which
quantities the figure most likely puts on its axes. Everything below is an
inference from text, not an observation of pixels. The confidence column says
how firm each guess is:

- **high** — the caption or the surrounding prose names the quantity with the
  renamed symbol itself, so the symbol is almost certainly drawn on the figure.
- **medium** — the caption names the quantity in words, and the plotting
  convention of the chapter makes the symbol the natural axis label, but the
  figure could be using words or a different label instead.
- **low** — the quantity is only implied by the file name or by the
  neighbouring discussion.

Whoever regenerates these should open each one and check before redrawing.
A figure absent from the table is listed in the closing section instead.

## Figures likely carrying a renamed symbol

| Figure label | Chapter | Figure file | Old symbol likely shown | New symbol | Confidence |
|---|---|---|---|---|---|
| `edwv-flxfrc` | internal_tide_eddy | `internal_tide_eddy/normalized_flux_fracs.pdf` | `\xi`, `\xi_0` (normalised placeholder field on the x-axis), `\varphi` on the y-axis | `\varXi`, `\varXi_0`; `\varphi` unchanged | medium |
| `edwv-ekl` | internal_tide_eddy | `internal_tide_eddy/ekh_pikh_wb_fs_lw.pdf` | legend/annotation `\alpha` for `N/f`, if the run parameters are printed on the panels | `\AR` | low |
| `edwv-eke` | internal_tide_eddy | `internal_tide_eddy/ekh_pikh_wb_fs_ew.pdf` | same as above | `\AR` | low |
| `thrm-fig1` | thermalization | `thermalization/Specra_allN_t3_t6.pdf` | `E(k)` on the y-axis, compensated `k^3 E(k)` in the inset, `\Delta_0 E` in the panel (b) inset | `\mathbb{E}(k)`, `k^3\mathbb{E}(k)`, `\Delta_0\mathbb{E}` | high |
| `thrm-fig2` | thermalization | `thermalization/Flux_allN_t3_t6.pdf` | nothing renamed on the axes (`\Pi`, `k`, `K_{\rm G}` all kept); legend may print `N` for resolution | `N_g` if the legend uses `N` | low |
| `thrm-fig3` | thermalization | `thermalization/enstrophyvstime_time_scalestbtc_gamma.pdf` | `\Omega`, `\Omega_\infty` on panel (a); `t_c` and `N` on panel (b); `E(k)` in the panel (b) inset | `\mathcal{Z}`, `\mathcal{Z}_\infty`; `t_{\rm cas}`, `N_g`; `\mathbb{E}(k)` | high |
| `int-inner-sol` | inertial_caustics | `inertial_caustics/pt_vrtx_upd.pdf` | `T_c` and `\mathcal{R}_c` against `\mathcal{R}_0`; `\ell` if the inner-region size is annotated | `\mathcal{T}_c`; `\mathfrak{l}` | medium |
| `int-pstruc` | inertial_caustics | `inertial_caustics/snapshot_PDF.pdf` | `\omega` on the vorticity colourbar of panels (a-c) | `\zeta` | high |
| `int-caus_nc_sum` | inertial_caustics | `inertial_caustics/caus_nc_summary_0.7.pdf` | `\theta_v` on the panel (a) alignment-angle axis; `\omega` on the panel (c) vorticity axis | `\vartheta_v`; `\zeta` | high |
| `int-caus_nc_sum_1` | inertial_caustics | `inertial_caustics/caus_nc_summary_1.0.pdf` | same as above, at `\alpha = 1` | `\vartheta_v`; `\zeta` | high |
| `int-flchrt` | inertial_caustics | `inertial_caustics/summary.pdf` | schematic annotations for the strain eigendirections, drawn as `\hat{e}_\pm`, and possibly `\hat{\theta}` | `\vec{e}_\pm`, `\vec{e}_\vartheta` | medium |
| `act-Figure1` | active_caustics | `active_caustics/Fig1prx.jpeg` | `\alpha` in the panel (c) caption strip; `\mathbf{U}` if the panel (b) schematic labels the flow; `\norm{\nabla \mathbf{U}}` on the panel (a) axis | `\alpha_{\rm act}`; `\vec{u}` | medium |
| `act-io` | active_caustics | `active_caustics/inner_outer.pdf` | `L` on the angular-momentum axis of panels (b,d); `\alpha` in the legends of all four panels | `\mathscr{L}`; `\alpha_{\rm act}` | high |
| `act-caustics_regime` | active_caustics | `active_caustics/Figure2mod.jpeg` | `r_c` marking the critical radius in panel (d); `\alpha` on the panel (e) axis; `\epsilon_i`-type labels if the stretching is annotated | `\mathcal{R}_{c0}`; `\alpha_{\rm act}`; `\varepsilon_i` | high |
| `act-pt_vortex` | active_caustics | `active_caustics/pt_vrtx_results.pdf` | `\alpha` in the legend of both panels; `\textbf{Z}` in a `Tr(Z)` annotation, a font change only | `\alpha_{\rm act}`; `\mathbf{Z}` | medium |
| `act-fig:abp1` | active_caustics | `active_caustics/ABP1.jpg` | `\alpha` in the panel strips | `\alpha_{\rm act}` | medium |
| `act-Fig3` | active_caustics | `active_caustics/Fig3_nondimensional.jpeg` | `\ell^2/\mathrm{w}_0^2` on the panel (c) axis and in the (a,b) row labels; `\omega` if the colourbar is labelled with the vorticity symbol rather than the word | `l^2/\mathrm{w}_0^2`; `\zeta` | medium |
| `act-caustics_noise` | active_caustics | `active_caustics/FigNoise.jpg` | `\sqrt{2D/\mathrm{w}_0^2\kappa}` in the panel (a,b) annotations | `\sqrt{2D_\eta/\mathrm{w}_0^2\kappa}` | high |
| `act-fig:3` | appendix (active_caustics) | `active_caustics/density_fluctuation_measure.jpg` | `\ell^2/\mathrm{w}_0^2` in the legend | `l^2/\mathrm{w}_0^2` | medium |
| `lucky-zeta-sm-1big` | polydisperse_lucky_drops | `polydisperse/sm_0.02_0.002.pdf` | `\omega` on the vorticity colourbar; `\varphi_s` on the volume-fraction colourbar | `\zeta`; `c_s` | high |
| (unlabelled) | polydisperse_lucky_drops | `polydisperse/sm-nobig.pdf` | `\varphi_s` on the volume-fraction colourbar | `c_s` | medium |
| `lucky-pstruc` | polydisperse_lucky_drops | `polydisperse/pstruc.pdf` | `\varphi_s` on the colourbar of all three panels | `c_s` | high |
| `lucky-grth-diffQ` | polydisperse_lucky_drops | `polydisperse/diff-Q-grwth-rate.pdf` | `\varphi_b` on the growth axis; `Q` kept | `c_b` | medium |
| (unlabelled) | polydisperse_lucky_drops | `polydisperse/pre-post-vort.pdf` | `\omega`, `\omega_{\rm rms}` in the `\omega > 2\omega_{\rm rms}` threshold annotation; `\varphi_b` on the volume axis | `\zeta`, `\zeta_{\rm rms}`; `c_b` | high |
| (unlabelled) | polydisperse_lucky_drops | `polydisperse/rndm_0.002_0.02.pdf` | `\omega` on the vorticity colourbar; `\varphi_s` on the concentration colourbar | `\zeta`; `c_s` | high |
| (unlabelled) | polydisperse_lucky_drops | `polydisperse/Qpos_0.002_0.02.pdf` | `\omega` on the vorticity colourbar; `\varphi_s` on the concentration colourbar; `Q_{rms}` kept | `\zeta`; `c_s` | high |
| `lucky-grwth` | polydisperse_lucky_drops | `polydisperse/sts_0.002_stb_0.01,0.02_grwth.png` | `\varphi_b` (left panel) and `\varphi_s` (right panel) on the y-axes | `c_b`, `c_s` | medium |
| `lucky-grwth-loglog` (figure) | polydisperse_lucky_drops | `polydisperse/sts_0.002_stb_0.01,0.02_grwth_loglog.png` | same as above, on log axes | `c_b`, `c_s` | medium |
| `lucky-growth-small-times` | polydisperse_lucky_drops | `polydisperse/smalltimes-2d.png` | `\varphi_s` and `\varphi_b` on the two y-axes | `c_s`, `c_b` | medium |
| `lucky-largetimes-2d` | polydisperse_lucky_drops | `polydisperse/largetimes-2d.png` | `\varphi_s` on the left y-axis; `\gamma` if the fitted exponential rate is annotated | `c_s`; `\lambda_s` | medium |
| `lucky-3d-grwth` | polydisperse_lucky_drops | `polydisperse/3d-grwth.png` | `\varphi_b` on the y-axis | `c_b` | medium |
| (unlabelled) | polydisperse_lucky_drops | `polydisperse/det-v-stoch.png` | `\varphi_b` on the growth-rate axis | `c_b` | low |
| (unlabelled) | polydisperse_lucky_drops | `polydisperse/stoch-v-m.png` | `m` (the Kolmogorov-length parameter, per the file name) in the legend; `\varphi_b` on the y-axis | upright `\mathrm{m}`; `c_b` | low |
| (unlabelled) | polydisperse_lucky_drops | `polydisperse/nfield-dits.png` | `\varphi_s` if the number-density field is shown as a volume fraction | `c_s` | low |
| `lucky-grad-corr` | appendix (polydisperse) | `polydisperse/grad-corr.png` | `N` if the bin count `128^3` is written with the resolution symbol | `N_g` | low |
| (unlabelled) | appendix (polydisperse) | `polydisperse/gen-corr.png` | `\lambda` and `\bar{\lambda}` from the correlated Poisson draw; these were not renamed, but `\lambda` now collides with `\lambda_s` | no rename required, worth a look | low |

## Figures confident of needing no work

**The one `.pgf` file.** `chapters/figures/polydisperse/sm-nobig.pgf` is
matplotlib's PGF output, a plain-text vector format whose labels can be edited
as text. Its only mathematical label is already `$c_s$`, the new symbol, so it
needs nothing. Note that the chapter includes `sm-nobig.pdf`, not the `.pgf`,
and the `.pdf` is listed in the table above because it is a separate compiled
image whose label I cannot read.

**internal_tide_eddy.** `vorticity_lw_o_b_f_3d.pdf` (`edwv-psl`),
`vorticity_ew_o_b_f_3d.pdf` (`edwv-pse`) and
`0.9-flux-fraction-vorticity-structure-lw-3d.pdf` (`edwv-flxmsk`) all show
vorticity, which this chapter already wrote as `\zeta` before the rename.
`tranfer_dissipation_net.pdf` (`edwv-dt`) shows the dissipation `D` and the
transfers `T`, `T_i`, all kept; the letter `D` stayed free because the domain of
integration became `V`, a symbol that appears in no figure.
`frequencies.pdf` (`edwv-iwc`) and `omg_kh_linear_waves.pdf` (`edwv-lwfrc`)
are frequency plots in `\omega`, `\omega_0` and `\Delta\omega`, which keep their
meaning of wave frequency in this chapter. `flux-efficiency-structure-pdf.pdf`
(`edwv-flxeff`) shows `\Pi_\ell` and `k_\ell`, both kept.

**inertial_caustics.** `analtcaustics.pdf` (`int-inequality`) is drawn in the
`QR` plane with the Vieillefosse line; `Q`, `R` and `\alpha` all keep their
meaning in this chapter. `caus_q_trz.pdf` (`int-fig: Q-timeseries-2d`) and
`caus_nc_Q_trz_mean.pdf` (`int-c_nc_Q_trz`) plot `Q`, `\delta = \Tr(\mathbb{Z})`
and `t - t_c`, every one of them kept, and `\mathbb{Z}` was already `\mathbb`.
`caus_propensity.pdf` (`int-propensity`) plots particle fractions against
`\alpha`, which is kept.

**active_caustics.** `collision_schematic.jpeg` (`act-fig:collision`) is a
schematic whose only annotation is the time step `\Delta t`.

**polydisperse_lucky_drops and its appendix.** `threshold-growth.png`
(`lucky-thresh`) and `sts_0.002_stb_0.01-0.02_final_distribution.png` plot
Stokes numbers `St_b`, `St_s`, which are kept. `dist-nbin-256.png`
(`lucky-nbin-dist-256`), `dist-nbin-128.png` (`lucky-nbin-dist-128`),
`poisson-check.png` (`lucky-poisson-check`), `n-snapshot-st-0.001.png`
(`lucky-n-snp`), `n-spectra-slope.png` (`lucky-n-spectra-slope`),
`binned-v-smeared-comp.png` (`lucky-struc-binned-v-smeared`),
`log_comp.png` (`lucky-log_comp`), `comp-cai-v-my-unclipped.png`
(`lucky-comp-cai-v-my-unclipped`) and `clipping-comp.png`
(`lucky-clipping-comp`) are all about the number-density field `n_s` and its
spectrum, and `n_s` was not renamed; the rename touched the volume fraction
`\varphi_s`, which is a different quantity. `stochastic-collision.pdf` is a
flowchart with no mathematical axis.
