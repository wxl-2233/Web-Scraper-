# 🕷️ Web Scraper 教程操作指南

本教程将带你从零开始学习如何使用浏览器开发者工具 + **Web Scraper 插件** 编写简单的爬虫。  
我们将以爬取 **豆瓣电影 Top 250** 为例，目标链接：  
👉 https://movie.douban.com/top250?start=0&filter=

---

## 1️⃣ 打开开发者工具

在浏览器中按下快捷键：

- **Windows / 部分笔记本**：`Fn + F12`  
- **Windows / 桌面键盘**：`F12`  
- **Mac (Chrome / Edge / Firefox)**：`⌘ + Option + I`

👉 或者：右键网页 → **检查 (Inspect)**。  

在开发者工具的菜单中可以看到 **Web Scraper** 选项，点击进入。  

<img src="images/FindScraper.png" alt="打开 Web Scraper" width="500px">

---

## 2️⃣ 创建一个 Sitemap

在 Web Scraper 页面下，点击 **Create new sitemap**，会出现三个选项，选择 **Create Sitemap**。  

<img src="images/create1.png" alt="创建 Sitemap 第一步" width="500px">

接下来，填入你想要建立的爬取任务名称（例如 `douban250`）和目标链接，然后点击 **Create Sitemap**。  

<img src="images/create2.png" alt="填写信息" width="500px">

创建完成后，系统会自动跳转到一个新页面。点击 **Add new selector** 开始配置要爬取的元素：  

1. 在 **Id** 栏输入一个名字，例如要爬取电影名称可以写 `Name`  
2. **Type** 可以先不用修改  
3. 点击 **Selector → Select**，此时鼠标移动到网页左边会出现高亮方块  
4. 选中两个同类型的方块（如电影名），系统会自动识别其他同类元素  
5. 选择完成后点击 **Done selecting**  
6. 在 **Multiple Type** 中选择输出表格形式（后续也可修改）  
7. 点击 **Save selector** 保存  

<img src="images/create3.png" alt="配置 Selector" width="500px">

---

## 3️⃣ 简单爬取

点击左侧的 **Sitemaps**，找到你刚刚创建的 sitemap，点击进入管理页面。  

<img src="images/scrape1.png" alt="进入 Sitemap 管理" width="500px">

在 **Sitemap douban** 页面中，点击 **Scrape** 即可开始运行爬取任务。  
一般默认的两个数值都是 `2000`，可以保持不变，直接点击 **Start Scraping**。  

<img src="images/scrape2.png" alt="开始爬取" width="500px">

---

## ✅ 小结

到这里，你已经完成了最简单的 Web Scraper 配置：  
- 创建 Sitemap  
- 配置要爬取的元素（Selector）  
- 启动爬取并获取结果  

后续可以尝试：  
- 添加更多 Selector（如评分、导演）  
- 爬取多页数据  
- 将数据导出为 CSV / Excel  

---

## 📌 提示：如何让图片更美观？

你的截图大小不一致，可以在 Markdown 里用 `<img>` 标签统一设置宽度，例如：  

```markdown
<img src="images/xxx.png" alt="描述文字" width="500px">
