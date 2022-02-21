---
layout: posts
title:  "Migration 介紹"
categories: Migration
permalink: /:categories
---
Rails 裡，專門用來對 database 的 table 上下其手的工具 **( Active Record Migrations )** 😎

Rather than write schema modifications in pure SQL, migrations allow you to use a Ruby DSL to describe changes to your tables. — Rails guide

(( 咱們忽略，可以對 database 的 table 上下其手其他方式，only use rails method！))

***

我們對 table 上下其手的過程，會被紀錄在 migrate 的 file 裡面，這只是紀錄上下其手的過程，要讓這些在 migrate 的紀錄發生！也就是說，產出 table 或 產出 table 的 column ...等其他上下其手的過程，我們需要執行 rake db:migrate，讓經過這些過程具體化並撰寫於 schema 內。