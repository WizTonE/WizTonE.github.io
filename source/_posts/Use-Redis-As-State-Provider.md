---
title: Use Redis As State Provider
date: 2019-04-19 19:46:53
tags:
---


## Redis提供速度卓越的Caching Service
## 既然是Caching Service, 那拿來取代Session操作也是很合理的
<!-- More -->

### 以下介紹如何實做 Redis Session State Provider

* ### 首先先開啟NuGet, 搜尋 redissessionstateprovider
    {% asset_img 01.png %}

    選取Microsoft提供的套件, 記得選取對應的 .NETFramework版本

* ### 選取Accept 等候安裝完成
    {% asset_img 02.png %}
    
    安裝完後會跳出readme.txt, 講Azure有提供Redis 的資源

* ### 在Web.config中找到 sessionState區塊, 在 providers內將原有的部份mark起來, 再加入以下字串
    {% asset_img 02.png %}

    {% codeblock %}
    <add name="MySessionStateStore" 		type="Microsoft.Web.Redis.RedisSessionStateProvider" host="127.0.0.1" accessKey="" 	ssl="false" />
    {% endcodeblock %}
    
    ip記得替換成redis的位置

* ### 就可以已原有操作Session方式使用了~
    {% codeblock lang:C# %}
    var session = CurrentContext.Session;
    session[$"Server_{Token}"] = token;
    {% endcodeblock %}

### 簡單易用~ 又可做到Session State獨立存放, 便於後續rolling deployment之用