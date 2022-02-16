---
layout: posts
title:  "Figaro"
categories: Gem
permalink: /:categories
---
啟動專案服務時，往往需要透過 API 和 金鑰等秘密資訊，進一步啟動專案的第三方服務。

開發者推專案到GitHub時，<font color="#f00">不能 </font>將這些秘密資訊的明碼，寫在專案的文件內，但是又要讓其他開發者可以透過秘密資訊啟動第三方服務！那要怎麼把這些秘密資訊放在專案內，並把專案到推到GitHub上，確保秘密資訊不被外來者拿到！ 另外，其他開發者將專案從GitHub 拉到本地端的電腦，又可以正常啟用第三方的服務呢！

這時就是  Figaro 登場的時機，當開發者將專案推上GitHub 時，事先使用 Rubygems 的 Figaro 將秘密資訊隱藏在 ENV！ 其他開發者(例如: 小明) 將專案從GitHub 拉下來，依照 .example 的格式，產出放置鑰匙的文件，小明再將要填寫的秘密資訊明碼依依填入，因此，小明就能啟用第三方的服務。小明在推專案到GitHub，秘密資訊也會一併忽略。

 Figaro 幫我產出 application.yml 專門放置秘密資訊的明碼，application.yml 檔案會紀錄在.gitignore之中，這確保我在git push時，我的秘密資訊不會被推上 GitHub。

我在 git push 之前，我需要自己產出一個 application.yml.example，告知其 小明 ，我的 application.yml 格式，讓 小明 知曉 application.yml 的結構，小明 依 .example 結構，在小明的電腦上產出application.yml ，並依依填入秘密資訊的明碼，小明便能啟用秘密資訊相對應的服務。

經了解 Figaro 的作用方式，我突然想到，使用RO外掛會被盜的其中一個原因，不知道你們跟我想的是不是一樣😅

在分享RO外掛的同時，不小心把自己的帳密也一起分享出去了😱

* * *

### 使用 figaro， 幫你隱藏各種秘密資訊，例如api 、 金鑰、ID...
{% highlight ruby %}
# 開始使用 Figaro，在gemfile新增：
gem 'figaro', '~> 1.2'

# 在cli執行，載入 figaro
bundle exec figaro install
{% endhighlight %}

### application.yml  append 在 .gitignore內，push 到 github時，不用擔心秘密資訊曝光😙
{% include figure image_path="/assets/images/起手勢-figaro.png
" alt="this is a placeholder image about bundle figaro" %}

### 使用 Figaro 方式

專門放置鑰匙的檔案: application.yml  (上傳GitHub時，會被忽略）<br>
使用鑰匙檔案: pusher.rb (whatever.rb) （文件內沒有明碼，秘密資訊使用ENV）<br>
啟動第三方服務時，兩個檔案**透過**環境變數 ENV[”name”] 互通，取得秘密資訊。
把 Key 放到環境變數 (ENV)，怎麼放進去環境變數呢！<br>
{% include figure image_path="/assets/images/起手勢-figaro ENV and Key .png
" alt="this is a image about figaro set ENV" %}
紅框處: developer 命名， application.yml 和 pusher.rb 的 ENV名稱一致。( 別打錯字 ) <br>
黃框處: 官方提供的名稱 (這裡的官方是 pusher) <br>
* * *
既然使用到ENV，雜們就來檢視專案內的ENV吧！
檢視 ENV cli

{% highlight ruby %}
# 以下cli 可執行在 irb 和 rails c
# irb => 檢視 irb (Interactive Ruby) 的互動式命令列
# rails c => 檢視 rails 專案
# 檢視環境變數 "GEM_HOME" 路徑
ENV["GEM_HOME"]
# "/Users/yourname/.rvm/gems/ruby-2.7.4"

# 檢視存在那些環境變數
ENV.keys

# 總共有幾個環境變數
ENV.keys
{% endhighlight %}

### oops! 執行rails c ，產生狀況:
{% include figure image_path="/assets/images/起手勢-figaro rails console error (1).png
" alt="this is a image about rails console error" %}
{% include figure image_path="/assets/images/起手勢-figaro rails console error (2).png
" alt="this is a image about rails console error" %}

### 解決突發狀況 - not find gem 'pusher'
{% highlight ruby %}
# 在 gemfile 新增
gem 'pusher'

# 在cli 輸入
bundle instal
# 將 pusher 的 gem 載入 rails 專案
{% endhighlight %}

{% include figure image_path="/assets/images/起手勢-figaro instal pusher.png
" alt="this is a image instal pusher" %}
### 使用 cli 檢視 ENV 的狀況
{% include figure image_path="/assets/images/起手勢-figaro rails console success.png
" alt="this is a image view rails ENV" %}
### 建立一個application.yml範例檔，當作秘密資訊的格式檔，檔名: application.yml.example
application.yml.example 作為設定管理機密資訊的架構，供其它開發者參考 application.yml 格式填寫。
{% include figure image_path="/assets/images/起手勢-figaro application.yml 架構.png
" alt="this is a image abot set ENV" %}

### 推上GitHub 的 Key 、私密資訊，不在程式碼內 - 達成 🥳
* * *
參考：<br>
[figaro](https://github.com/laserlemon/figaro/) <br>
[如何使用環境變數](https://ithelp.ithome.com.tw/articles/10249250) <br>
[Rails Environment Variables](http://railsapps.github.io/rails-environment-variables.html)<br>
[使用figaro管理機密資訊或密碼的gem以及fog](https://gregning.github.io/ruby-on-rails/2018/01/30/5408775/)<br>