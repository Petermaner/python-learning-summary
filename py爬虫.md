爬取豆瓣三部电影名字+年份    
源代码：   
```py
from requests_html import HTMLSession
session = HTMLSession()

links = ['https://movie.douban.com/subject/1292052/', 'https://movie.douban.com/subject/1962665/', 'https://movie.douban.com/subject/26752088/']
for link in links:
    r = session.get(link)
    title = r.html.find('#content > h1 > span:nth-child(1)', first=True)
    year = r.html.find('#content > h1 > span.year', first=True)
    print(title.text, year.text)
```
运行结果:   
```
肖申克的救赎 The Shawshank Redemption (1994)
银河铁道之夜 銀河鉄道の夜 (1985)
我不是药神 (2018)
```
