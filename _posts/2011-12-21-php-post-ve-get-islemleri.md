---
id: 17
title: PHP Post ve GET İşlemleri
date: 2011-12-21T01:05:20+00:00
author: Hakan
layout: post
permalink: /php-post-ve-get-islemleri/
categories:
  - PHP
tags:
  - form
  - get
  - işlemleri
  - nasıl
  - php
  - post
  - yapılır
---
Php&#8217;de POST ve GET işlemlerinin nasıl olduğu hakkında ufak bilgiler paylaşalım.
  
Öncelikle POST ve GET metodları nelerdir? Ne işe yarar? Nerelerde kullanılır? onlardan bahsedelim. POST ve GET metodları PHP'de HTML formlarından gelen verileri işlemekte kullanılır. Örnek olarak bir form tasarladığımızı düşünelim;

{% highlight php %}
<form name="myForm" action="process.php" method="GET">
	Name:<input type="text" id="name">
	Surname:<input type="text" id="surname">
	<input type="submit" value="Send">
</form>
{% endhighlight %}


Bu kodlarda ne yaptığımızı açıklayalım. Bir form oluşturduk &#8220;name&#8221; ile formumuza &#8220;myForm&#8221; ismini verdik. &#8220;method&#8221; ile formumuzun GET metodu ile işleyeceğimizi ve &#8220;action&#8221; ile de formumuzun submit edildiği zaman hangi sayfada işleneceğini belirttik. 2 adet text input ve 1 adet buton ekledik. Kısaca kullanıcıdan ad ve soyad bilgilerini alıp bunları process.php sayfasında işleyeceğiz.
  
Kullanıcı Send butonuna tıkladığı zaman çağırılacak olan &#8220;process.php&#8221; sayfamızda neler yapmamız gerek onlardan bahsedelim.

{% highlight php %}
<?php
$name=$_GET["name"];
$surname=$_GET["surname"];
echo "Your Name:".$name."<br>";
echo "Your Surname:".$surname;
?>
{% endhighlight %}

process.php sayfamızın içeriği bu şekilde olsun. Şimdi bu sayfada neler yaptığımızı anlatalım. $name isimli değişkenimize GET metoduyla, gelen formdaki name isimli inputu atadık. Aynı şekilde $surname isimli değişkenimize gelen formdaki surname isimli inputu atadık. Bu noktada değinmemiz gereken önemli nokta $\_GET["name"] kısmı. PHP&#8217;de GET metoduyla gelen veriyi $\_GET["name"] ile yakalıyoruz. Aynı şekilde formumuzu POST metoduyla işleyecek olsaydık $_POST["name"] ile yakalayacaktık. Son olarak PHP echo fonksiyonu ile ekrana gelen verileri yazdık.
  
Burada değinmemiz gereken diğer bir nokta ise, POST ve GET metodları arasındaki fark. GET metodunu en akılda kalıcı şekilde açıklayacak olursak, gönderilen veriler URL&#8217;de görülebilir formattadır. Yani form verileri gönderildiği zaman process.php?name=hakan&surname=torun olarak görünecektir. POST metodunda ise process.php olarak çağırılacak ve veriler url'de görünmeyecektir.