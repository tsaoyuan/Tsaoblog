---
layout: posts
title:  "Html element (1)，標籤語意化"
categories: Html element
permalink: /:categories
---
HTML, CSS, JavaScript 網頁前端三兄弟，HTML 用來制定網頁結構，定義語意標籤

製作網頁的過程中，不要被外在的視覺外觀影響，制定 HTML 標記的過程，當作在撰寫一份 word 文件。文件裡面的文字內容有一個主標題 (h1) 多個副標題 (h2) 多個內文 (p)...等，文件內，可能會有圖片、影音、表格、表單..等文件架構。
{% highlight html %}
<!-- 一份無序清單 -->
<!-- 快速產生： ul>li{我是清單}*3 -->
<ul>
  <li>我是清單</li>
  <li>我是清單</li>
  <li>我是清單</li>
</ul>

<!-- 兩份清單項目 -->
<ul>
  <li>我是清單</li>
<ul>

<ul>
  <li>我是清單</li>
<ul>
{% endhighlight %}

### 只看標籤的語意! 注重語意時，不看 (忽略) 視覺外觀; 注重標籤的語意 (需求)，忽略 CSS 的外觀控制
- 流程, 結果, 架構 ⇒  決定使用什麼語意，網頁設計沒有唯一解，沒有標準答案！
    - 流程：怎麼 run 畫面
    - 結果：決定需求; 外觀
    - 架構：選擇語意; 制定標籤

### 語意、架構清楚的優點
- SEO
- 無障礙網頁
- 易於給其他族群使用，像是手機用戶、低網速…等<br>

***
### 自我思考

- ### QA. 點擊的按鈕，使用哪種標籤？
    - 陷阱：點擊的按鈕。
    - 提示：依需求，決定標籤。
    - 思考：點擊後，要產生什麼”結果”，決定使用什麼標籤！別被字面上的用語，矇混了
        - \<a>         超連結; 通往其他頁面的超連結;  有資料、歷史紀錄 (返回上一頁, 下一頁)
        - \<button>    一個可點擊的按鈕; 開關使用，按下去，彈出一個視窗要填資料
        - \<div>       一个 “纯粹的” 容器 <br>


- ### QA. 語意兼外觀的標籤？
    - 粗體
        - \<b>      顯示”粗體”外觀，可以使用 CSS 的 font-weight 代替
        - \<strong> 十分重要，一般用”粗體”顯示外觀
    - 容器; 區域
        - \<div> 一個區域; “纯粹的” 容器;
        - \<section> 章節
        - \<article> 文章
        - \<header> Logo、搜索框、作者
        - ...等


- ### QA. 購物網站的路徑列，使用無序清單 or 有續清單？
    - 兩種方式都可以
    - 無續清單，沒有順序性。
    - 有續清單，代表順序性，從第一頁連結到下一頁，**階層性明顯**。


- ### QA. 一個1, 2, 3, 4 的清單，使用 \<ul> or \<ol> ?
    - 陷阱：1, 2, 3, 4。
    - 提示：依需求，決定標籤。
    - 思考：1, 2, 3, 4 作為外觀？還是這個清單需要的是”順序性”
    - 如果是順序性，請指名\<ol>，再使用 css 把外觀 1, 2, 3, 4的效果做出來。

***
參考：<br>
[HTML 元素](https://developer.mozilla.org/zh-TW/docs/Web/HTML/Element)<br>
[無障礙網頁](https://developer.mozilla.org/zh-TW/docs/Learn/Accessibility/What_is_accessibility)<br>

google 文件 :<br>
[Writing accessible documentation](https://developers.google.com/style/accessibility)<br>
[Headings and titles](https://developers.google.com/style/headings) （標題的好與壞）<br>