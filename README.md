# 🕷️ Web Scraper 教程操作指南

本教程将带你从零开始学习如何使用浏览器开发者工具 + **Web Scraper 插件** 编写简单的爬虫。  
我们将以爬取 **豆瓣电影 Top 250** 为例，目标链接：[豆瓣电影 Top 250](https://movie.douban.com/top250?start=0&filter=)

---

## 1️⃣ 打开开发者工具

在浏览器中按下快捷键：

- **Windows / 部分笔记本**：`Fn + F12`  
- **Windows / 桌面键盘**：`F12`  
- **Mac (Chrome / Edge / Firefox)**：`⌘ + Option + I`

👉 或者：右键网页 → **检查 (Inspect)**  

在开发者工具的菜单中可以看到 **Web Scraper** 选项，点击进入。  

<img src="images/FindScraper.png" alt="打开 Web Scraper" width="500px">

---

## 2️⃣ 创建一个 Sitemap

在 Web Scraper 页面下，点击 **Create new sitemap**，会出现三个选项，选择 **Create Sitemap**。  

<img src="images/create1.png" alt="创建 Sitemap 第一步" width="500px">

接下来，填入你想要建立的爬取任务名称（例如 `douban`）和目标链接，然后点击 **Create Sitemap**。  

<img src="images/create2.png" alt="填写信息" width="500px">

点击左侧的 **Sitemaps**，找到你刚刚创建的 sitemap，点击进入管理页面：  
在 **Sitemap douban** 页面中，点击 **Edit metadata**，即可修改上述内容。  

<img src="images/scrape1.png" alt="进入 Sitemap 管理" width="500px">

---

## 3️⃣ 创建一个 Selector

完成 Sitemap 创建后，系统会跳转到新页面。点击 **Add new selector** 开始配置要爬取的元素：  

1. 在 **Id** 栏输入一个名字，例如 `Name`（用于电影名称）。  
2. **Type** 保持默认即可。  
3. 点击 **Selector → Select**，此时网页元素会高亮。  
4. 选中两个同类型的元素（如电影名），系统会自动识别其他同类元素。  
5. 点击 **Done selecting**，右侧 **Data preview** 出现字符即为成功。  
6. 在 **Multiple Type** 中选择表格输出形式，点击 **Data preview** 可预览效果。  
7. 点击 **Save selector** 保存。  

<img src="images/create3.png" alt="配置 Selector" width="500px">

在 **Sitemap douban** 页面中，点击 **Selectors** 可查看你创建的所有 selector。  
点击 **Edit** 可以随时修改。  

<img src="images/create4.png" alt="查看 Selector" width="500px">

---

## 4️⃣ 简单爬取

在 **Sitemap douban** 页面中，点击 **Scrape** 开始运行任务。  

- 默认参数（`2000`）保持不变  
- 点击 **Start Scraping**  

<img src="images/scrape2.png" alt="开始爬取" width="500px">

系统会自动爬取，完成后点击 **Refresh** 即可看到结果。  

<img src="images/scrape3.png" alt="爬取结果 1" width="500px">  
<img src="images/scrape4.png" alt="爬取结果 2" width="500px">  
<img src="images/scrape5.png" alt="爬取结果 3" width="500px">  

> 注：以上为三种 selector 的 `multiple type` 输出效果。  

最后，在 **Sitemap douban** 页面中点击 **Export data**，即可导出数据。  

---

## 5️⃣ 多个网页的信息--进阶请往后看

豆瓣链接格式说明：  

- `https://movie.douban.com/top250?start=0&filter=`  
  - 从第 1 部电影开始，展示 1–25  
- `https://movie.douban.com/top250?start=25&filter=`  
  - 从第 26 部电影开始，展示 26–50  

如果网页链接类似： `http://example.com/page/1`  `http://example.com/page/2`  
则可以写成： `http://example.com/page/[1-3]`  

对于豆瓣链接，可以改写为： ` https://movie.douban.com/top250?start=[0-225:25]&filter=`

这样 Web Scraper 就会抓取 **Top 250 的所有页面**。  

<img src="images/scrape6.png" alt="分页爬取结果" width="500px">

---

## 6️⃣ 导入与导出 Sitemap

- **导出 Sitemap**  
  在 **Sitemap douban** 页面点击 **Export Sitemap**，复制全部内容后即可分享。  

- **导入 Sitemap**  
  点击 **Create new sitemap** → **Import Sitemap**，粘贴内容后即可创建。  

<img src="images/import.png" alt="导入 Sitemap" width="500px">

---

## 7️⃣ 控制抓取数量

在一些网站（如 [Quotes to Scrape](https://quotes.toscrape.com/scroll)）中，页面会采用无限滚动的方式加载更多数据。  
如果不加限制，插件会一直抓取，直到页面加载完成或网络断开。  

我们可以通过 **CSS 伪类选择器** 限制抓取数量：  

- 假设 selector 为 `dl.article-card`，会默认抓取网页中所有的 `dl.article-card` 元素。  
- 在选择器后加上 `:nth-of-type(-n+100)`，表示只抓取前 **100 条** 数据。  
- 如果想抓取前 **200 条**，则写为 `:nth-of-type(-n+200)`，以此类推。  

<img src="images/num.png" alt="限制抓取数量" width="500px">

---

## 8️⃣ 设置爬取时间间隔

有时单条数据内容较长（例如某些长回复），默认的 **1s 间隔** 可能不足以完整抓取。  
此时可以将时间间隔适当调大，让爬虫在读取每条信息时有更多缓冲时间。  

<img src="images/ms.png" alt="设置时间间隔" width="500px">

---

## 9️⃣ Selector 类型与应用场景

爬虫的本质与我们手动读取信息类似：  
- 有些需要不断向下滚动才能出现新内容；  
- 有些需要点击跳转到新页面；  
- 有些是分页加载或“加载更多”；  
- 还有的以表格形式存储数据。  

Web Scraper 插件提供了多种 Selector 类型，使用方法类似，只是组合方式不同。  

<img src="images/type.png" alt="Selector 类型" width="500px">

### 常见 Selector 类型

1. **Element Selector**  
   - 用于多个网页的多条信息爬取。  

2. **Link Selector**  
   - 用于跳转超链接，抓取文本和链接地址。  

3. **Table Selector**  
   - 用于获取表格数据。  

4. **Element Scroll**  
   - 用于滚动加载页面。  

5. **Element Click**  
   - 用于点击操作，例如分页器、加载更多。  

---

## 示例：Element Selector 多字段爬取

如果我们想要同时爬取一部电影的 **排名、名称、评价** 等多条信息，可以使用 **Element Selector** 作为容器，然后在其下创建多个子 Selector 来获取不同类型的数据。  

### 步骤 1：创建 Element Selector  
新建一个 Selector，并将 **Type** 设置为 `Element`。  

<img src="images/mul_information1.png" alt="创建 Element Selector" width="500px">

### 步骤 2：在 Element 下创建子 Selector  
进入该 Element，在此页面下新建多个子 Selector，例如：  
- `rank`：排名  
- `name`：电影名称  
- `remark`：电影评价  

此时可以看到，所有子 Selector 的父选择器均为 `douban`。  

<img src="images/mul_information2.png" alt="创建子 Selector" width="500px">

### 步骤 3：运行爬取任务  
重新执行 **Scrape**，稍等片刻，即可获得完整的结果。  

<img src="images/mul_information3.png" alt="多字段爬取结果" width="500px">

---

### 📄 示例 Sitemap

```json
{
  "_id": "douban",
  "startUrl": ["https://movie.douban.com/top250?start=[0-225:25]&filter="],
  "selectors": [
    {
      "id": "douban",
      "type": "SelectorElement",
      "parentSelectors": ["_root"],
      "selector": ".grid_view li",
      "multiple": true,
      "elementLimit": 0,
      "scroll": false
    },
    {
      "id": "name",
      "type": "SelectorText",
      "parentSelectors": ["douban"],
      "selector": "span.title:nth-of-type(1)",
      "multiple": false,
      "regex": "",
      "multipleType": "singleColumn"
    },
    {
      "id": "rank",
      "type": "SelectorText",
      "parentSelectors": ["douban"],
      "selector": "em",
      "multiple": false,
      "regex": "",
      "multipleType": "singleColumn"
    },
    {
      "id": "remark",
      "type": "SelectorText",
      "parentSelectors": ["douban"],
      "selector": ".quote span",
      "multiple": false,
      "regex": "",
      "multipleType": "singleColumn"
    }
  ]
}

```

## 示例：Click Selector 分页爬取

对于分页或“加载更多”的场景，可以使用 **Element Click**：  

- 将 Selector 类型设置为 **`Element Click`**  
- 在 **Click selector** 中指定按钮的 CSS 选择器  
- 插件会模拟点击，加载新的数据，直到达到设定的次数或页面没有更多数据  

<img src="images/click.png" alt="Click Selector 示例" width="500px">  
<img src="images/paging1.png" alt="分页示例 1" width="500px">  
<img src="images/paging2.png" alt="分页示例 2" width="500px">

---

##  示例：Link Selector 获取链接

在很多场景下，我们不仅需要文本信息，还需要获取对应的 **超链接**。  
这时可以使用 **Link Selector**：  

- 将 Selector 类型设置为 **`Link`**  
- 插件会同时抓取元素的文字内容和其对应的链接 URL   

<img src="images/link1.png" alt="Link Selector 示例" width="500px">
