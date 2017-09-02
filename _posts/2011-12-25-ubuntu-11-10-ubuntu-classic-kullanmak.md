---
id: 32
title: 'Ubuntu 11.10 &#8211; Ubuntu Classic Kullanmak'
date: 2011-12-25T21:44:53+00:00
author: Pase
layout: post
guid: http://www.pasein.com/?p=32
permalink: /ubuntu-11-10-ubuntu-classic-kullanmak/
categories:
  - Genel
tags:
  - linux
  - ubuntu
  - ubuntu-classic
---
Ubuntu 11.10 dağıtımı ile birlikte gelen unity klasik Gnome Ubuntu kullanıcılarını çileden çıkarmaya devam ediyor. Klasik Gnome görünümü için Ubuntu 11.04 Natty&#8217;de Login kısmında Ubuntu Classic seçilerek sorun çözülüyordu ancak Ubuntu 11.10 da bu durum ortadan kalkmış durumda. Ancak bunu kısmen çözmek mümkün.

Bunun için ubuntu-shell ve ubuntu-session-fallback paketlerinin kurulması gerek. Bunun için

<pre></p>

<p>
  apt-get install ubuntu-shell
</p>

<p>
  apt-get install ubuntu-session-fallback
</p>

<p>
  </pre>
  
</p>


<p>
  ile paketleri kuruyoruz ve ardından tekrar login oluyoruz. Login olurken sağdaki seçenekler ikonunda Ubuntu Classic seçiyoruz. Bu kısmen sorunu çözüyor. Ancak benim gibi root olarak sisteminizi kullanıyorsanız sıkıntı çıkarıyor. Root olarak login olursanız Ubuntu Classic kullanamıyorsunuz ancak diğer kullanıcılarda bir problem yok.
</p>


<p>
  Şahsen tekrardan Ubuntu 11.04&#8242;e ya da Xubuntu&#8217;ya geçmeyi düşünüyorum. 
</p>