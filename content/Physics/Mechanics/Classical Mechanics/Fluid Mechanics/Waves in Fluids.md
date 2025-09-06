---
cssclasses:
  - img-grid
  - img-zoom
---
## Surface Gravity Waves

![Surface Gravity Waves](https://i.imgur.com/xle9M6n.png)
![Surface Gravity Waves2](https://i.imgur.com/NZ2RYyY.png)

**Thrm**  <i><u>Surface Gravity Waves Dispersion Relation</u></i>
For a flow of depth $H$, the dispersion relation of surface gravity waves is$$w=\sqrt{gk\tanh(kH)}$$In shallow water ($kH\ll1 \implies \tanh(kH)\approx kH$), it is non-dispersive, we have $$v_g=v_p=\sqrt{gH}$$

![surface_gravity_waves_dispersion.png](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/surface_gravity_waves_dispersion.png)


## Interfacial Waves

**Thrm**  <i><u>Interfacial Waves Dispersion Relation</u></i>
The dispersion relation for waves on an interface between two fluids of density $\rho_1$ (top fluid) and density $ρ_2$ (bottom fluid), with a surface tension $T$ (N/m) at the interface, and a uniform flow in the upper layer of $U$ (m/s) is given by
$$
\omega = \frac{kU\rho_{1}\pm \sqrt{(\rho_1+\rho_2)(k^3T+(\rho_2-\rho_1)gk)-\rho_1\rho_2k^2U^2}}{\rho_1+\rho_2}
$$

## Hydrodynamic Instabilities

**Def**  <i><u>Instability</u></i>
A system such that any small initial perturbation will be exponentially amplified with time is called an unstable system.

### Rayleigh-Taylor Instability

**Def**  <i><u>Rayleigh-Taylor Instability</u></i>
The Rayleigh-Taylor instability happens when the uniform flow in the upper layer of doesn't move(i.e. $U=0$). And we have the dispersion relation:
$$
(\rho_1+\rho_2)\omega^2=k^3T+(\rho_2-\rho_1)gk
$$

### Kelvin Helmholtz Instability

**Def**  <i><u>Kelvin Helmholtz Instability</u></i>
Kelvin Helmholtz instability happens when $\rho_1\approx\rho_2=\rho$ and $\rho_2-\rho_1=\Delta\rho\ll\rho$:
$$
\omega = \frac{kU}{2}\pm \sqrt{\frac{k^3T+\Delta\rho gk}{2\rho}-\frac{k^2U^2}{4}}
$$