---
layout: post
title: SpringBoot学习笔记
category: 笔记
tags: Note
keywords: springboot 笔记
---

## 1.基础

### 1.1 数据源概念

数据源，即数据库连接池，如果用户每次请求都建立conn，耗费资源（时间和内存）

数据库连接池负责管理conn，保持一定数量的conn重复

### 1.2 编写数据库连接池

​	实现java.sql.DataSource接口

- 构造函数批量create conn，LinkedList.add

- 实现func:getConnection, get conn from LinkedList

- Connection.close(), 回收conn到LinkedList，不关闭conn

  核心代码

  ----

  使用动态代理

  ```java
  proxyConn = (Connection) Proxy.newProxyInstance(this.getClass()
              .getClassLoader(), conn.getClass().getInterfaces(),
              new InvocationHandler() {
          //此处为内部类，当close方法被调用时将conn还回池中,其它方法直接执行
              public Object invoke(Object proxy, Method method,
                        Object[] args) throws Throwable {
                  if (method.getName().equals("close")) {
                      pool.addLast(conn);
                      return null;
              }
              return method.invoke(conn, args);
          }
      });
  ```

  ### 1.3 开源DataSource

  Weblogic，Tomcat提供DataSource实现，开发起来方便，导入相关jar包，不需要再实现
