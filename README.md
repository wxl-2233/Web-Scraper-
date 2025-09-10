# 🕷️ Web Scraper 教程操作指南

本教程将带你从零开始学习如何使用浏览器开发者工具 + Python 编写简单的 Web Scraper。  
请按顺序操作，每一步都配有截图和代码示例。  

---

## 1️⃣ 打开开发者工具

在浏览器中按下：

- **Windows / 部分笔记本**：`Fn + F12`  
- **Windows / 桌面键盘**：`F12`  
- **Mac (Chrome / Edge / Firefox)**：`⌘ + Option + I`

👉 或者右键网页 → 选择 **检查 (Inspect)**。

在后面的选项中就可以看到Web Scraper。

📸 示例截图（请替换为你自己的图片）：
![打开开发者工具](images/open-devtools.png)

---

## 2️⃣ 定位网页元素

在开发者工具的 **Elements / 元素** 标签下，可以看到 HTML 结构。  
- 鼠标移动到代码上，页面对应元素会高亮。  
- 复制标签的 **CSS Selector / XPath**，后面写爬虫要用。

📸 示例截图：
![元素定位](images/select-element.png)

---

## 3️⃣ 新建 Python 文件

在项目文件夹中新建一个 `scraper.py`：

```bash
touch scraper.py
  
