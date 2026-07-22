# 焦糖玛奇朵 v2 — 完整参数确认单示例

> 本文件记录了一次完整的 Phase 0 参数确认过程，作为 skill 使用的参考示例。
> 口味卡交付物：`caramel-macchiato-card-v2-standalone.html`（2MB，base64 内嵌渲染图）。

---

## Phase 0 参数确认单

| 板块 | 最终确认值 |
|------|-----------|
| **品类** | 卡片式便携 |
| **提取工艺** | 冷萃 Cold Brew（咖啡）+ 分子蒸馏 Molecular Distillation（可可） |
| **香韵分路（6 路）** | 焦糖 30% · 咖啡 25% · 坚果 15% · 奶香 10% · 可可 10% · 烘焙 10% |
| **雷达维度（6 维）** | 还原度 4 · 凉度 2 · 甜度 3 · 层次 5 · 留香 3 · 耐抽性 4 |
| **EXTRACT 描述句** | 长版 · 52 字 |
| **色谱条三段** | TOP·CARAMEL / MID·COFFEE / BASE·NUT |

---

## EXTRACT 描述句（长版）

> 以冷萃工艺温和萃取咖啡豆的烘焙焦香，再以分子蒸馏技术提纯可可的油脂醇香，两种提取方式叠加出层次分明的焦糖玛奇朵甜点调性。

---

## 感官四段文案（定稿）

| 段落 | 文案 |
|------|------|
| **Tonality** 香韵定调 | 像午后第一口焦糖玛奇朵，焦糖裹着咖啡醇苦与坚果温厚，微凉收束。 |
| **Structure** 层次走线 | 前调焦糖甜润铺底 → 中调咖啡烘焙与可可交融 → 尾调坚果回甘，六层香韵递进分明，微凉在鼻腔喉口轻轻一点。 |
| **Vapor Feel** 雾气体感 | 烟雾细腻不刺激，焦糖甜香随呼气缓缓释放，坚果余韵在唇齿间停留约30秒。 |
| **Occasion** 随身场景 | 口袋里的午间玛奇朵，会议间隙的三口温厚停顿。 |

---

## Phase 2 色彩体系

| 变量 | HEX | 说明 |
|------|-----|------|
| 主色 · caramel | #B8956A | 焦糖琥珀莫兰迪金 |
| 深色 · caramel-deep | #6B4E3D | 咖啡可可深棕 |
| 浅色 · caramel-light | #D4B896 | 焦糖浅金 |
| 可可 · cocoa | #5C4033 | 深可可棕 |
| 奶色 · cream | #D8C8B8 | 奶白 |
| 底色 · oatmeal | #EAE4DA | 暖灰燕麦 |
| 油墨 · ink | #2A2218 | 深棕黑 |
| 网格 · grid | #8C7A66 | 深可可灰 |

**液体渐变**：`#D4B896 → #A08060 → #6B4E3D`（焦糖浅金 → 咖啡琥珀 → 坚果深棕）

**情绪关键词**：醇厚、温润、午间甜点

---

## Phase 5 模板绑定速查

将上述参数映射到 `templates/template-v3.html` 对应的占位符：

| 占位符 | 本示例填充值 |
|--------|------------|
| `{{COLOR_CSS}}` | `--caramel:#B8956A; --caramel-deep:#6B4E3D; --caramel-light:#D4B896; --cocoa:#5C4033; --cream:#D8C8B8;` |
| `{{MAIN_RGB}}` | `74,50,34` |
| `{{HERO_COLOR}}` | `rgba(40,32,24,0) 78%,rgba(234,228,218,.32) 100%` |
| `{{PRODUCT_NO}}` | `023` |
| `{{NAME_EN}}` | `Caramel &lt;span class=&quot;amp&quot;&gt;&amp;amp;&lt;/span&gt; Macchiato` |
| `{{NAME_CN}}` | `焦糖玛奇朵` |
| `{{CATEGORY}}` | `Card &amp;middot; Portable Eau de Vape` |
| `{{SPEC_NO}}` | `Spec. N°&amp;thinsp;VC&amp;middot;023 / jiaotangmaqiduo / 07.2026` |
| `{{SPECTRUM_GRADIENT}}` | `linear-gradient(90deg,#D4B896 0%,#A08060 50%,#6B4E3D 100%)` |
| `{{SPECTRUM_TICKS}}` | `&lt;span&gt;TOP &amp;middot; CARAMEL&lt;/span&gt; &lt;span&gt;MID &amp;middot; COFFEE&lt;/span&gt; &lt;span&gt;BASE &amp;middot; NUT&lt;/span&gt;` |
| `{{YEARS}}` | `XXVI` |

---

## 用户修改记录（Phase 0 交互追踪）

1. **Step 2**：「1-A, 2.咖啡提取物采用冷萃工艺，可可提取物采用分子蒸馏工艺；3.坚果15%，焦糖30%，咖啡25%，奶香20%，烘焙10%」
2. **Step 2 追问**：可可 → 「新增一路可可，奶香10%，可可10%，其他不变」
3. **Step 3**：雷达维度调整 → 「还原度4，凉度2，甜3，层次5，留香3，耐抽性4」
4. **Step 3**：跳过感官三件套+留香 → 「技术参数区在新版本HTML只留了extract一个参数」
5. **Step 4**：EXTRACT → 「C」（长版）
6. **Step 5**：感官四段确认 → Tonality 确认；Structure 修改「微凉在鼻腔喉口轻轻一点」；Vapor Feel 修改「烟雾细腻不刺激，停留约30秒」；Occasion 确认
7. **Step 6**：色谱条 → 三段全部确认
