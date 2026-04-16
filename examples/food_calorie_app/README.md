## Food detection + calorie estimation (Streamlit)

### 1) 训练模型
在项目根目录运行：

```bash
python examples/food_calorie_app/train_food_detect.py
```

训练完成后使用 `best.pt`（示例）：
`runs/detect/runs/detect/food_v1_final50/weights/best.pt`

### 2) 启动网页

```bash
python -m streamlit run examples/food_calorie_app/app.py
```

在侧边栏 `Model path` 填你的 `best.pt` 路径。

### 3) 热量估算说明
- 推荐：`S/M/L 份量估算`（无真实克数时更稳定）
- 可选：`标定宽度 + 体积粗估`
- `food_calories_template.json` 的 key 必须和模型类别名一致，否则会使用 unknown 默认值

### 4) 豆包建议（可选）
先安装依赖并设置环境变量：

```bash
python -m pip install openai
```

PowerShell:

```powershell
$env:ARK_API_KEY="你的key"
$env:ARK_BASE_URL="https://ark.cn-beijing.volces.com/api/v3"
$env:ARK_ENDPOINT_ID="ep-xxxxxx"
```

页面中启用 “AI饮食建议（豆包）” 即可生成建议。

### 5) 校准
见 `CALIBRATION_10_IMAGES.md`（10张图快速校准）。

