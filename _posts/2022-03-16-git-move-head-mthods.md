---
layout: posts
title:  "Git 移動 HEAD 的方法 - checkout"
categories: Git move head
permalink: /:categories
tags: Git
---
## git checkout head 
- head 指向 branch 時，head 取消指向原本 branch，將 head 指向 commit，形成斷頭之姿！((head 不會移動，只會停在原 commit 上))
{% highlight git %}
Note: switching to 'head~'.
You are in 'detached HEAD' state. You...略
HEAD is now at 657fce7 add container
{% endhighlight %}

## git checkout head~
- head 在 branch 時，head 抽離原本 branch，往後跳一格 commit，形成斷頭之姿！
- "head~" 表示 head 在當下的 commit 往後跳一格 commit ; 效果等同於 "head~1"

## git checkout head~2
- "head~3" 表示 head 在當下的 commit 往後跳三格 commit
- 以此類推，head~n，就是當下的 commit 往後跳 n 格 commit


## head~n 的 n 超過可以跳的 commit 數，例如 commit 數只有 5 個，卻下了 git checkout head~6 會怎樣？
- 不會怎麼樣，錯誤警報 get
- error: pathspec 'head~6' did not match any file(s) known to git

## 不計算幾個 commit 數，直接使用 commit 代碼進行跳躍:
- git checkout commit-代碼
- git checkout cc79

---

以上操作，都是操作 (移動) head，斷頭 (detached HEAD) 純屬正常現象。有頭在手，head走到那，branch 貼到那。