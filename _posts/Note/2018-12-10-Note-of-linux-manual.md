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

## 2 Firewall 防火墙

### 2.1 简单命令

​	查看防火墙当前状态

```bash
service firewalld status
```

​	防火墙开启对应端口

```bash
# 以Mongodb 端口27017为例
iptables -A INPUT -p tcp -m state --state NEW -m tcp --dport 27017 -j ACCEPT
```

## 3 DNS配置

### 3.1 使用命令行工具nmcli

```bash
#显示当前网络连接
nmcli connection show
#修改当前网络对应的DNS服务器
nmcli con mod eth0 ipv4.dns "8.8.8.8"
#使之生效
nmcli con up eth0
```

### 3.2 修改/etc/resolv.conf

```bash
#手工修改
nameserver 8.8.8.8
```

