---
layout: post

title: JAVA系列之－－JDK源码
subtitle: "JDK源码解读"
cover_image: blog-cover.jpg

author:
  name: Skyouth
  weibo: skyouth
  bio: Runnable,cmbchina
  
tags: [技术]
---

# Jdk5\jdk6\jdk7\jdk8的区别
JDK5开始新增了泛型、自动装箱\拆箱、for-each、变长参数等；





# hashmap\hashset\hashtable
Hashmap的底层是一个Entry数组，每个entry带有对下一个元素的引用，即链表。所以整体的看，他是一个数组和链表的结合体（<a href='http://zha-zi.iteye.com/blog/1124484'>链表散列</a>，散列即hash）。如图：
<img src='/images/hashmap.png'>

初始化时，Hashmap的容量肯定为2的n次方，即entry[2^n]，默认为entry[16]。当新增一个键值对时，先计算键值的的散列值，使其平均分布在entry数组上，不同的key值，散列值可能相同，这时就放在该数组位置的链表头上，链表头指向原链表头。如果hashmap的实际容量超过了数组长度的影响因子倍（loadFactor，默认0.75）（或者是初始容量，jdk7），则entry将进行扩容，同时将原来列表进行重新计算散列值分布于新的entry中。
    <pre><code>h = key.hashCode();
</code></pre>



