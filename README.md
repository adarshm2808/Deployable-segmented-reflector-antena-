⚠️THIS PROJECT IS STILL IN PROGRESS !!
# Deployable-segmented-reflector-antena-
Design and Simulation of an Ultra-Lightweight Segmented Deployable Reflector Antenna for Space Operations

# Segmented Deployable Reflector Antenna (Space Payload Design)

An ultra-lightweight, high-stiffness, "Lotus-style" segmented deployable parabolic antenna mechanism optimized for space-shuttle payload deployment. This repository contains the CAD architecture, structural design parameters, and rigid-body dynamic simulation profiles executed within SolidWorks.



## 🚀 Project Overview

Deployable space structures must balance minimal stowed volume during launch with exceptional structural rigidity upon deployment. This project presents a positive-driven, synchronized mechanical architecture that entirely avoids the unpredictability of traditional spring-back mechanisms.

### Key Features
* **Mechanism:** Motor-driven contact and push system ensuring a synchronized, deterministic "blooming" phase.
* **Locking Matrix:** Self-aligning $90^\circ$ male/female V-Groove edge joints that transition individual segments into a rigid structural hoop upon full deployment.
* **Velocity Management:** Viscous-linear damping and solid-body contact tuning to enforce slow, controlled terminal seating against the base.
* **Solver Optimization:** Built and validated using the **GSTIFF** dynamic integrator to completely eliminate numerical drift and solver explosions.

---

## 🛠️ Material Architecture & Space-Qualification

The structural components are specified with space-grade materials to eliminate vacuum outgassing, prevent thermal distortion (warping), and maximize strength-to-weight ratios:

| Component | Specified Material | Mechanical Property | Critical Advantage |
| :--- | :--- | :--- | :--- |
| **Reflector Petals** | Toray M55J Carbon Fiber / Cyanate Ester Resin | $E_1 \approx 310 \text{ GPa}$, Quasi-Isotropic $[0/45/-45/90]_s$ | Near-zero CTE ($\alpha \approx -0.4 \times 10^{-6}\text{ /K}$); prevents orbital thermal warping. |
| **Central Hub** | Titanium Grade 5 (Ti-6Al-4V) | Yield Strength: $880 \text{ MPa}$ | Extreme yield strength to handle mechanical translation and tracking stresses. |
| **Base Interface** | Nitronic 60 Stainless Steel | High Internal Material Damping Coefficient | Naturally absorbs structural shockwaves; exceptional anti-galling properties in a vacuum. |

---

## 📊 Simulation Methodology & Kinematics

The physics environment is managed inside **SolidWorks Motion Analysis** to isolate real-world mechanical behavior during the single-event opening sequence.



### 1. Mechanical Constraint Fixes (Anti-Explosion)
To prevent the solver from dropping tracking data over extended timelines, over-constraining Width Mates were eliminated. Lateral panel centering is locked using **Plane-to-Plane Coincident Mates** mapped directly to infinite reference planes, dropping the system's mathematical degrees of freedom (DoF) down to a highly predictable $1$.

### 2. Contact Dynamics Settings
The terminal stroke impact profile is regulated via a custom User-Defined Solid Body Contact relationship to minimize elastic rebound:
* **Impact Solver:** GSTIFF Numerical Integrator
* **Sampling Rate:** $100\text{--}150\text{ Frames Per Second (FPS)}$
* **Contact Parameters:** High Damping Coefficient ($c \ge 500\text{ N}\cdot\text{s/m}$) matched with Static Friction ($\mu_s = 0.8$) to freeze the hub instantly upon striking the seat.

##Preview
<img width="959" height="708" alt="Screenshot 2026-05-25 162705" src="https://github.com/user-attachments/assets/de6e298b-584a-45aa-8545-7ce1812a7941" />
<img width="609" height="683" alt="Screenshot 2026-05-25 162715" src="https://github.com/user-attachments/assets/a741b3c2-75dc-4b9c-9d71-55e078fdb9f5" />
<img width="693" height="624" alt="Screenshot 2026-05-25 162725" src="https://github.com/user-attachments/assets/8620f28b-3e38-4cd3-ab51-402b33960983" />

<img width="609" height="683" alt="Screenshot 2026-05-25 162715" src="https://github.com/user-attachments/assets/12a56813-7bfe-4481-b912-879f40800713" />
<img width="693" height="624" alt="Screenshot 2026-05-25 162725" src="https://github.com/user-attachments/assets/f1e57286-fc55-40bc-9052-5862e0409d3e" />
