---
layout: posts
title:  "建立 migrate file 方法"
categories: Create Migration 
permalink: /:categories
---
建立 migrate file 途徑有很多，這裡介紹其中的兩個方法：

- rails g model model_name
- rails g migration migrate_file_name

***

相信大家使用 Rails ，都該熟悉 CoC (Convention Over Configuration; 慣例優於設定)，剛認識 Rails 的各位， CoC 是怎麼回事？！ CoC 換句話說，照著Rails的潛規則，Rails會幫你省掉些設定，不然你會很痛苦，因為什麼都要自己設定！
{% highlight ruby %}
# CLI
rails g model model_name
# model_name，使用"單數名詞" 或 "複數名詞"? 
{% endhighlight %}

### Rails 貼心提醒，像是使用CLI 建制一個 model ，model 名稱使用單數名詞 or 複數名詞?

- **單數名詞**作為 model_name
- 若用複數名詞作為 model_name，請三思 ((別自己搞自己
- model_name: cats，雖然建立 model 時，使用複數名詞，Rails 順手幫你改成單數名詞。除非必要，別自己改成複數名詞檔名  ((別自己搞自己
{% include figure image_path="/assets/images/單數or 複數.jpg" alt="migrate file use 單數名詞" %}
不管你使用 model_name 是單數名詞 or 複數名詞，在 app/models 底下，產生 model_name.rb ，和 db/migrate 底下，產生 YYYYMMDDHHMMSS_create_model_names.rb 

***

### 手動建立 migrate file
{% highlight ruby %}
# CLI
rails generate migration whatever_you_want_file_name
# migrate file 檔名若有空白，請使用底線區隔兩單字
# migrate file 有意義的檔名，維護會相對容易
{% endhighlight %}

{% include figure image_path="/assets/images/step0 Add new Migration.jpg" alt="create migrate file" %}

參考：<br>
**[Active Record Migrations](https://edgeguides.rubyonrails.org/active_record_migrations.html)**<br>
[為你自己學 Ruby on Rails](https://railsbook.tw/chapters/17-model-migration) 

備註：<br>
Rails 6.1.4.6 <br>
ruby 2.7.4p191 (2021-07-07 revision a21a3b7d23)