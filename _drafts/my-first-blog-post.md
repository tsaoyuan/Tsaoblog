---
layout: posts
title:  "Welcome to my first post"
---

# drafts (草稿) content 

### 啟動local jekyll
- bundle exec jekyll serve
### 檢視草稿方式 (本機端檢視)：
- jekyll serve \--drafts 
- jekyll s \--drafts

### drafts注意：
- 檔名不需要慣YYYY-mm-dd
- _drafts內的檔案, 不顯示在 github pages上; 除非使用 jekyll s \--drafts 在本機端檢視
- 草稿顯示的url, 會是test 當日的YYYY-mm-dd
- 參考： <https://youtu.be/X8jXkW3k2Jg>

### 新增圖片方法
{% include figure image_path="/assets/images/gem-env-view-gem-instal-in.jpg" alt="this is a placeholder image" caption="This is a figure caption." %}
### 新增code區塊
{% highlight ruby %}

{% endhighlight %}

### 遇到html element + \
### markdown 無法使用 空白 and Tab 縮排

  