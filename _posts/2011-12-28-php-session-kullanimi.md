---
id: 34
title: PHP Session Kullanımı
date: 2011-12-28T02:12:01+00:00
author: Pase
layout: post
guid: http://www.pasein.com/?p=34
permalink: /php-session-kullanimi/
categories:
  - PHP
tags:
  - php
  - session
---
PHP&#8217;de olmazsa olmazlardan biri olan session kullanımından bahsedelim.
  
Session bir nevi global değişkenlerdir. Farklı php dosyalarında erişmek istediğiniz veriler olabilir. Örneğin sisteme giriş yapmış kullanıcı adını Session nesnesinde tutalım ve buna erişelim. Kullanıcının sisteme başarılı bir şekilde giriş yaptığını varsayalım. Kullanıcı adı $username değişkeninde saklanıyor olsun. Mesela login.php sayfamızda;

{% highlight ruby %}
&lt;?php
session_start();
$_SESSION["username"]=$username;
?&gt;
{% endhighlight %}

Buradaki session_start() fonksiyonuyla yeni bir oturum başlattık ve session nesnesine username isimli değişkendeki veriyi aktarmış olduk.
  
Diyelim ki redirect.php diye bir yönlendirme sayfamız var ve bu sayfamız kullanıcı başarılı bir giriş yaptıktan sonra anasayfaya yönlendiriyor olsun. Login.php sayfamızdaki $username değişkenimizi bu sayfada kullanamayız. Dolayısıyla session işimizi görecek.

{% highlight ruby %}
&lt;?php
session_start();
echo "Hoşgeldin ".$_SESSION["username"];
?&gt;
{% endhighlight %}

gibi bir kullanım yapabiliriz. Burada basitçe login.php&#8217;de başarılı bir şekilde giriş yapmış olan kullanıcıya redirect.php sayfasında hoşgeldin dedik.
  
Bu makaleyi yazarken anladım ki daha detaylı kullanımı ve bir üyelik sistemi hakkında yeni bir makale paylaşmam gerek. Şimdilik bu kadar. Detaylı kullanımını tekrardan kaleme almalıyım..