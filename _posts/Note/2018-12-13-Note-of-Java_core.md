---
layout: post
title: Java核心学习
category: 笔记
tags: Note
keywords: Java
---

## 1. 基础

### 1.1 copy

- clone

- 深度clone

###1.2 inter
	Java内部类是Java语言中很重要的一个概念，但是在实践中很少用到
	应用场景
-	1. 当某个类除了它的外部类，不再被其他的类使用时
    -2. 解决一些非面向对象的语句块
    -3. 一些多算法场合
    -4. 适当使用内部类，使得代码更加灵活和富有扩展性
###1.3 String
	1.“值传递”，即方法操作的是参数变量（也就是原型变量的一个值的拷贝）改变的也只是原型变量的一个拷贝而已，而非变量本身
```java
public class StringT {
    public static void main(String[] args) {
        String str = "123";
        change(str);
        System.out.println(str);// print "123"
    }

    public static void change(String str) {
        str = "456";
    }
}
```
	2. 对象含String做方法的参数传递
```java
/**
 * @author BYSocket
 * @since 2016-01-06 20:07:00
 * 对象含有String作为方法参数传递
 */
public class StringT2 {

    public static void main(String[] args) {
        StringObject sb = new StringObject();
        sb.setName("123");
        change(sb);
        System.out.println(sb.getName());//print "123"
    }

    public static void change(StringObject sb) {
        sb = new StringObject();
        sb.setName("456");
    }

}
class StringObject {
    String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```
##2. Collection
###2.1 hash
###2.2 list
###2.3 map
###2.4 queue
###2.5 set
###2.6 util