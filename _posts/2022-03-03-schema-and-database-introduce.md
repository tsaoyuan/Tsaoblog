---
layout: posts
title:  "Ruby on Rails 的 database, schema, schema.rb 白話敘述"
categories: introduce RoR Schema
permalink: /:categories
---
討論行程路線 ＝ migrate file <br>
筆記在大家的共同行程 ＝ rails db:migrate <br>
共同行程的快照 = schema.rb <br>
蒐集 / 創造回憶 ＝ database <br>


出門玩，三五好友討論行程路線，三五好友都同意，將討論後的行程路線筆記在大家的共同行程，大家依照共同行程的快照旅遊，蒐集 / 創造回憶。<br>
往後覺得共同行程好玩，但是忘記大家當初怎麼討論行程路線，只要有共同行程的快照，依然可以照著
共同行程的快照走，蒐集 / 創造新的回憶

***

database：
- 存放資料容器
- 資料表/欄位
- 內涵資料
- 語意包含 schema<br>

schema：
- 某些 SQL的 schema 等同於 database, 例如 MySQL
- 沒有資料
- 描述 database 架構
    - table_name
    - column_name
    - data type
    - pk, fk

schema.rb (Ruby on Rails)
- database 的快照

***
### 如果要建立一個全新資料庫 (把資料表建回來)?
{% highlight ruby %}
# 依照 schema 架構，建立一個全新的空資料庫
rails db:schema:load
{% endhighlight %}
### 在 database 有欄位，但是 schema.rb 卻沒有，例如 database user table 有10個欄位，但是 schema 卻顯示 8個！ 怎麼會相差兩個欄位？
有人直接操作 database 新增欄位，而不是透過  rails db:migrate 變更 schema.rb，產生兩個欄位的落差，這時只要執行  rails db:migrate ，就可以在  schema.rb，將缺少的兩個欄位補回來。

***
參考：

[introduce schema in Rails Guides](https://edgeguides.rubyonrails.org/active_record_migrations.html)

[What is a database schema?](https://youtu.be/3BZz8R7mqu0) (生動描述 schema 作用)

[Difference between database and schema](https://stackoverflow.com/questions/5323740/difference-between-database-and-schema)

[Schema 檔案的格式](https://ihower.tw/rails/migrations.html#schema%E6%AA%94%E6%A1%88%E7%9A%84%E6%A0%BC%E5%BC%8F)

[In MySQL, a schema is a database, so this table provides information about databases.](https://dev.mysql.com/doc/refman/8.0/en/system-schema.html)