---
layout: posts
title:  "快速變更 database 設定"
categories: RoR fast-change-database
permalink: /:categories
---
### 除了new專案前，預設 database 為 postgresql 之外，還有其他方法嗎？
方法一：
{% highlight ruby %}
# 在空資料夾中，開啟一個Rails的新專案，預設 database ＝ postgresql
rails new . --database=postgresql
# 創立新專案，預設 database ＝ postgresql
rails new 專案名稱 --database=postgresql
{% endhighlight %}
方法二：<br>
手動 copy / paste 修改 gemfile, database.yml <br>

***
### Rails 6 之後有個新功能，在new 專案後，再變更 database 的預設，那就是： 
{% highlight ruby %}
# 原先若是使用SQLite3 開發專案，改用 postgresql
rails db:system:change --to=postgresql
# Rails 變更 gemfile 設定
bundle
{% endhighlight %}
***
### oops!
{% include figure image_path="/assets/images/step0 set database GG.jpg
" alt="this is a image about I have issue" %}

{% highlight ruby %}
# M1電腦產生問題：
# Running via Spring preloader in process 86186
# invalid option: --database=postgresql
# ----------- 解惑--------------------
# 純粹我自己電腦 (M1) 的問題，善心人士幫我解答！
# 其他版本的蘋果電腦，是 Run 的起來的喔！
# M1 乖乖的使用: rails new 專案名稱 --database=postgresql
{% endhighlight %}
***
參考：
**[The Rails db:system:change command](https://gorails.com/episodes/rails-6-db-system-change-command)**
