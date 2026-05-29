# 卡牌 RPG 数值拆解

**角色成长、战斗公式、资源循环与阵容评估**

这是一个面向游戏数值策划 / 系统策划 / 战斗策划岗位的作品集项目。项目基于一个假设的卡牌 RPG / 放置 RPG 模型，分析角色成长、战斗属性、技能倍率、资源消耗、阵容评估和数值设计风险。

> 本项目是个人建模与分析练习。
> 

> 不代表商业卡牌项目经验，也不复刻任何真实游戏的具体数值。
> 

---

## 项目目标

这个项目用于展示我以下能力：

- 拆解卡牌 / 放置 RPG 的角色成长系统
- 建模等级、突破、星级、技能、装备和阵营成长
- 建立简化但可解释的战斗公式
- 分析 Lv.1–60 的资源压力与成长节奏
- 用多维模型评估阵容强度，而不是只看战力
- 识别暴击膨胀、治疗护盾过强、付费差距等数值风险

---

## 适用岗位

- 数值策划实习生
- 系统策划实习生
- 战斗策划实习生
- 卡牌 / 放置 RPG 策划
- 制作人培训生

---

## 仓库结构

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

## XLSX Sheet 结构

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

| 层级 | Sheet | 作用 |
| --- | --- | --- |
| 配置层 | `01_Characters`, `02_Growth_Curve`, `03_Breakthrough`, `04_Star_System`, `05_Skills` | 定义基础数据和成长系统 |
| 计算层 | `06_Combat_Calculator`, `10_Character_Stats`, `11_Damage_Test` | 将配置转化为最终属性和伤害输出 |
| 资源 / 阵容层 | `07_Resource_Cost`, `08_Team_Evaluation`, `12_Resource_Dashboard` | 展示资源压力和阵容评估 |
| 展示 / 风险层 | `09_Risk_Checklist`, `13_Charts_Index` | 总结风险和图表输出计划 |

---

## 核心公式

```
期望伤害 =
ATK
× 技能倍率
× (1 - DEF / (DEF + 防御常数))
× (1 + 暴击率 × 暴击伤害加成)
× (1 + 增伤 + 属性增伤 + 阵营增伤)
× (1 - 减伤)
× 等级修正
```

---

## 示例角色

| 角色 | 定位 | 设计重点 |
| --- | --- | --- |
| 绯刃·赛琳 | 单体爆发输出 | 爆发伤害、斩杀逻辑、击杀回能 |
| 星环术士·弥娅 | AOE 法术输出 | 群体压血、持续伤害、能量循环 |
| 白羽祭司·诺雅 | 治疗 / 护盾辅助 | 续航、保护、净化、反爆发 |

---

## 设计洞察

- 战力适合作为成长提示，但不能完整代表阵容强度。
- 暴击率、暴击伤害、速度和多段攻击容易造成后期数值膨胀。
- 治疗和护盾会直接影响关卡难度设计。
- 重复角色不应该只提供线性属性增长。
- 自动战斗中的技能循环会显著影响角色价值。
- 阵容协同有时比单卡强度更重要。
- 资源瓶颈应当分阶段出现，而不是所有资源同时卡住玩家。

---

## 使用工具

- Excel / Google Sheets
- Markdown 文档
- GitHub 仓库中的 CSV 数据文件
- 基础图表可视化

---

## 免责声明

本项目是个人作品集和建模练习。所有数值均为假设数据，仅用于设计分析展示。