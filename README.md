# Aerodynamic Drag & Energy-Optimal Path Planner for Long-Range UAVs

![Python 3](https://img.shields.io/badge/Language-Python%203.10-blue)
![Optimization](https://img.shields.io/badge/Domain-Aerodynamics%20%26%20Graph%20Search-green)
![Developer](https://img.shields.io/badge/Developer-Ayoub%20Lahmar-brightgreen)

An energy-aware path planning system that replaces traditional Euclidean metric costs with **Aerodynamic Power Metrics**. Integrates parasitic drag \(P_{\text{drag}}\) and ambient wind fields into an admissible \(A^*\) search algorithm to minimize total energy expenditure (Joules).

Implemented by **Ayoub Lahmar** ([@Redayoub-lang](https://github.com/Redayoub-lang)).

## 📐 Aerodynamic Power Model

Total instantaneous power \(P_{\text{total}}\) required during forward transition is:

$$
P_{\text{total}} = \sqrt{\frac{(mg)^3}{2 \rho A_{\text{rotor}}}} + \frac{1}{2} \rho C_d A_{\text{frontal}} \|\vec{V}_{\text{air}}\|^3
$$

Path traversal cost integrates power over transit duration \(T = \frac{d}{\|\vec{V}_{\text{ground}}\|}\):

$$
E = \int_{0}^{T} P_{\text{total}}(\vec{V}_{\text{air}}(t)) \, dt
$$

## 💻 Run Pipeline

```bash
python energy_planner.py
