---
layout: posts
title:  "Ruby的 { } "
categories: Ruby block
permalink: /:categories
---
Ruby的世界裡，幾乎所有的東西都是**物件**，block例外! 

### block兩種表示方式:
- { } ; 又稱 **curly braces**
- do...end

### { } 為例
{% highlight ruby %}
3.times {|number| puts "hi man #{number}" }
#=> hi man 0
#=> hi man 0
#=> hi man 0
{% endhighlight %}

我曾經卡在對 |number| 的理解，看到這兩個猶如絕對值的符號，啊 😱！我卡蠻久。<br>
尤其是 | | 內的變數名稱，起初我以為變數 number 被 |  | 框住，要求解這個變數的 Absolute value！
其二是被框在絕對值記號的變數命名要有意義的！<br>

這個在兩根看起來像牆壁中間的 <font color="#f00">number</font>，是在這個 Block 範圍裡的**區域變數**，離開 Block 之後就會失效了。看到我用**whatever**，表示區域變數名稱可以自己取，具有意義的『區域變數名稱』，易於閱讀。
在{ }裡面使用變數，得要先用 | | 框住變數名稱，再次使用變數就不用 | | 框住了。

在字串內使用變數，要以 #{ 變數 }的方式：
{% highlight ruby %}
3.times {|number| puts "I have #{number+1} apple!"}
#=> I have 1 apple!
#=> I have 2 apple!
#=> I have 3 apple!
{% endhighlight %}
***
### do...end 為例
{% highlight ruby %}
(1..3).each do |number|
  puts "I have #{number} apple!"
end
# I have 1 apple!
# I have 2 apple!
# I have 3 apple!
{% endhighlight %}

### 參考 stack overflow， do..end 和 curly braces 差異：
do..end 用在 多行的程式 <br>
curly braces 用在 單行的程式 <br>

***

參考：
[do..end vs curly braces for blocks in Ruby](https://stackoverflow.com/questions/5587264/do-end-vs-curly-braces-for-blocks-in-ruby)
[DAY11 程式碼區塊（Block）](https://ithelp.ithome.com.tw/articles/10220491)
