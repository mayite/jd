# jd
京东商品详情+评论爬虫（Scrapy、Redis）

基于Python+scrapy+redis+mongodb的分布式爬虫实现框架

scrapy runspider jdredisurl.py 主要功能是抓取种子url，保存到redis

scrapy runspider jdmongodb.py 主要是从redis里面读url，解析数据保存到mongodb（拓展到其他机器,修改REDIS_HOST = "主机ip"，都是从redis里面读url,MONGODB_HOST = "存储服务器ip"）。

middlewares.ProxyMiddleware 使用阿布云代理服务器轮换请求IP。

每页60条数据，源码仅有30条，解决下拉时刷新的剩余30条数据抓取。

使用Spiderkeeper监控爬虫管理，定期执行，分析日志报告，异常维护。

                                                    京东商品信息mongodb图示
![京东商品信息](https://github.com/renqian520/jd/blob/master/%E4%BA%AC%E4%B8%9C%E5%95%86%E5%93%81%E4%BF%A1%E6%81%AF.jpg)

                                                    京东商品评论mongodb图示
![京东商品评论](https://github.com/renqian520/jd/blob/master/%E4%BA%AC%E4%B8%9C%E5%95%86%E5%93%81%E8%AF%84%E8%AE%BA.jpg)
