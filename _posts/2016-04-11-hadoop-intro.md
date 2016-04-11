---
layout: post
title:  初识hadoop
date:   2016-04-11 17:15:00
category: "Hadoop"
---
**谷歌三大论文：GFS、 MapReduce、 BigTable  (2003、2004、2006)**

- HDFS实现数据的存储  
- MapReduce实现数据的分析和处理（将硬盘的读写问题转换为对一个数据集(key-value)的计算）

**MapReduce对比传统技术（关系数据库、网络计算）：**  
1. 大量硬盘寻址的时间  `>>>` 流数据读取模式，读取全部数据（取决于硬盘传输速率）  
2. 基于消息传递接口的数据处理时间（网络传输数据）`>>>` 数据尽量在本地，快速访问处理（数据本地化）  
对于`2`的补充：  
大规模分布式计算环境下，协调各进程的执行（是否挂了，挂了能继续完成整个计算）。MapReduce更有优势，
能够检测并重新执行失败的任务，无共享框架（任务彼此独立）。传统的基于MPI（消息传递接口）必须显式管理检查点和恢复机制。

## Hadoop发行版本： ##
`1.x`版本(0.22之前）     `0.22`发行版本     `2.x`版本(0.23及之后, *YARN、HDFS联邦管理与高可用*)

兼容性：  
主发行版本允许破坏API兼容性(1.x.y 到 2.0.0)  
次重点发行版本和单点发行版本不应该破坏兼容（`@InterfaceStability.Stable、@InterfaceStability.Evolving`）

## MapReduce简介： ##