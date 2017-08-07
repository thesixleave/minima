---
layout: post
title: pre輸入textarea同步
---

<html>
<head>
<style>
.content{
        background:yellow;
        outline:none;}
.line{
     float:left;
     clear:both;
     background:blue;
}
    
</style>

<script  src='https://code.jquery.com/jquery-2.x-git.min.js'></script>
<script>
$('document').ready(function(){


var tx= $('#p')
var con=$('.content')

var div = new RegExp("<div>","g");
var div2 = new RegExp("</div>","g");
var br = new RegExp('<br>','g')
var o =new RegExp('&lt;','g')
var ya=new RegExp('&gt;','g')
var text7=new RegExp('&amp;','g')

$.fn.keyrun=function(e){



tx.val(con.html().replace(div,'\n').replace(div2,'').replace(br,'').replace(ya,">").replace(o,"<").replace(text7,'&'))   
       


}

con.keyup(function(e){

$.fn.keyrun(e)

})

con.keypress(function(e){

$.fn.keyrun(e)

})

con.keydown(function(e){

$.fn.keyrun(e)

})
})
</script>
</head>
<body>

<pre class="content" contenteditable="true">
</pre> 
<textarea id='p' ></textarea><br>
<button id='btn'>確認</button>
</body>
</html>
