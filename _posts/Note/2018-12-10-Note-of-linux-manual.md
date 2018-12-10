---
layout: post
title: Linux使用手册
category: 笔记
tags: Note
keywords: Note
---

## 1.配置代理服务器

###1.1 /etc/profile

​	/etc/profile文件的改变会涉及到系统的环境

​	**代理配置**

```bash
# 追加
http_proxy=http://192.1.2.2:808
export http_proxy
```

