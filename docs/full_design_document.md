# Card RPG Numerical Analysis — Full Design Document

## 1. Research Framework

### Project Purpose

This project analyzes a hypothetical card RPG / idle RPG numerical model. It is designed as a portfolio project for numerical design, system design, and combat design roles.

The project demonstrates the ability to analyze character progression systems, combat attributes, skill multipliers, role differentiation, combat formulas, resource costs, power inflation, and numerical design risks.

This project does **not** claim commercial card RPG development experience. All numbers are hypothetical and created for design modeling.

### Target Roles

| Role | Relevant Content |
| --- | --- |
| Numerical Designer Intern | Growth curves, damage formulas, combat variables, power evaluation |
| System Designer Intern | Character progression, resource loops, long-term goals |
| Combat Designer Intern | Skill roles, combat pacing, role interactions |
| Card / Idle RPG Designer | Auto-battle cycles, team synergy, resource pressure |
| Game Designer Trainee | System thinking, player behavior, balance risks |

### Scope

The model assumes a 5-character team formation, role / class / faction-based character structure, level / ascension / star-up / skill / equipment growth, semi-auto or auto combat, and energy-based active skills.

### Not Included

| Not Included | Reason |
| --- | --- |
| Full monetization pricing | Focus is combat and progression modeling |
| Real commercial game values | Avoid copying actual game configurations |
| Full server implementation | Portfolio focuses on design and spreadsheet modeling |
| UI / art / narrative | Outside numerical design scope |
| Large-scale LiveOps calendar | Can be future extension |
| Advanced PvP matchmaking | Not core to this model |

---

## 2. Character Growth System

```
Total Character Strength
= Base Stats
× Level Growth
× Ascension Growth
× Star Growth
× Skill Growth
× Equipment Growth
× Exclusive System Growth
× Team / Faction Modifiers
× Battle Context Modifiers
```

| System | Player Action | Numerical Variables | Resource Cost | Design Purpose | Risk |
| --- | --- | --- | --- | --- | --- |
| Level | Spend EXP to level up | HP, ATK, DEF growth | EXP materials, gold | Basic and frequent growth feedback | Overly strong level scaling reduces strategy |
| Level Cap | Reach cap and unlock next stage | Max level, growth coefficient | Ascension materials, gold | Stage-based progression gate | Hard gates may cause frustration |
| Ascension | Collect materials to advance | Level cap, stat bonus, skill unlock | Class materials, faction materials | Mid-term goal and stage pacing | Too much power invalidates old content |
| Star-up | Use duplicates or shards | Stat multiplier, passive upgrades | Character shards, universal shards | Long-term gacha goal | Large star gaps hurt F2P experience |
| Skill Level | Upgrade skills | Multiplier, chance, duration | Skill books, gold | Strengthen role identity | Over-scaling skills can break balance |
| Equipment | Obtain and enhance gear | ATK, HP, DEF, crit, speed | Gear, stones, gold | General growth path and material sink | Random substats may create excessive grind |
| Exclusive Weapon | Unlock role-specific power | Special passive, mechanism upgrade | Exclusive materials, shards | Late-game identity and depth | Can make no-exclusive versions feel useless |
| Rune / Talent | Choose build path | Crit, speed, damage bonus, energy | Rune materials, talent points | Build diversity | If one option is optimal, choice becomes fake |
| Faction / Bond | Build faction teams | Team ATK%, HP%, speed, energy | Collection cost | Encourage team-building and roster breadth | Overpowered bonuses reduce team freedom |
| Rarity | Pull different rarity units | Base stats, growth rate, skill complexity | Gacha currency | Differentiates acquisition value | Low rarity units may become irrelevant |

---

## 3. Combat Attribute System

| Attribute | Combat Experience | Role Value | Balance Risk |
| --- | --- | --- | --- |
| HP | Determines damage tolerance | Tanks, frontliners, healing targets | High HP slows combat too much |
| ATK | Base for damage, healing, and shields | DPS, healers, shield supports | If too universal, ATK becomes dominant |
| DEF | Reduces incoming damage | Tanks and durable units | Linear defense can create unkillable units |
| Crit Rate | Chance to deal critical damage | Burst and sustained DPS | High crit causes large output variance |
| Crit Damage | Critical hit multiplier | Crit-based DPS | Scales strongly with crit rate |
| Speed | Turn order or action frequency | Control, healers, energy supports | First-turn advantage can dominate PvP |
| Hit / Accuracy | Control and debuff reliability | Control and debuff units | Too much hit removes counterplay |
| Resistance / Evasion | Avoid control or attacks | Tanks, cores, PvP units | Too much randomness hurts readability |
| Damage Bonus | Increases outgoing damage | DPS units | Multiple bonus layers can inflate damage |
| Damage Reduction | Lowers incoming damage | Tanks and defensive supports | Stacking reduction can create immortal teams |
| Healing Bonus | Increases healing output | Healers | Excessive healing invalidates stage damage |
| Energy / Rage | Controls skill frequency | Ultimate-dependent units | Fast cycles can break cooldown pacing |

