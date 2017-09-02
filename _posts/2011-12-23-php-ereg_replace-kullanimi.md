---
id: 27
title: 'PHP &#8220;ereg_replace&#8221; Kullanımı'
date: 2011-12-23T10:33:55+00:00
author: Pase
layout: post
guid: http://www.pasein.com/?p=27
permalink: /php-ereg_replace-kullanimi/
categories:
  - Genel
tags:
  - ereg_replace
  - ereg_replace fonksiyonu kullanımı
  - php ereg_replace fonksiyonu
---
Bazen PHP&#8217;de bir takım manipülasyonlar yapmanız gerekebilir. Bu anlarda kendi fonksiyonlarımızın da iş gördüğü gibi PHP fonksiyonları da imdadınıza koşuyor.

Şimdi bu fonksiyonlardan sadece birisi olan &#8220;ereg\_replace&#8221; fonksiyonu hakkında biraz bilgi verelim. ereg\_replace fonksiyonu stringler üzerinde manipülasyon yapmanıza olanak sağlıyor. Örneğin;

<pre>Bugün hava çok sisli
</pre>

cümlesindeki &#8220;sisli&#8221; kelimesini &#8220;yağmurlu&#8221; ile değiştirmek için;

<pre>&lt;?php
$cumle="Bugün hava çok sisli";
$cumle=ereg_replace("sisli","yağmurlu",$cumle);
?&gt;
</pre>

gibi bir yöntem izlememiz gerekiyor. 

ereg_replace fonksiyonunun en basit haliyle kullanımı bu şekilde. İlerleyen safhalarda düzenli ifadelerle kullanılması ile birlikte, iş yükünü çok hafifleteceğini hatırlatayım. </p></p>