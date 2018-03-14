---
layout: post
title:  Happy Pi Day
bigimg: /img/pi-day.jpg
tags: [Pi Day, pie]
---
Happy [Pi Day](http://www.piday.org)! In honor of today, I thought I’d share with some of the delicious-looking work of Teeny Lamothe, owner of Teeny Pies. Harmonie and I went to school with Teeny and I discovered her passion for pies last year on [Instagram](https://www.instagram.com/teenypies/). 

<script>
   function httpGet(theUrl)
   {
       if (window.XMLHttpRequest)
           {// code for IE7+, Firefox, Chrome, Opera, Safari
               xmlhttp=new XMLHttpRequest();
           }
       else
           {// code for IE6, IE5
               xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
           }
       xmlhttp.onreadystatechange=function()
       {
           if (xmlhttp.readyState==4 && xmlhttp.status==200)
               {
                   createDiv(xmlhttp.responseText);
               }
       }
       xmlhttp.open("GET", theUrl, false);
       xmlhttp.send();    
   }

   function createDiv(responsetext)
   {
       var _body = document.getElementsByTagName('body')[0];
       var _div = document.createElement('div');
       _div.innerHTML = JSON.parse(responsetext)["html"];
       _body.appendChild(_div);
   }

   httpGet("https://api.instagram.com/oembed?url=http://instagr.am/p/{{ include.id }}/");
  </script>

Visit her [site](https://www.teenypies.com) to read her blog, order pies, or learn more about her cookbook!