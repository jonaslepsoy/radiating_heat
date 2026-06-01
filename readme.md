# FDTD Electromagnetic Radiation Heat Transfer Simulation

A browser-based 2D finite-difference time-domain (FDTD) simulation demonstrating electromagnetic thermal radiation from a heated irregular object. The simulation visualizes how a hot body emits EM radiation that propagates outward, coupling Maxwell's equations with a simplified thermal model.

## Physics

- **FDTD Method**: Solves Maxwell's equations (TM mode: Ex, Ey, Hz) on a 1024×512 Yee grid using the standard leapfrog time-stepping scheme.
- **Thermal Emission**: Stochastic electric currents are injected in the heated object proportional to T², mimicking fluctuational electrodynamics.
- **Radiative Cooling**: The object cools following a Stefan-Boltzmann T⁴ law.
- **Absorbing Boundaries**: A matched-impedance perfectly matched layer (PML) with quartic polynomial grading eliminates reflections at the domain edges.
- **CFL Stability**: Time step satisfies dt = dx/(c√2) for unconditional stability in 2D.

## Running

Open `index.html` in a modern browser. No build step or dependencies required.

## Controls

| Control | Description |
|---------|-------------|
| Play | Run simulation forward |
| Pause | Freeze simulation |
| Reverse | Run time-reversed (EM fields propagate inward) |
| Reset | Restore initial conditions (hot object, no fields) |
| Steps/frame | Number of FDTD iterations per animation frame (1–16) |
| Emission | Thermal emission intensity (1–100) |

## Visualization

- **Color** encodes temperature: black → blue → red → yellow → white (0–100 K).
- **Brightness overlay** shows instantaneous |E| field intensity.
- The black border is the PML absorbing region (not rendered).

## Stats Display

- **Step**: Current simulation time step
- **Max T**: Peak temperature in the object
- **Avg Object T**: Mean object temperature
- **EM Energy**: Total electromagnetic energy in the domain
- **FPS**: Rendering frame rate

## Known problems

- **Time-reversal** doesn't work properly at all. Everything explodes.
