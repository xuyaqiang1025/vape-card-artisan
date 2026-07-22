# Vape Card Artisan / 雾卡匠

> v3.0.0 · Cormorant Garamond 衬线统一制 · 深色莫兰迪静物 · standalone HTML

专注便携卡片式雾化产品的口味视觉全案设计师——把抽象的雾化风味翻译成可被看见、可被触摸、可被期待的视觉语言，交付对标轻奢卡片香水极简美学的产品卡。

## 类型

Agent 型（单个 AI 专家）

## v3.0 核心特性

- **Cormorant Garamond 衬线统一制**：全卡统一 Cormorant Garamond + Noto Serif SC，靠 weight + italic + size + letter-spacing 分层，italic 是高级感灵魂（Le Labo / Diptyque 手法），大字间距替代 monospace 档案感
- **深色莫兰迪静物**：深色底（#2A2218 深琥珀）+ 丰盛实物道具聚簇（开心果/黑巧/可可粉等多颗组合），moody artisan food photograph 风格
- **standalone HTML 默认**：图片 base64 内嵌（data:image/png;base64），字体 CDN 为唯一外链，解决分享破图问题
- **技术参数区可视化**：grid 3 列 + 6 种迷你可视化（双 pill / 柱状图 / 时间轴 / 点阵 / 圆 / 堆叠条），色块取自参数语义色
- **国际化排版**：英文主导（主标题 italic 48px），中文降为副标（24px ink-soft 色），感官四段标题全英 + 中文释义副标
- **风味解构与感官翻译**：基于 GC-MS 风味物质拆解逻辑，五维结构（前调/中调/后调 + 凉感线 + 留香线）
- **Phase 0 参数确认机制**：模型提案 + 用户确认的交互式参数校准
- **附录风味色彩映射参考表**：涵盖基础果味/烟草/凉感/茶香 + Boutique Mixology 高定复合风味

## 交付物清单

每次完整执行 Phase 0-5 后，默认交付：

1. **standalone HTML 产品卡**（.html 单文件）
   - 图片 base64 内嵌，字体 CDN 为唯一外链
   - 可直接双击打开预览，可独立部署
   - 含 Swiss Design 12 栏栅格 + 技术参数区 + 雷达图
2. **AI 静物渲染图**（.png）
   - 深色莫兰迪底 + 丰盛实物道具
   - 1024×1024，独立交付

## 字体系统说明

| 字体 | 用途 | 来源 |
|------|------|------|
| Cormorant Garamond | 英文标题/段标题/术语标签/数字（italic 为主） | Google Fonts CDN |
| Noto Serif SC | 中文正文/中文副标（normal, weight 300/400） | Google Fonts CDN |

CDN 引入：
```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,400;1,500;1,600&family=Noto+Serif+SC:wght@300;400;600&display=swap" rel="stylesheet">
```

## 使用示例

- 帮我设计一款「青提冰」口味卡：配色、材质、感官文案、HTML 产品卡一体化输出
- 设计「冷萃烟草」便携雾化卡片：深色莫兰迪静物 + 丰盛实物道具 + Cormorant 衬线排版 + standalone HTML 输出
- 对标轻奢卡片香水美学，做「开心果抹茶拿铁」口味介绍页 + 线下陈列卡组合

## 头像

头像已自动生成在 `avatars/` 目录下。如需替换为自定义头像，要求：
- 格式：PNG（推荐）或 JPG
- 尺寸：512×512 px
- 大小：单张不超过 500KB

## 安装

将专家包目录放到专家目录下：

```
C:\Users\138939\.workbuddy\plugins\marketplaces\my-experts\plugins/vape-card-artisan/
```

然后运行注册命令使其可见：

```bash
python3 scripts/register_expert.py <expert-dir>
```

## 打包分享

```bash
zip -r vape-card-artisan.zip vape-card-artisan/
```

## 变更日志

### v3.0.0（当前）
- **字体统一制**：替代 serif/sans/mono 三档制，全卡 Cormorant Garamond + Noto Serif SC，italic + 大字间距分层
- **深色莫兰迪底**：渲染图与氛围顶区默认 #2A2218 深琥珀莫兰迪底（仍守低饱和原则）
- **丰盛实物道具**：从"最多一件"升级为"丰盛聚簇"（完整 + 裂开 + 碎片 + 粉末多颗组合）
- **standalone HTML 默认**：图片 base64 内嵌，解决分享破图
- **技术参数区可视化重构**：grid 3 列 + 6 种迷你可视化，MAIN ACCORDS 拆出独立区块
- **国际化排版**：英文主导，中文降为副标，感官四段标题全英
- **雷达图升级**：网格 #8C7A66 + 数据点白心描边 + 字体加大 + SVG 280px+
- **排版细节**：&thinsp; 细空格 / &middot; 中点 / 罗马数字年份装饰位

### v2.0.0
- 新增 Phase 0 参数确认机制（模型提案 + 用户确认）
- 技术参数区引入 MAIN ACCORDS 横向柱状图
- 雷达图维度数动态化（3-7 维）
- Boutique Mixology 高定复合风味色彩表

### v1.0.0
- 初始版本
- 五维风味解构 + 风味色彩情绪匹配
- 静物渲染 + 四段式感官文案
- HTML 产品卡（Swiss Design 12 栏 + serif/sans/mono 三档字体）
