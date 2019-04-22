---
title: Use ConnectionString as State Provider Connection
tags:
  - 'C#'
  - Redis
date: 2019-04-22 14:20:46
---


## 上一篇提到以Redis當作State Provider
## 這篇介紹如何依據不同環境自動切換 State Provider 連線位置
<!-- More -->

### 本篇利用 ConnectionStrings configuration來做到自動切換連線

* 首先 先設定 ConnectionStrings的config, 可於Web.config中設定, 亦可獨立由專案設定
    設定如下所示
    {% codeblock %}
    <configuration>
        <connectionStrings>
            <add name="Redis" connectionString="127.0.0.1,password=******" />
        </connectionStrings>
    </configuration>
    {% endcodeblock %}

* 接下來回到SessionState中找到redis的設定, 加入connectionStringName, 並且把host, accesskey都刪除
    如下所示
    {% codeblock %}
    <add name="DefaultSessionProvider" 		type="Microsoft.Web.Redis.RedisSessionStateProvider" connectionStringName ="Redis" />
    {% endcodeblock %}

* 這樣Redis State Provider就會依照ConnectionStrings的設定抓取對應的連線字串, 而連線字串可透過Configuration Manager依環境做切換

### 如此設置會依照部屬環境自動切換連線, 打完收工