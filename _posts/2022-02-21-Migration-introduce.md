---
layout: posts
title:  "Migration 簡介"
categories: Migration
permalink: /:categories
---
Rails 裡，專門用來對 database 的 table 上下其手的工具 **Active Record Migrations** 

Rather than write schema modifications in pure SQL, migrations allow you to use a Ruby DSL to describe changes to your tables. — Rails guide

(( 咱們忽略，可以對 database 的 table 上下其手其他方式，only use rails method！))

***

我們對 table 上下其手的過程，紀錄在 migrate 的 file 裡面，這只是我們自己手動紀錄上下其手的過程，要讓這些在 migrate 的紀錄發生！也就是說，產出 table 或 產出 table 的 column ...等其他上下其手的過程，我們需要執行 rails db:migrate，讓這些紀錄具體化並撰寫於 schema.rb 內。（不需要也沒必要手動改寫 schema 內容，改變 schema 內容使用 migrate）

上下其手，意指，新增 / 修改 / 刪除 table 和 table 的 column，可以把 schema.rb 視為現在 database 的最新版本內容，database 透過 migrate 修改後，產出 schema.rb 。 schema.rb 內涵有table, table_name, table_column, table_column_type的資訊。另外每個 migrate file 都有一串數字，如 圖片中，紫框處
{% include figure image_path="/assets/images/migrate file name.jpg" alt="this is a image about migrate file name"  %}

這串數字代表的是建立檔案的時間 (YYYYMMDDHHMMSS)，雖然檔名可以是 whatever，這裡使用 create_users 方便我在檢視檔案，我習慣有意義的命名，維護會相對容易。

***

**Active Record Migrations** 好用在：

你只需要用 Ruby DSL 操作 **Migrations** ，就可以操作不同資料庫 (SQLite3, MySQL, postgresql...等) ，不同資料庫的 SQL 語法雖相近，但是可以用一個標準化的工具，操作不同資料庫，取得相同的結果。

每次修改資料庫的過程都會被記錄下來，也都會進 Git 版本控制，所以整個資料庫的設計過程全部都可以一目了然。若是從SQLite3 轉到 postgresql 或其他資料庫，除非有特殊要求，通常只要一行指令，就可以再把資料庫建回來。

備註：<br>
DSL ( 領域特定語言; domain-specific language )

參考：

[Active Record - 資料庫遷移(Migration)](https://ihower.tw/rails/migrations.html)

[Active Record Migrations](https://edgeguides.rubyonrails.org/active_record_migrations.html)

[為你自己學 Ruby on Rails](https://railsbook.tw/chapters/17-model-migration)