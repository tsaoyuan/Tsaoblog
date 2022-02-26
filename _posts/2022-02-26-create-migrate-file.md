---
layout: posts
title:  "建立 migrate file 方法"
categories: Migration
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