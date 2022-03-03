---
layout: posts
title:  "Ruby on Rails 的 schema 和 database 簡介"
categories: introduce RoR Schema
permalink: /:categories
---
討論行程路線 ＝ migrate file <br>
筆記在大家的共同行程 ＝ rails db:migrate <br>
共同行程的快照 = schema.rb <br>
蒐集 / 創造回憶 ＝ database <br>


出門玩，三五好友討論行程路線

三五好友都同意，將討論後的行程路線筆記在大家的共同行程

大家依照共同行程的快照旅遊，蒐集 / 創造回憶

往後覺得這個行程好玩，但是忘記大家當初怎麼討論行程路線，只要有這個

共同行程的快照，依然可以照著共同行程的快照走，蒐集 / 創造新的回憶

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

Ruby on Rails: schema.rb
- database 的快照