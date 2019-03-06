---
title: 自訂 IFTTT Applet 初體驗
date: 2019-03-06 12:10:22
tags:
  - IFTTT
  - RSS
  - LinkedIn
---


## 如果IFTTT上提供的現有功能不敷使用, 可以建立屬於自己的Applet
<!-- More -->

### IFTTT 就是 IF This Then That的縮寫

之前使用的RSS to LinkedIn Applet, 轉發去LinkedIn缺少預覽功能, 但是又沒選項可以調整

因此打算自己建立Applet

在IFTTT上建立Applet有兩種方式, 

1. Create new applet directly

2. Create applet by IFTTT platform

### 此篇先介紹第一種方式

---

* 首先到{% link IFTTT [https://ifttt.com/discover] %}左上角註冊會員
{% asset_img 1.png %}
   

* 註冊完後下拉式選單選擇 **New Applet**
{% asset_img 2.png %}   
   

* 就會看到如下圖所示, 點選 **this**
{% asset_img 3.png %}
   

* 就會跳出現有服務選擇
{% asset_img 4.png %}
   

* 由於這次是要修改RSS to LinkedIn的格式, 在輸入框中打入RSS便會跳出服務
{% asset_img 5.png %}

* 在trigger中選擇 New feed item
{% asset_img 6.png %}

* 在Feed URL內填上RSS檔案位置
{% asset_img 7.png %}

* 跳回if this then that, 這時候可以注意到 this被換成RSS了, 選擇that繼續
{% asset_img 8.png %}

* 在service中打上LinkedIn, 選取服務
{% asset_img 9.png %}

* 選擇Share an update
{% asset_img 10.png %}

* 接下來就是選擇該怎麼呈現在LinkedIn上的內容, 按下Add ingredient選擇, 經過多次嘗試, 如下圖選取就會呈現出Blog縮圖
{% asset_img 11.png %}

* 按下Create action後, 跳出Review and finish的頁面, 修改一下敘述即完成
{% asset_img 11.png %}

---

第一種方式優點, 能迅速搭建IFTTT功能, 缺點是彈性不大, 可以發現RSS feed url被刻死了, 因此只適合自己用

第二種方式留待下篇介紹