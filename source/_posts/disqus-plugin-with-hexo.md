---
title: 整合Disqus comment 進 Hexo
date: 2019-02-25 10:41:05
tags: [Hexo, Disqus]
---


## Disqus是個專門提供留言板的服務, 且具有大的整合能力, 適合整合在blog, forum以及一些社群網站
<!-- More -->

* ### 首先先去 {% link Disqus [https://disqus.com/]%} 註冊會員. {% asset_img 1.png %}
* ### 接下來跳出選項, 選擇 I want to install Disqus on my site. {% asset_img 2.png %}
* ### 把new site資料填好, 按下Create Site. {% asset_img 3.png %}
* ### 選擇Basic Plan {% asset_img 4.png %}
* ### 在platform 中拉到最下面, 選擇 Universal Code {% asset_img 5.png %}
* ### 在instructions 頁面中, 直接拉到最下面 選擇 Configure {% asset_img 6.png %}
* ### 在Website Name填上剛剛申請的site name, Website URL填上blog網址, 按下Complete Setup{% asset_img 7.png %}
* ### 設定就完成了 {% asset_img 8.png %}
* ### 接下來去Hexo -> themes -> 主題資料夾 -> _config.yml中開啟disqus設定, 這邊以next做示範 {% asset_img 9.png %}
* ### 發布Hexo後, 就能看到blog下方出現Comments 區囉 {% asset_img 10.png %}