# Visualization Gallery

This folder contains the final chart images for the **Card RPG Numerical Analysis** portfolio project.

These images are not raw data screenshots. They are selected visual summaries that explain the main design logic of the project: character growth, resource pressure, combat formula behavior, numerical risk, and team evaluation.

---

## Overview

| Image | What It Shows | Why It Matters |
| --- | --- | --- |
| `growth_curve.png` | Lv.1–60 EXP and power scaling | Shows how the progression curve creates early feedback and late-game investment |
| `resource_pressure_pivot.png` | Estimated resource pressure by progression stage | Shows how resource bottlenecks shift across early, mid, and late game |
| `defense_reduction_curve.png` | Defense mitigation with diminishing returns | Shows why defensive stats need nonlinear scaling to avoid invincible units |
| `crit_expected_value.png` | Expected damage scaling from crit rate and crit damage | Shows how crit systems can create late-game burst inflation |
| `team_evaluation_radar.png` | Multi-dimensional team role coverage | Shows why team strength cannot be explained by power score alone |

---

## Visual Narrative

The five charts are designed to be read as a complete numerical design story:

```
Growth Curve
→ Resource Pressure
→ Defense / Crit Formula Behavior
→ Numerical Risk Control
→ Team Evaluation
```

Together, they show how a card RPG numerical model connects **progression pacing**, **resource economy**, **combat formulas**, and **team-building strategy**.

---

## `growth_curve.png`

**Chart focus:** Character progression pacing

This chart visualizes Lv.1–60 growth through EXP requirement and power scaling.

It shows that early levels are designed to provide fast upgrade feedback, while later levels require more investment and create longer-term progression goals.

**Design takeaway:**  

A good growth curve should not be purely linear. It should give players fast early motivation, then gradually introduce planning and resource pressure.

---

## `resource_pressure_pivot.png`

**Chart focus:** Resource bottleneck distribution

This pivot chart visualizes estimated resource pressure across different progression stages.

Instead of treating all resources as equally scarce, the model compares resource requirements through estimated farming pressure. This makes it easier to understand which resources become bottlenecks at each stage.

**Design takeaway:**  

Resource pressure should shift over time. Early progression should feel smooth, mid-game should introduce planning, and late-game should create meaningful long-term investment goals.

---

## `defense_reduction_curve.png`

**Chart focus:** Defensive stat scaling

This chart visualizes the defense mitigation formula:

```
DefenseReduction = DEF / (DEF + DefenseConstant)
```

The curve shows diminishing returns: as DEF increases, each additional point of defense provides less extra damage reduction.

**Design takeaway:**  

Nonlinear defense scaling helps prevent tanks or defensive teams from becoming nearly invincible while still allowing defense to feel valuable.

---

## `crit_expected_value.png`

**Chart focus:** Crit scaling risk

This chart shows how crit rate and crit damage affect expected damage output.

The model uses:

```
CritExpectedMultiplier = 1 + CritRate × CritDamageBonus
```

As both crit rate and crit damage increase, expected output can rise quickly, especially for burst, multi-hit, or execute-based characters.

**Design takeaway:**  

Crit systems need careful control because crit rate and crit damage scale together. If both are too accessible, late-game burst damage can inflate quickly.

---

## `team_evaluation_radar.png`

**Chart focus:** Team strength beyond power score

This radar chart compares teams across multiple dimensions:

```
DPS
Survival
Control
Healing
Energy
Synergy
```

It shows that teams with similar raw power can have very different functional profiles. A burst team, sustain team, and control team may perform differently depending on combat context.

**Design takeaway:**  

Power score is useful as a quick reference, but it cannot fully represent real team strength. Team performance depends on role coverage, skill timing, sustain, control, energy cycle, and synergy.

---

## Summary

These visualizations are included to make the project easier to understand at a glance.

They demonstrate that the project is not only a spreadsheet exercise, but a complete numerical design model covering:

- Character growth pacing
- Resource economy pressure
- Combat formula behavior
- Balance risk analysis
- Team composition evaluation

The goal of these images is to help reviewers quickly understand the design reasoning behind the workbook and documentation.