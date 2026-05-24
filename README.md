# 💎 黄金多周期量化决策面板 (Gold Multi-Timeframe Quant Panel)

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Active-emerald?style=flat-square&logo=github)](https://simom1.github.io/Gold-Quant-Panel/)
[![Language](https://img.shields.io/badge/渲染-HTML5%20%2F%20SVG-amber?style=flat-square)](https://simom1.github.io/Gold-Quant-Panel/)
[![Data-Source](https://img.shields.io/badge/数据源-XAUUSD%20现货黄金-blue?style=flat-square)](https://simom1.github.io/Gold-Quant-Panel/)

这是一个免后端依赖、全矢量动态渲染的高阶黄金（XAUUSD）量化投资决策交互面板。

本仓库仅对外开源本量化研究的**交互式成果报告（`index.html` 及数据包 `report_assets/`）**。面板支持 7 大核心周期（**1m、5m、15m、30m、1h、4h、D1**）的实时无缝联切，深度呈现黄金市场的波动规律与盈亏概率。

---

## 🔮 核心研究板块与数理功能

### 1. 🔮 DTW 动态时间规整相似沙盘
传统的欧氏距离计算对时间轴的移位和拉伸极其敏感。本引擎引入 **DTW (Dynamic Time Warping) 算法** 进行非线性的时间对齐，将当前最新的 100 根实盘 K 线与历史 3.2 年（百万级高频数据）中 Top-6 最相似的走势完美重叠对齐，并拉出其真实的历史后续前瞻路径，为交易员研判“历史重演”的概率分布提供直观参考。

### 2. 📐 经典技术图形扫描与风控精算
基于 Pivot 顶底极值检测与动态 ATR-ZigZag 骨架，系统自动扫描 8 大经典技术形态（双底 W、双顶 M、收敛/发散三角、头肩顶底、通道等），并根据历史全样本精算出以下实战指标：
* **历史胜率 (Win Rate)**：形态确认突破点后，前瞻 20 根 K 线持仓期结束时符合预期方向收盘的样本比例。
* **数学期望值 (EV)**：历史样本在持仓期内的平均回报率，正值代表统计学优势。
* **半凯利杠杆 (Half-Kelly)**：动态概率盈亏比精算开仓推荐杠杆，防范回撤与账户侵蚀，零/负期望形态自动归零保护。

### 3. 📊 100% 矢量无图轻量化设计 (Pure SVG)
主面板摒弃了所有 Matplotlib 渲染的静态 PNG 图片，完全由浏览器通过 HTML5 + SVG 矢量引擎在本地实时绘制。
* **极速加载**：文件大小大幅精简，完美杜绝破损图片链接。
* **零后端依赖**：无需任何数据库或 API，可直接在 GitHub Pages 免费部署托管，或在本地双击 standalone 网页文件流畅运行。

---

## 🚀 在线预览与使用方法

### 🌐 网页在线预览
点击直接访问在线交互网站：**[simom1.github.io/Gold-Quant-Panel](https://simom1.github.io/Gold-Quant-Panel/)**

### 💻 本地打开运行
如果您已将本仓库克隆至本地，只需双击 **`index.html`** 文件，即可在任何浏览器（包括手机浏览器）中流畅打开：
```bash
# macOS 终端命令行打开
open index.html
```

---

## 🔒 算法保密与私有引擎声明
本仓库为**只读量化研究报告成果展示仓**。

底层的量化分析引擎——包括百万级数据库重采样链、并行加速 DTW 滑窗检索算法、无监督 K-Means 状态聚类器、以及 ATR-ZigZag 技术图形识别库等核心 Python 代码——属于**非公开专有商业机密（Proprietary & Closed-source）**，不在此开源仓库中提供。
