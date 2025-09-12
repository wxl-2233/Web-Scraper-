# 🕷️ Web Scraper 教程操作指南

本仓库带你从零开始学习如何使用 **Web Scraper 插件** 爬取网页数据。  
教程分为 **基础 → 进阶 → 深入 → 特例** 四个阶段，循序渐进，帮助你从零快速上手，再逐步掌握复杂场景。

---

## 📚 学习路径

1. [基础篇 · Basic](docs/basic.md)  
   - 安装与打开 Web Scraper  
   - 创建 Sitemap  
   - 添加 Selector  
   - 简单数据导出  
   👉 适合第一次接触爬虫的用户

2. [进阶篇 · Advanced](docs/advanced.md)  
   - 多页面爬取（分页、URL 范围）  
   - 控制抓取数量  
   - 设置爬取时间间隔  
   - 导入与导出 Sitemap  
   👉 适合完成入门后想采集更大规模数据的用户

3. [Selector 篇 · Selectors](docs/selectors.md)  
   - 各类 Selector 的使用方法（Element / Link / Table / Click 等）  
   - 正则表达式速查表 & 重复匹配  
   - CSS 选择器语法  
   👉 适合作为 **工具手册** 随查随用

4. [特例篇 · Special Cases](docs/special_cases.md)  
   - 刷新分页（递归结构树）  
   - 无限滚动页面  
   - 点击加载更多  
   👉 适合解决实际采集中遇到的“疑难杂症”

---

## 📂 示例资源

- [豆瓣 Top 250 Sitemap](examples/douban_sitemap.json)  
- [Click Selector 示例](examples/click_demo.json)  
- [截图集](images/)

---

## 💡 学习建议

- **新手**：从 [基础篇](docs/basic.md) 开始，先成功跑通第一个爬虫  
- **进阶**：完成 [进阶篇](docs/advanced.md)，掌握多页面与大规模数据采集  
- **查阅**：遇到具体问题时，直接翻 [Selector 篇](docs/selectors.md)  
- **实战**：遇到特殊网站结构，再看 [特例篇](docs/special_cases.md)  

---

## 🤝 贡献

如果你有新的示例 sitemap 或技巧，欢迎提交 PR，一起完善这份学习指南！