---

## 4. Role and Skill Design

| Role | Core Variables | Skill Design Focus | Team Value | Risk |
| --- | --- | --- | --- | --- |
| Single-target DPS | ATK, multiplier, crit, execution bonus | High multiplier, focus fire, execute | Kill boss or enemy core | PvP one-shot risk |
| AOE DPS | ATK, AOE multiplier, target count, energy | Wave clear, group pressure | Campaign and multi-target combat | Can replace single-target DPS if too strong |
| Tank | HP, DEF, damage reduction, taunt | Damage absorption, protection | Stabilizes frontline | Too durable slows combat |
| Healer | ATK / HP, healing multiplier, frequency | Single / group healing, sustain | Increases tolerance and stability | Forces burst or anti-heal stage design |
| Shield Support | ATK / HP, shield multiplier, duration | Preemptive protection | Anti-burst, backline protection | Stackable shields can create immortal teams |
| Control | Hit, speed, control chance, duration | Stun, silence, freeze, pushback | Disrupts enemy cycle | First-turn control can remove interaction |
| Buffer | Buff value, duration, uptime | ATK, speed, crit, energy buffs | Amplifies carry units | Buff stacking can cause damage explosion |
| Debuffer | DEF down, vulnerability, slow, anti-heal | Lower enemy defenses or recovery | Raises team damage or limits enemies | Vulnerability stacking can be too efficient |
| Summoner | Summon stats, duration, inheritance | Extra units, damage soak | Increases tactical complexity | Too many units reduce clarity |
| Energy Support | Energy gain, speed, skill cost | Energy generation and cycle control | Enables faster ultimates | Infinite ultimate loops |
| Burst Unit | Multiplier, crit, energy cost | Short-window high damage | Kills key targets | One-shot experience |
| Sustained DPS | Attack frequency, DOT, stacking | Long-fight scaling | Boss and guild content | Can overpower burst in long fights |

```
Actual Skill Value
= Skill Multiplier
× Release Frequency
× Target Count
× Buff / Debuff Value
× Timing
× Auto-battle Reliability
```

---

## 5. Combat Formulas

```
BaseDamage = ATK × SkillMultiplier
DefenseReduction = DEF / (DEF + DefenseConstant)
CritExpectedMultiplier = 1 + CritRate × CritDamageBonus
DamageBonusMultiplier = 1 + DamageBonus + ElementBonus + FactionBonus
DamageReductionMultiplier = 1 - DamageReduction
```

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

```
HealingAmount =
CasterATK
× HealingMultiplier
× (1 + HealingBonus)
× TargetHealingReceivedModifier
```

```
ShieldAmount =
CasterATK
× ShieldMultiplier
× (1 + ShieldBonus)
```

---

## 6. Resource and Progression Model

| Stage | Level Range |
| --- | --- |
| Early | Lv.1–20 |
| Mid | Lv.21–40 |
| Late | Lv.41–60 |
| Principle | Explanation |
| --- | --- |
| Fast early game | Players should understand growth quickly |
| Mid-game branching | Players begin choosing main team members |
| Slower late game | Long-term goals need pacing |
| Stage gates | Ascension controls major growth jumps |
| Resource mismatch | EXP, gold, skill books, shards, and gear should not all be equally abundant |

---

## 7. Team and Power Evaluation

```
TeamScore =
DPSScore × 0.30
+ SurvivalScore × 0.25
+ ControlScore × 0.15
+ HealingScore × 0.15
+ EnergyScore × 0.10
+ SynergyScore × 0.05
```

Power score cannot fully represent skill timing, control coverage, healing and shield uptime, energy cycle, faction advantage, buff / debuff synergy, boss mechanic adaptation, or auto-battle targeting reliability.

---

## 8. Sample Characters

| Character | Role | Core Design Value | Main Risk |
| --- | --- | --- | --- |
| Serin, Crimson Blade | Single-target burst DPS | Execute low-HP targets and chain kills | Crit + execute + energy refund can create one-shot chains |
| Mia, Star Ring Mage | AOE magic DPS | Multi-target pressure and wave clear | AOE total multiplier and energy loop can become too efficient |
| Noa, White Feather Priest | Healer / shield support | Team sustain, shield, cleanse, anti-burst | Healing + shield + cleanse may create mandatory support |

---

## 9. Design Insights

1. Duplicate characters should not only provide linear power.
2. Crit and speed can easily scale out of control.
3. Healing and shielding change stage design.
4. Paid players should grow faster, not ignore strategy.
5. Auto-battle skill cycles strongly affect value.
6. Team synergy can be more important than single-card strength.
7. AOE skills must consider total effective multiplier.
8. Defense and damage reduction need diminishing returns or caps.
9. Resource bottlenecks should appear gradually.
10. Power score is a guide, not a full strength model.