`https://github.com/phunterlau/data_science_for_whitehat`

[TOC]
# 排列与组合

## 一个问题

工作三年的白帽子安全工程师小王观测到一种 cc 攻击，它利用伪造的字符串进行恶意查询消耗资源。小王所负责的业务的正常查询字符串模式一般为 12 到 16 个英文小写字符和数字组合，其正则表达为 `[a-z0-9]{12,16}` ，而从情报分析观测到的攻击字符串为 2 到 32 个英文大小写和数字随机混合，其正则表达为 `[A-Za-z0-9]{2,32}` 。小王的问题是，如何设计一个正则表达式，在数据流中用很短时间通过查询字符的模式侦测 cc 攻击 IP ？提醒注意，有一些合法但是错误设置的 IP 也有可能偶然出现大写字母的查询，但是不多，同时因为攻击的脚本随机性，攻击查询**并不一定**会出现大写字母。

这一节我们会简单复习一下高中说到的排列和组合概念，并介绍应用排列组合模型到实际数据问题里的方法。