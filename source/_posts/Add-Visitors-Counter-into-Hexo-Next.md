---
title: Add Visitors Counter into Hexo Next
tags:
  - Hexo
  - Firebase
date: 2019-02-26 18:13:18
---


## Firebase是 Google專為行動應用開發者所提供的後端平台服務 (BaaS), 可以快速搭建後端以及資料儲存服務, 並提供強大的分析工具

### Hexo Next在Blog中也提供 Firebase支援, 紀錄文章瀏覽次數等統計數據
<!-- More -->
* ### 首先 先到 {% link Firebase [https://firebase.google.com/?hl=zh-tw] %}首頁, 登入google 帳號, 然後按下 GET STARTED {% asset_img 1.png %}
* ### 接著新增專案 {% asset_img 2.png %}
* ### 填入專案名稱, 這邊以hexo-net-visitors-counter為例{% asset_img 3.png %}
* ### 按下建立專案後, 等待firebase建立 {% asset_img 4.png %}
* ### 看到專案就緒後, 按下**繼續**, 進入Firebase專案頁 {% asset_img 5.png %}
* ### 選擇 Database, 按下**建立資料庫** {% asset_img 6.png %} 
* ### 選擇**以鎖定模式啟動**, 等待安全設定完成 {% asset_img 7.png %}
* ### 接下來在左上角選擇專案設定 {% asset_img 8.png %}
* ### 將專案ID跟API key複製下來 {% asset_img 9.png %}
* ### 接著開啟 Next的_config.yml, 填入以下設定參數
    **articles**是給 firebase用的集合id, 這邊若做修改, firebase設定也要跟著改
     {% asset_img 10.png %}
* ### 我們回到firebase網頁, 按下**Database**, 選擇**規則** {% asset_img 11.png %}
* ### 在右方出現的規則script, 加入權限判斷 {% asset_img 12.png %}
* ### 發佈後等待幾分鐘讓他生效, 接著回到文章, 點選看看, 次數應該會增加 {% asset_img 18.png %}
* ### 回頭來看 firebase的資料集合, 應該會呈現下圖所示, 文章標題與count數都紀錄進來了 {% asset_img 17.png %}