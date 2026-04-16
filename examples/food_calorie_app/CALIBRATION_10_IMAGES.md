# 10张图快速校准（简版）

目标：用少量样本把热量估算调到更稳定。

## 1) 选图（10张）
- 6张单菜 + 4张多菜
- 尽量同一拍摄角度和距离

## 2) 记录
每个检测目标记 3 列：
- `class_name`
- `estimated_grams`（程序输出）
- `expected_grams`（你的经验值）

并计算：`ratio = expected / estimated`

## 3) 调参数（按类）
编辑 `food_calories_template.json`：
- 克数偏小：上调 `portion_grams_s/m/l`（或 `thickness_cm` / `density_g_per_cm3`）
- 克数偏大：下调对应参数
- 克数基本准但热量偏差大：调 `kcal_per_100g`

## 4) 复测
再跑同样10张图，重复步骤2~3，直到误差收敛。

## 5) 通过标准（课程项目）
- 多数类别总热量趋势正确（大份 > 小份）
- 主要类别误差控制在可接受范围（可按 ±20%~30% 作为参考）
