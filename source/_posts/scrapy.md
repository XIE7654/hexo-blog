---
title: scrapy
date: 2020-04-26 15:35:14
tags:
---

### 创建项目
```bash
scrapy startproject scrapy_first
```

### 生成爬虫模版文件
scrapy genspider -t 母版名称 爬虫文件名称 要爬取的域名
```bash
scrapy genspider -t basic filter baidu.com
```
可以不加-t basic, 默认使用basic模版

### 测试一个爬虫文件是否合规 scrapy check 爬虫名称
```bash
scrapy check filter
```

### 执行爬虫文件 scrapy crawl 爬虫名称
```bash
scrapy crawl filter
scrapy crawl filter --nolog  # 不显示日志
```
