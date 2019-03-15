---
title: Zapier Convert Flac to MP3 via Dropbox - 01
tags:
  - Zapier
  - CloudConvert
  - Dropbox
  - MP3
date: 2019-03-16 00:42:34
---


# 使用Zapier自動化轉檔與儲存 (上)

文章長, 圖片多慎入~

<!-- More -->

最近開始研究Zapier到底能做多少事, 發現他連上的服務比IFTTT多好多啊..

至少多兩倍有

此篇文章就藉由**Zapier**連結 **Dropbox** 與 **CloudConvert**兩大網路服務來達成自動轉檔的功能 **Flac-> MP3**

要達成這功能, 分為兩個Zap, 分別是
    
* 利用Zapier監控Dropbox指定資料夾新增檔案, 並將檔案傳給CloudConvert

* 利用Zapier將CloudConvert轉完的檔案轉存到Dropbox指定資料夾

---

## 利用Zapier監控Dropbox指定資料夾新增檔案, 並將檔案傳給CloudConvert

### 連結Zapier與Dropbox

* 首先先登入或註冊Zapier
{% asset_img 1.png %}

* 在左邊格子打上Dropbox, 選取下面的服務
{% asset_img 2.png %}

* 接下來在右邊格子打上CloudConvert, 選取下面的服務
{% asset_img 3.png %}

* 畫面會跳出兩個已存在的Zap, 這步驟先選取 **Convert files added Dropbox folder with CloudConvert**, 按下**Use This Zap**
{% asset_img 4.png %}
{% asset_img 5.png %}

* 畫面會顯示Dropbox Trigger, 並說明限制為何, 按下Continue繼續
{% asset_img 6.png %}

* 按下Connect an Acount, 登入dropbox並按下Allow
{% asset_img 7.png %}
{% asset_img 8.png %}

* 跳出Dropbox Account確認, 按下Test, 跳出Success代表設定成功
{% asset_img 9.png %}
{% asset_img 10.png %}

* 接下來選擇Dropbox上的Folder, 資料夾須自己建立, 這次是要選擇Convert資料夾
{% asset_img 11.png %}
{% asset_img 12.png %}

* 再來本機有裝dropbox套件的話, 移至本機的Dropbox資料夾, 選擇Convert資料夾, 貼上要轉的flac檔
{% asset_img 13.png %}
{% asset_img 14.png %}

* 這時候Zapier畫面會顯示抓到測試檔案, 選擇Continue繼續
{% asset_img 15.png %}

### 連結Zapier與CloudConvert

* 現在來設定CloudConvert動作, 只有一個**Convert File**, 選Continue繼續
{% asset_img 16.png %}

* 連結CloudConvert, 按下Connect an Acount
{% asset_img 17.png %}

* 再來會看到要輸入CloudConvert API Key, 到{% link "CloudConvert" https://cloudconvert.com/ %}網站, 

  若沒有帳號就註冊一個, 在帳號下左邊選擇 **API V1**->**API Keys**, 
  
  將右側的API Key copy起來, 填入Zapier連結的頁面中
{% asset_img 18.png %}
{% asset_img 19.png %}
{% asset_img 20.png %}

* 再來就可以測試看看 看到Success代表設定成功
{% asset_img 21.png %}
{% asset_img 22.png %}

* 終於快完成第一步了~, 在Output Format選擇要轉的格式, 這邊是轉MP3
{% asset_img 23.png %}

* Save選項看個人, 選擇yes他會殘留檔案在CloudConvert上, 

  選擇no則是下載一次後就刪除
{% asset_img 25.png %}

* 最後對這個Zap設定做個Final Test, 成功就完成第一步驟
{% asset_img 26.png %}
{% asset_img 27.png %}
{% asset_img 28.png %}

### 下一篇介紹存檔的Zap設定

{% post_link Zapier-Convert-Flac-to-MP3-via-Dropbox-02 %}