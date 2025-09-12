# Selector 篇

## 1️⃣ Selector 类型与应用场景（概览）

爬虫的操作本质上是模仿人工浏览，常见场景包括滚动加载、点击加载、翻页与跳转等。Web Scraper 提供多种 Selector 来应对不同场景：

<img src="../images/type.png" alt="Selector 类型" width="500px">

### 常见 Selector（简要说明）
- **Element**：作为容器选中每一条记录（适合多字段抓取）。  
- **Link**：用于抓取链接文本及目标 URL（适合目录页跳转）。  
- **Table**：直接抓取表格数据（结构化表格优先使用）。  
- **Scroll**：用于处理无限滚动页面。  
- **Click**：模拟点击（例如“加载更多”按钮），注意仅在点击不触发整页刷新时使用。  
- **Attribute**：抓取元素属性（例如 `<img src>`、`alt`、`title` 等）。  
- **Regex**：在 Selector 中使用正则抽取文本的一部分（注意 Web Scraper 的正则限制，详见正则资源篇）。

---

## 2️⃣ 属性抓取示例（`Attribute`）

示例 HTML：
```html
<img src="images/mul_information1.png" alt="创建 Element Selector" width="500px">
