# Card RPG Numerical Analysis

**Character Progression, Combat Formulas, Resource Economy, and Team Evaluation**

This is a portfolio project for game numerical design, system design, and combat design roles. It analyzes a hypothetical card RPG / idle RPG model, focusing on character growth, combat attributes, skill scaling, resource costs, team evaluation, and numerical design risks.

> This is a personal modeling and analysis project. It does not claim commercial card RPG development experience, and it does not copy numerical data from any existing game.
> 

---

## Project Goals

This project demonstrates my ability to:

- Break down character progression systems in card / idle RPGs
- Model level, ascension, star-up, skill, equipment, and faction growth
- Build simplified but explainable combat formulas
- Analyze Lv.1–60 resource pressure and growth pacing
- Evaluate team strength beyond raw power score
- Identify numerical design risks such as crit scaling, shield stacking, healing inflation, and paid progression gaps

---

## Target Roles

- Numerical Designer Intern
- System Designer Intern
- Combat Designer Intern
- Card RPG / Idle RPG Designer
- Game Designer Trainee

---

## Repository Structure

```
card-rpg-numerical-analysis/
├── README.md
├── README_CN.md
├── docs/
│   └── full_design_document.md
├── data/
│   ├── 01_characters.csv
│   ├── 02_growth_curve.csv
│   ├── 03_breakthrough.csv
│   ├── 04_star_system.csv
│   ├── 05_skills.csv
│   ├── 06_combat_calculator.csv
│   ├── 07_resource_cost.csv
│   ├── 08_team_evaluation.csv
│   ├── 09_risk_checklist.csv
│   ├── 10_character_stats.csv
│   ├── 11_damage_test.csv
│   ├── 12_resource_dashboard.csv
│   └── 13_charts_index.csv
├── workbook/
│   └── Card_RPG_Numerical_Model.xlsx
└── images/
    ├── growth_curve.png
    ├── resource_pressure.png
    ├── defense_reduction_curve.png
    ├── crit_expected_value.png
    └── team_evaluation_radar.png
```

---

## XLSX Sheet Structure

```
01_Characters
02_Growth_Curve
03_Breakthrough
04_Star_System
05_Skills
06_Combat_Calculator
07_Resource_Cost
08_Team_Evaluation
09_Risk_Checklist
10_Character_Stats
11_Damage_Test
12_Resource_Dashboard
13_Charts_Index
```

| Layer | Sheets | Purpose |
| --- | --- | --- |
| Configuration | `01_Characters`, `02_Growth_Curve`, `03_Breakthrough`, `04_Star_System`, `05_Skills` | Defines base data and growth systems |
| Calculation | `06_Combat_Calculator`, `10_Character_Stats`, `11_Damage_Test` | Converts configuration into final stats and damage outputs |
| Progression / Team | `07_Resource_Cost`, `08_Team_Evaluation`, `12_Resource_Dashboard` | Shows resource pressure and team strength evaluation |
| Presentation / Risk | `09_Risk_Checklist`, `13_Charts_Index` | Summarizes risks and visual output plan |

---

## Key Formula

```
ExpectedDamage =
ATK
× SkillMultiplier
× (1 - DEF / (DEF + DefenseConstant))
× (1 + CritRate × CritDamageBonus)
× (1 + DamageBonus + ElementBonus + FactionBonus)
× (1 - DamageReduction)
× LevelModifier
```

---

## Sample Characters

| Character | Role | Design Focus |
| --- | --- | --- |
| Serin, Crimson Blade | Single-target burst DPS | Burst damage, execute logic, kill energy refund |
| Mia, Star Ring Mage | AOE magic DPS | Multi-target pressure, DOT, energy loop |
| Noa, White Feather Priest | Healer / shield support | Sustain, protection, cleanse, anti-burst |

---

## Key Design Insights

- Power score is useful as a progression signal, but it cannot fully represent team strength.
- Crit rate, crit damage, speed, and multi-hit skills can easily create late-game scaling issues.
- Healing and shielding directly affect stage difficulty design.
- Duplicate characters should not only provide linear stat growth.
- Auto-battle skill cycles strongly affect character value.
- Team synergy can be more important than individual unit strength.
- Resource bottlenecks should appear gradually across early, mid, and late game stages.

---

## Tools

- Excel / Google Sheets
- Markdown documentation
- CSV data files for GitHub
- Basic chart visualization

---

## Disclaimer

This project is a personal portfolio and modeling exercise. All numbers are hypothetical and created for design analysis purposes.