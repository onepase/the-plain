---
id: 134
title: Linux Üzerinde Mplayer İle Radyo Yayını Dinlemek
date: 2013-08-02T03:32:37+00:00
author: Pase
layout: post
guid: http://www.hakantorun.com.tr/?p=134
permalink: /linux-uzerinde-mplayer-ile-radyo-yayini-dinlemek/
categories:
  - Linux
tags:
  - dinle
  - how to
  - konsol
  - linux
  - mplayer
  - nasıl
  - radio
  - radyo
  - stream
---
Linux üzerinde radyo yayını dinlemek isteyebilirsiniz. Bunun için vlc,mplayer gibi medya oynatıcıları kullanabilirsiniz. Renkli renkli grafiklerden haz etmeyen biriyseniz mplayer sizin aradığınız şey. Mplayer ile konsol üzerinde radyo yayını dinlemek için;
  
Örnek olarak Özgür radyo stream için &#8220;canliyayin.ozgurradyo.com&#8221; adresi üzerinden 8100 portunu kullanıyor. 

`<br />
mplayer -nolirc http://canliyayin.ozgurradyo.com:8100<br />
` 

komutunu kullanmak yeterli.