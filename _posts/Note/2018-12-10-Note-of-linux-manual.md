---
layout: post
title: Linux使用手册
category: 笔记
tags: Note
keywords: Note
---

## 1.配置代理服务器

###1.1 centos代理设置

​	/etc/profile文件的改变会涉及到系统的环境

​	**代理配置**

```bash
# 追加
http_proxy=http://192.1.2.2:808
export http_proxy
```

### 1.2 Centos 7 yum代理设置

​	在/etc/yum.conf后面添加一下内容

```bash
proxy=http://代理服务器IP：端口号
```

​	如需要验证

```bash
proxy=http://IP:Port
proxy_username=user
proxy_password=password
```

