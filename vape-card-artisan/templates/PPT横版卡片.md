# 雾卡匠 · PPT 横版卡片模板（16:9）

> 本模板用于生成**横版 1280 × 720（= PPT 一页）**的便携卡片式雾化产品口味卡。
> 与默认竖版 template-v3.html（手机端优先）相对，本版面向**陈列屏 / PPT 汇报 / 横版展示**。
> 配套骨架：`templates/template-h-ppt.html`（占位符驱动，可直接替换生成）。

---

## 1. 何时使用横版

- 用户明确要「横版 / PPT 一页 / 16:9 / 陈列屏」尺寸
- 需要把产品渲染图与文案并排呈现，而非竖版「图在上、文在下」
- 单张卡展示一个口味，横排三栏：左图 / 中铭牌+文案 / 右雷达+香韵

默认仍是竖版 template-v3.html；仅在用户点名横版时启用本模板。

---

## 2. 卡片技术规范

| 项 | 值 |
|----|----|
| 画布 | 1280 × 720 px，固定尺寸（`body { width:1280px; height:720px }`），`overflow:hidden` |
| 布局 | CSS Grid 三栏：`[hero 304px] [middle 1fr] [right 1fr]`，中间 26px 间隔 |
| 底色 | 暖纸色 `#F6F7F0`（或风味辅色微调），head/foot 横跨全宽 |
| 字体 | 标题/英文：Cormorant Garamond（衬线 italic）；中文：Noto Serif SC |
| 交付 | 单文件 HTML，内联 CSS，渲染图 base64 内嵌（standalone），仅外链 Google Fonts |
| 合规脚注 | 底部固定：`本描述仅指香韵与雾气体感，不涉及功效宣称` + 罗马数字年份（MMXXVI = 2026）|

### 三栏内容分配

- **左栏 hero（304px 宽，满高）**：产品渲染图，绝对定位叠加
  - 左上角药丸：`NO. 0X`（半透明深底 blur）
  - 右下角药丸：`ORIVA`（半透明深底 blur，用于压制图片自带水印）
- **中栏 middle**：铭牌 + 产地 + 三大文案块
  1. 铭牌：英文名（Cormorant italic 600 ~36px）+ 中文名（Noto Serif SC 300 ~18px）+ 品类标签（CARD · PORTABLE）
  2. 产地 ORIGIN：中文 + 英文
  3. **Tonality / 香韵定调**：一句话通感
  4. **Extract / 提取工艺**：pill 标签 + 描述句
  5. **Chromatic Scale / 风味色谱**：三段渐变条 + TOP/MID/BASE 刻度
- **右栏 right**：数据与香韵
  - **Flavor Data / 风味数据**：雷达 SVG（7 维内联）+ 档案编号
  - **Main Accords / 香韵分路**：2–7 条横向柱状图（天然色相）

### head / foot

- head（顶部全宽）：左 `ORIVA · CARD · PORTABLE VAPE` ；右 `Spec. N° 0X · [拼音] · 07.2026`
- foot（底部全宽）：左合规脚注；右 `MMXXVI`（罗马数字年份）

---

## 3. 色彩与字体变量（示例：青柠）

```css
:root{
  --font-serif: "Cormorant Garamond","Noto Serif SC",Georgia,serif;
  --font-cn: "Noto Serif SC","Cormorant Garamond",serif;
  --color-ink: #2A2522;
  --color-ink-soft: #8C7A66;
  --accent: #8A9C68;        /* 风味主色 */
  --accent-soft: #C4D0A8;
  --accent-deep: #6C7858;
}
```

> 主色/辅色/底色一律压到莫兰迪区间（饱和度 15%–35%），禁止纯黑纯白大面积。
> 各口味参考 `agents/vape-card-artisan.md` 文末「风味色彩映射参考表」。

---

## 4. 亚克力电子烟油瓶 · 渲染图规范（核心）

这是横版卡与竖版卡**最大的差异点**：产品图必须是**修长亚克力油瓶 + 电子烟吸嘴**，不是圆口玻璃瓶。

### 4.1 ImageGen prompt 模板（image-to-image 高保真）

以一张已确认风格的油瓶图（`lime.png` 类）为 `image1`，`input_fidelity: 0.9`，保持瓶身/布局/水印位不变，仅换液体色与道具：

