---
layout: post
title: "Understanding Radiative Torques"
date: 2026-05-25
---

# Rotational Disruption from radiative torques

Current goal, to define, derive and understand the paper.

## Introduction

Your introductory paragraph goes here.

---

## Background

Your background section goes here.

---

## Key Concept / Theorem

> **Definition (Name of Concept):**
> Write your definition or theorem statement here. For example:
> A grain of radius $a$ subject to a radiative torque $\Gamma$ will spin up at a rate given by...

---

## Mathematical Derivation

Inline math uses single dollar signs: $\omega = 2\pi f$

Display math uses double dollar signs:

$$
\frac{d\omega}{dt} = \frac{\Gamma}{I}
$$

Where:
- $\omega$ — angular velocity
- $\Gamma$ — applied torque
- $I$ — moment of inertia

---

## Code Example

```python
# Your Python code here
def compute_spinup_rate(torque, moment_of_inertia):
    """
    Compute the angular acceleration of a grain.
    """
    return torque / moment_of_inertia

omega_dot = compute_spinup_rate(Gamma, I)
print(f"Spin-up rate: {omega_dot:.4f} rad/s²")
```

```bash
# Shell commands if needed
pip install numpy scipy matplotlib
```

---

## Results / Discussion

Your discussion goes here.

---

## Conclusion

Your conclusion goes here.

---

## References

- A Rotational Disruption Crisis for Zodiacal Dust
The Astrophysical Journal Letters
2025-04-01 | Journal article
DOI: [10.3847/2041-8213/adc133](10.3847/2041-8213/adc133)
Contributors: Kedron Silsbee; Brandon S. Hensley; Jamey R. Szalay; Petr Pokorný; Jeong-Gyu Kim

