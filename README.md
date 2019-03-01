# spider_newrank

新榜榜单内容抓取，数据仅用于研究学习。

### 使用说明

打开目录 `/path/to/spider_newrank`

运行

```
scrapy crawl newrank
```

爬取结果输出在 `/path/to/spider_newrank/newrank.csv`

默认爬取的是`财富经营`类目下 `阅读数` 前100名的公众号

| 名称       | 微信号 | 参考粉丝数 | 阅读数 | 是否是原创 | 新榜指数 | 微信id | 微信认证     |
| ---------- | ------ | ---------- | ------ | ---------- | -------- | ------ | ------------ |
| 吴晓波频道 | abc    | 888888     | 88888  | 1          | 999.99   | jsjhde | 反正很厉害的 |

### 难点

新榜公众号的榜单数据异步请求抓取相对容易，难点在于每次异步请求都会带上两个参数 `nonce` 和 `xyz`，通过查阅前端 `js` 代码以及参考亮哥的文档，找到了相关参数的计算方法。

### 参考资料

在寻找签名解决方案的时候找到了亮哥的 `Java` 版本，参考了亮哥的计算方法，在此感谢！
https://github.com/lhl4546/spider-newrank
