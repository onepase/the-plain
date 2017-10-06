---
title: 'Python Scrapy Kurulumu Ve Kullanımı'
date: 2017-10-07T00:15:12+00:00
author: Hakan
layout: post
permalink: /python-scrapy-kurulumu-ve-kullanimi/
categories: Genel
tags: python scrapy kurulum kullanım
---

Scrapy Python ile yazılmış, html ve xml gibi yapısal içeriklerden verilerin ayıklanmasını sağlayan açık kaynak bir frameworktür. Özellikle web siteleri üzerinde yeterince hızlı bir şekilde scraping ve crawling yapabilmektedir.

pip kurulu sistemler üzerinde

`pip install scrapy`

komutu ile kurulumu yapılabilir. Kurulum gerçekleştirildikten sonra terminal üzerinden proje dizininde,

`scrapy startproject tutorial`

komutuyla yeni bir scrapy projesi oluşturulur. Bir scrapy projesi oluşturulduğunda şu şekilde bir dosya/dizin yapısı oluşmuş olacaktır.

```bash
tutorial/
    scrapy.cfg            # deploy configuration file

    tutorial/             # project's Python module, you'll import your code from here
        __init__.py

        items.py          # project items definition file

        pipelines.py      # project pipelines file

        settings.py       # project settings file

        spiders/          # a directory where you'll later put your spiders
            __init__.py
```

Örnek bir spider 

```bash
import scrapy

class QuotesSpider(scrapy.Spider):
    name = "quotes"
    start_urls = [
        'http://quotes.toscrape.com/page/1/',
        'http://quotes.toscrape.com/page/2/',
    ]

    def parse(self, response):
        for quote in response.css('div.quote'):
            yield {
                'text': quote.css('span.text::text').extract_first(),
                'author': quote.css('small.author::text').extract_first(),
                'tags': quote.css('div.tags a.tag::text').extract(),
            }
```

Scrapy örümcekleri ile bir veya birden fazla adres üzerinde tarama ve veri çıkarma işlemi yapılabilmektedir. Scrapy seçicileri ile istenen alanlar seçilip filtrelenebilmektedir. Scrapy seçicilerinde xpath scrapy tarafından desteklenmektedir.

Crawl etmek için 

`scrapy crawl quotes`

Elde edilen çıktıyı json formatında bir dosyaya yazmak için

`scrapy crawl quotes -o qutoes.json`

komutu kullanılabilir.
