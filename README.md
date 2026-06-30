# 全球黄金实时看板 Global Gold Dashboard

实时监控全球黄金市场的交互式看板，数据来自 gold-api.com + Yahoo Finance。

## 功能特性

- **COMEX 黄金期货实时行情**：最新价、涨跌额、涨跌幅、今开/最高/最低
- **多市场金价对比**：伦敦金、上海金、COMEX 以及折算各主要货币价格
- **贵金属横向对比**：黄金、白银、铂金、钯金四品种卡片
- **实时走势图**：基于真实 1 分钟 K 线的动态价格轨迹
- **多周期趋势**：1分钟 / 5分钟 / 15分钟 / 30分钟 / 1小时涨跌数据
- **30 日历史趋势**：Yahoo Finance 真实日线数据
- **金银比仪表盘**：实时金银比价 + 历史均值参考
- **关联指标**：美元指数 DXY、USD/CNY 汇率
- **全球新闻**：每 1 分钟自动从 Google News 抓取最新黄金资讯（英文自动转中文展示）
- **暗色主题**：红涨绿跌，中国市场惯例配色

## 技术实现

- 纯静态页面，无需后端
- ECharts 图表引擎
- gold-api.com 实时金价轮询（每 10 秒）
- Yahoo Finance 历史 K 线数据（yfinance）
- rss2json.com 新闻 RSS 代理
- 支持 GitHub Pages 一键部署

## 本地运行

```bash
# 任意静态文件服务器即可
python -m http.server 8080
# 或
npx serve .
```

## 数据来源

| 数据 | 来源 | 更新频率 |
|------|------|----------|
| XAU/USD 现货金价 | gold-api.com | 每 10 秒 |
| COMEX 期货历史 K 线 | Yahoo Finance | 初始加载 |
| 白银/铂金/钯金价格 | Yahoo Finance | 初始加载 |
| DXY / USDCNY | Yahoo Finance | 初始加载 |
| 全球黄金新闻 | Google News RSS | 每 1 分钟 |
