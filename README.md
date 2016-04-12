# js中cookie的使用详细分析
JavaScript中的另一个机制：cookie，则可以达到真正全局变量的要求。 cookie是浏览器 提供的一种机制，它将document 对象的cookie属性提供给JavaScript。可以由JavaScript对其进行控制，而并不是JavaScript本身的性质。

cookie机制将信息存储于用户硬盘，因此可以作为全局变量，这是它最大的一个优点。它可以用于以下几种场合。 

（1）保存用户登录状态。

例如将用户id存储于一个cookie内，这样当用户下次访问该页面时就不需要重新登录了，现在很多论坛和社区都提供这样的功能。 cookie还可以设置过期时间，当超过时间期限后，cookie就会自动消失。因此，系统往往可以提示用户保持登录状态的时间：常见选项有一个月、三个 月、一年等。 

（2）跟踪用户行为。

例如一个天气预报网站，能够根据用户选择的地区显示当地的天气情况。如果每次都需要选择所在地是烦琐的，当利用了 cookie后就会显得很人性化了，系统能够记住上一次访问的地区，当下次再打开该页面时，它就会自动显示上次用户所在地区的天气情况。因为一切都是在后 台完成，所以这样的页面就像为某个用户所定制的一样，使用起来非常方便。 

（3）定制页面。

如果网站提供了换肤或更换布局的功能，那么可以使用cookie来记录用户的选项，例如：背景色、分辨率等。当用户下次访问时，仍然可以保存上一次访问的界面风格。 

（4）创建购物车。

正如在前面的例子中使用cookie来记录用户需要购买的商品一样，在结账的时候可以统一提交。例如淘宝网就使用cookie记录了用户曾经浏览过的商品，方便随时进行比较。 

当然，上述应用仅仅是cookie能完成的部分应用，还有更多的功能需要全局变量。cookie的缺点主要集中于安全性和隐私保护。主要包括以下几种： 

（1）cookie可能被禁用。当用户非常注重个人隐私保护时，他很可能禁用浏览器的cookie功能； 

（2）cookie是与浏览器相关的。这意味着即使访问的是同一个页面，不同浏览器之间所保存的cookie也是不能互相访问的； 

（3）cookie可能被删除。因为每个cookie都是硬盘上的一个文件，因此很有可能被用户删除； 

（4）cookie安全性不够高。所有的cookie都是以纯文本的形式记录于文件中，因此如果要保存用户名密码等信息时，最好事先经过加密处理。 
```
如果要将cookie设置为10天后过期，可以这样实现： 

<script language="JavaScript" type="text/javascript"> 
<!-- 
//获取当前时间 
var date=new Date(); 
var expiresDays=10; 
//将date设置为10天以后的时间 
date.setTime(date.getTime()+expiresDays*24*3600*1000); 
//将userId和userName两个cookie设置为10天后过期 
document.cookie="userId=828; userName=hulk; expires="+date.toGMTString(); 
//--> 
</script>
```
cookie详细介绍地址：http://www.jb51.net/article/14566.htm
