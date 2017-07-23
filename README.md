# mySimpleDistributedCrawler
一个基于hadoop的简易朴素分布式爬虫。主要分为四个模块：
1.injector：种子url注入模块。
2.fetcher: 网页抓去模块。
3.parser：网页解析模块。
大致流程是injector注入种子url，fetcher抓去网页，将html存入hbase，parser解析之后获得新的url存入hbase，其中fetcher和parser均为mapreduce实现。
设置循环次数，依次循环爬取。
url过滤采用基于redis的布隆过滤，其中redis使用了一致性hash实现的简易分布式。
另外项目中也有基于单机的简易多线程爬虫实现。

need to do：
ip代理池，反爬虫。
完善网页解析，内容获取。
总体来说实现的很简易，仅作学习用。。。
