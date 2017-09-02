---
id: 120
title: Jquery Ui ve Php İle Otomatik Tamamlama
date: 2013-07-27T18:19:32+00:00
author: Pase
layout: post
guid: http://www.hakantorun.com.tr/?p=120
permalink: /jquery-ui-ve-php-ile-otomatik-tamamlama/
categories:
  - Javascript
  - PHP
tags:
  - autocomplete
  - google
  - javascript ile otomatik
  - jquery
  - jquery ui
  - nasıl
  - otomatik
  - php ile
  - php ile otomatik tamamlama
  - tamamlama
  - yapılır
  - yapımı
---
Otomatik tamamlama bir çok noktada hem kullanıcının hem programcının işini kolaylaştırıyor. Otomatik tamamlama ile ilgili fazlasıyla jquery plugini mevcut. Biz Jquery ui ile küçük bir örnek yapacağız.

Hazırlık:

- Öncelikle jquery ui için http://jqueryui.com/download/ adresinden jquery ui download builder aracını kullanarak jquery ui son versiyonunu indiriyoruz. Bizim için lazım olan widgetlardan autocomplete. İndirdiğimiz dosya içerisinden jquery ui javascript dosyası ve jquery ui css dosyası bizim için gerekli olan dosyalar. Tabi ki jquery son versiyon da jquery ui için gerekli.<!--more-->

Öncelikle css ve js dosyalarımızı autocomplete kullanacağımız projemize dahil ediyoruz.

<pre>&lt; link rel="stylesheet" type="text/css" href="css/jquery-ui-1.10.3.custom.css" >
   &lt; script type="text/javascript" src="js/jquery-ui-1.10.3.custom.min.js">&lt;/script>

   &lt; input type="text" id="search" name="search" >

</pre>

Autocomplete kullanacağımız input alanı için şöyle bir yol izlememiz gerekiyor;

    
    $(function() { 
        $( "#search" ).autocomplete({
          source: function( request, response ) {
            $.ajax({
              url: "search.php",
              dataType: "json",
              data: {
    		term: request.term
              },
              success: function( data ) {
                response( $.map( data, function( item ) {
                  return {
                    label: item,
                    value: item
                  }
                }));
              }
            });
          },
        });
    });
    
    

Yaptığımız aslında basitçe bir ajax olayı ve input alanına her karakter girilince tetiklenmesini sağlamak. Search idsine sahip input alanına her girilen karakter tekrar ajax isteği başlatıyor ve search.php dosyamıza parametre geçerek bize bir json verisi döndürüyor. Yani örneğin kullanıcının &#8220;ali&#8221; kelimesini aratacağını düşünelim;

- Kullanıcı a harfine bastığında ajax olayı search.php?term=a
  
- Kullanıcı l harfine bastığında ajax olayı search.php?term=al
  
- Kullanıcı i harfine bastığında ajax olayı search.php?term=ali sayfasına istekte bulunacak ve bize search.php sayfamızdan bir json verisi dönecek. 

Search.php sayfamızı basitçe şöyle kurgulayabiliriz.

    
    $options = array();
    $term    = $_GET['term'];
    $results = $this->db->get_results('SELECT name FROM user WHERE name LIKE '$term%''); //Kullandığımız metoda göre veritabanında arama yapıyoruz
    
    foreach($results as $k=>$v):
    {
       $options[] = $v->name;
    }
    
    echo json_encode($options);
    

Search.php sayfamızda gelen parametreye göre veritabanımızda arama yapıyoruz ve sonucu json verisi olarak ekrana basıyoruz. Ajax olayı da bu sayede json verisini geri sonuç olarak alıyor ve input alanında otomatik tamamlama verisi olarak kullanıyor. 

Şimdilik bu kadar.