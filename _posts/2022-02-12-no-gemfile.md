---
layout: posts
title:  "no gemfile"
categories: RoR
permalink: /:categories
---
### 沒有gemfile，也可使用套件 (Gem)！前提是，確定在正確的ruby-版號 （正確的位置），確定有 gem instal 該套件。

### 根據 我當前使用 ruby-版本號  下載Gem , 這個Gem就會儲存在 .rvm/gems/ruby-版本號
* * *
例如：
我當前是使用 ruby-2.7.4，gem  install rails， 這個 rails 儲存在 .rvm/gems/ruby-2.7.4，
我若切換到 ruby-3.0.0，要使用 rails => not found rails 是正常現象;
我要在 ruby-3.0.0 使用 rails，必須在 ruby-3.0.0 在 gem  install rails

資料夾中，不存在 gemfile 的檔案 , 在terminal cli: gem install 套件的名稱, 仍然可以把套件裝起來！

### gem install 套件名稱, 安裝的套件存放電腦的那個根目錄底下？
⇒ terminal cli: where 套件名稱
{% highlight ruby %}
# 套件名稱：pry
where pry
# /Users/chuangtsaoyuan/.rvm/gems/ruby-2.7.4/bin/pry 
{% endhighlight %}

### 當前使用 ruby-version，gem install 後的套件裝到哪裡去？

- type gem env

![image tooltip here](/assets/images/gem_env_view_gem_instal_in.jpg)

### ruby-2.7.4底下，下載了哪些套件？

- type gem list

![image tooltip here](/assets/images/.jpg)
### 一個套件, 只有一個存放位置嗎？ NO

⇒ 例如. 存放Rails, 就有兩個以上的位置
{% highlight ruby %}
#Gem name: rails
where rails
#/Users/chuangtsaoyuan/.rvm/gems/ruby-2.7.4/bin/rails
#/Users/chuangtsaoyuan/.rvm/rubies/ruby-2.7.4/bin/rails
#/usr/bin/rails
{% endhighlight %}
### 為什麼是在 .rvm?

我是使用 [RVM](https://rvm.io/)，所以 Gem 的安裝路徑會在 .rvm 目錄裡。

參考：

[gem install 之後，那些 gem 安裝到哪裡去了?](https://kaochenlong.com/2016/04/29/where-are-the-installed-gems/)

[rvm官網](https://rvm.io/)

[Ruby guide](https://www.rubyguides.com/2018/09/ruby-gems-gemfiles-bundler/)