# Climbing Jack Stability Tool

A single-file HTML tool that evaluates climbing-jack / stillage stability with a **two-support planar model** and visualises the mechanics in real time.

> **Safety**: Planning aid only. Outputs must be reviewed and signed off by a **competent person**. Does not check sliding, ground bearing, or member capacities.

## What it does
- Live inputs (m, t, m/s) with an SVG infographic (supports A/B, CG, height Z, FS+FW, reactions).
- Computes: `FS + FW`, reactions `RA, RB`, **Stability % = RB / RB_vert × 100**, and an indicative overturning FoS.

## Inputs
`L, x1, x2, Z, FV (t), side% of FV, A, Cd, ρ, V, Ns`.

## Equations
- `Fv = FV[t] × 1000 × 9.81`
- `FS = Fv × (side% / 100)`
- `FW = 0.5 × Cd × A × ρ × V² / Ns`
- `RA_vert = Fv × x2 / L`, `RB_vert = Fv × x1 / L`
- `ΔR = (FS + FW) × Z / L`
- `RA = RA_vert + ΔR`, `RB = RB_vert − ΔR`
- `Stability% = RB / RB_vert × 100`
- `FoS ≈ (Fv × min(x1,x2)) / ((FS+FW) × Z)`

## Quick start
Open `index.html` in any modern browser—no build or dependencies.

## Compliance
Use within a controlled procedure (e.g., LOLER/PUWER, BS 7121 series). Add project-specific load cases (wind limits, dynamics, GBP, sliding, anchors) in the lift plan.
