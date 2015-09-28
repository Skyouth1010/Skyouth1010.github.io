---
layout: post

title: JAVA系列之－－并发编程（基础）
subtitle: "容器、队列、同步工具类、线程池"
cover_image: blog-cover.jpg

author:
  name: Skyouth
  weibo: skyouth
  bio: Runnable,cmbchina
  
tags: [技术]
---

# 基础
1. 线程有哪些状态？







	他不在整个get方法上使用锁，因为读取是从片段上读取，只需在片段中读取值的时候上锁就可以了。（key值没变，所以hash值也不会变，那key值在map中的位置也不会变，只要确保读取时的value不被修改即可）






	Fork/join模式，分而治之思想，将任务拆分成多个子任务进行。Work Stealing机制，在该线程池的每个线程中会维护一个队列来存放需要被执行的任务。当线程自身队列中的任务都执行完毕后，它会从别的线程中拿到未被执行的任务并帮助它执行。


	Executors. newCachedThreadPool corePoolSize=0, maximumPoolSize=max