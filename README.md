# Predator–Prey Dynamics in Economic and Financial Systems

Numerical companion code for the manuscript *Predator–Prey Dynamics in Economic
and Financial Systems* (Acharya, Bastola, Dulal, Bhusal, BK). The repository
contains the Python / Jupyter notebook used to generate every figure in the
paper, together with sign-corrected models and verification scripts developed
during revision.

The paper applies Lotka–Volterra predator–prey dynamics to three
socio-economic settings: the Goodwin growth-cycle model, a debt–capital model
linked to Minsky's Financial Instability Hypothesis, and a three-species
extension incorporating highly leveraged "financial super-predators." A
stochastic agent-based buyer–seller model is also developed and shown to
converge, in a mean-field sense, to the deterministic Lotka–Volterra ODE.

## Contents


## Figures

| # | Model                                  | Section |
|---|----------------------------------------|---------|
| 1 | Classical Lotka–Volterra               | §2.1    |
| 2 | Goodwin growth-cycle model             | §3.1    |
| 3 | Debt–capital predator–prey model       | §4.2    |
| 4 | Three-species financial super-predator | §4.3    |
| 5 | Stochastic agent-based buyer–seller    | §5      |

Each notebook cell is self-contained: imports, parameter block, ODE / SDE
definition, numerical integration, and plotting live together, so any figure
can be re-run on its own.

## Models at a glance

**Classical Lotka–Volterra.**
`dx/dt = r x − a x y`, `dy/dt = −m y + b x y`.
Conserved `H = b x − m ln x + a y − r ln y`.

**Goodwin growth-cycle.** State: wage share `ω`, employment rate `v`.
`dω/dt = ω[ρ v − (γ + α)]`, `dv/dt = v[s(1 − ω)/ν − (α + β)]`.
Interior equilibrium `v* = (γ + α)/ρ`, `ω* = 1 − (α + β)ν/s`.

**Debt–capital predator–prey.** Capital `C` (prey), debt `D` (predator).
`dC/dt = r_C C − a_DC C D`, `dD/dt = −r_D D + b_DC C D`.
Conserved `H = b_DC C − r_D ln C + a_DC D − r_C ln D`.
Interior equilibrium `C* = r_D / b_DC`, `D* = r_C / a_DC`.

**Three-species super-predator.** Adds a highly leveraged species `S` that
extracts returns from both `C` and `D`.

**Stochastic buyer–seller ABM.** Discrete-time, N-agent generalization of
the buyer–seller Lotka–Volterra system with price impact and optional
herding. Converges to the deterministic LV ODE as `N → ∞`.

## Reproducing the figures

Clone and launch Jupyter:

```bash
git clone https://github.com/deepakbastola/PredatorPrey.git
cd PredatorPrey
jupyter notebook PredatorPrey.ipynb
```

Run **Kernel → Restart & Run All** to regenerate every figure. Each cell writes
its PNG to the working directory (`fig1_basic_lotka_volterra.png`, …,
`fig5_abm_market.png`).

Random seeds are fixed in the stochastic figure (Figure 5) and in the
Monte-Carlo panel of Figure 3, so output is bit-reproducible within the same
NumPy version.

## Requirements

- Python ≥ 3.10
- numpy ≥ 1.24
- scipy ≥ 1.10
- matplotlib ≥ 3.7
- jupyter

Install:

```bash
pip install numpy scipy matplotlib jupyter
```

## Parameters

Default parameter blocks sit at the top of each notebook cell and are the ones
used in the paper's figures. They are chosen for illustrative clarity rather
than empirical calibration; references for empirically grounded values are
given in the manuscript (Harvie 2000 for Goodwin, Keen 2011 for the
debt–capital model, Crookes & Blignaut 2016 for the trophic-sectoral model).

## Citation

If you use this code, please cite the paper:

```bibtex
@article{acharya2026predatorprey,
  title   = {Predator--Prey Dynamics in Economic and Financial Systems},
  author  = {Bastola, Deepak and Acharya, Pitambar  and Dulal, Dipak
             and BK, Pawan Kumar},
  journal = {<STAR Journal of Applied Mathematics, Statistics, and Computational Sciences (JAMSCS) >},
  year    = {2026}
}
```

## License

MIT License

## Contact

Issues and pull requests welcome. For questions about the mathematics, please
contact the corresponding author at deepakbastola89@gmail.com.
