# 🕸️ Web Scraper 使用指南

本仓库使用 Web Scraper 插件作为示例工具，按章节将教程拆成若干可独立阅读的文档，便于学习与维护。
所有正文位于 `docs/`，截图统一放在仓库根目录的 `images/` 文件夹中。

## 文档一览

- [基础篇](docs/basic.md)  
  介绍：从打开开发者工具到创建 Sitemap、添加 Selector、运行简单爬取与数据导出（包含对应截图与操作提示）。
  主要包含：
  - 打开开发者工具
  - 创建 Sitemap
  - 创建 Selector（选择元素、Multiple Type 预览）
  - 运行简单爬取 + 导出数据
  - 导入 / 导出 Sitemap

- [进阶篇](docs/advanced.md)  
  介绍：处理多页面的抓取、限制抓取条数、设置抓取间隔等提升稳定性与效率的操作。
  主要包含：
  - 多页面 / 范围 URL 写法
  - 控制抓取数量（`:nth-of-type` 限制）
  - 设置爬取时间间隔

- [Selector](docs/selector.md)  
  介绍：逐一说明 Web Scraper 中常用的 Selector 类型与适用场景，并给出属性抓取与正则应用场景示例。

- [正则资源篇](docs/regex.md)  
  介绍：常用正则速查表、重复匹配说明，以及 Web Scraper 内置正则的局限性提示（便于查阅）。

- [应用与特例篇](docs/examples.md)  
  介绍：组合示例（Element + 子 Selector）、Click/Link 分页示例、刷新分页的递归结构、CSS 选择器细节与结构树示意等实战内容。