```
保持完全相同的 [高瘦磨砂半透明亚克力电子烟油瓶，顶部带圆润的电子烟烟杆式吸嘴，
不是圆口玻璃瓶开口]，相同的瓶身比例与居中位置，相同的米色纹理纸卡与深色木板台面，
相同的深棕莫兰迪暗调背景，相同的柔和单向棚拍布光，相同的左上角 'NO. 0X' 与
右下角 'ORIVA' 排版位。仅替换周边原料道具为 [风味实物列表]，并将瓶内液体换成 [风味色] 色调。
影棚产品摄影，高端杂志感，浅景深。
禁止圆口玻璃瓶、滴管瓶、酒瓶，禁止额外 logo 与水印。
```

### 4.2 关键约束（用户硬要求）

- **瓶型**：修长长方体亚克力，半透明磨砂，顶部是类似电子烟烟杆的**圆润吸嘴**（决不能是圆形瓶口 / 软木塞 / 滴管）
- **比例与排版**：对齐参考母版的长宽高与页面布局；NO. 编号在左上、ORIVA 在右下
- **底面**：米色纸卡 + 深色木板，深棕莫兰迪暗调
- **光**：单侧柔光，长投影，高光克制
- **液体**：分层渐变（前调浅 → 后调深），丁达尔微透
- **道具**：丰盛聚簇（完整 + 裂开 + 碎片 + 粉末），围绕主体一侧，另一侧留白
- 出图尺寸 `1024 × 1536`（竖图，CSS `object-fit:cover` 裁切入 304px 左栏）

### 4.3 水印处理

生成图右下角常带平台 `AI 生成` 水印，会与 `ORIVA` 重叠。卡片在 hero 右下 `.no` 处加
`background: rgba(42,34,24,.72); padding:4px 10px; border-radius:999px; backdrop-filter:blur(4px)` 药丸，
覆盖水印并突出 ORIVA 文字。

---

## 5. HTML 骨架占位符索引（见 template-h-ppt.html）

| 占位符 | 含义 |
|--------|------|
| `{{TITLE}}` | 页面标题 |
| `{{COLOR_CSS}}` | :root 色彩变量 |
| `{{HERO_IMAGE}}` | 渲染图 src（base64 或路径） |
| `{{PRODUCT_NO}}` | 编号 `01`–`05` |
| `{{NAME_EN}}` / `{{NAME_CN}}` | 英文名 / 中文名 |
| `{{PINYIN}}` | 口味拼音（Spec. 编号用） |
| `{{CATEGORY}}` | 品类标签 `CARD · PORTABLE` |
| `{{ORIGIN_CN}}` / `{{ORIGIN_EN}}` | 产地中 / 英 |
| `{{TONALITY}}` | 香韵定调一句话 |
| `{{EXTRACT_PILLS}}` | 提取工艺 pill HTML |
| `{{EXTRACT_DESC}}` | 提取工艺描述句 |
| `{{SPECTRUM_GRADIENT}}` | 色谱条渐变 CSS |
| `{{SPECTRUM_TICKS}}` | TOP/MID/BASE 三段文案 |
| `{{RADAR_SVG}}` | 完整雷达 SVG |
| `{{ACCORD_ROWS}}` | 香韵分路柱状图 HTML |
| `{{YEARS}}` | 罗马数字年份 `MMXXVI` |

> 雷达为纯内联 SVG（`viewBox 0 0 284 284`），维度数 3–7 动态，详见竖版 skill 的「雷达图规范」。

---

## 6. 生成流程（横版）

1. **Phase 0** 参数确认（品类 / 提取工艺 / 香韵分路 / 雷达维度评分 / 四段文案 / 色谱）— 同竖版六阶段，不可跳过
2. **Phase 2** 取色 → 写入 `{{COLOR_CSS}}`
3. **Phase 4** 用 §4.1 模板生成油瓶渲染图（image-to-image 高保真）
4. **Phase 5** 用 `template-h-ppt.html` 替换占位符，base64 内嵌渲染图，输出 standalone HTML
5. `present_files` 预览；`index.html` 可 iframe 聚合多张横版卡

---

## 7. 合规红线

- 只写「香韵 / 凉度 / 层次 / 留香 / 雾感 / 便携氛围」，禁功效/健康/成瘾词
- 技术参数区只写风味化学信息（提取工艺 / 香韵分路），禁尼古丁含量、击喉强度等性能数据
- 底部脚注固定合规声明
