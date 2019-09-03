---
title: .Net core webapi Secure Connection Failed
tags:
  - .net core
  - 'C#'
date: 2019-09-03 12:42:09
---


# .Net core webapi getting Secure Connection Failed error

If we initial an .net core webapi project but getting Secure Connection Failed error like this.
{% asset_img 01.png %}

We can try some methods below.

- ## Enforce ASP.NET Core HTTPS development certificate on Windows

    If we have certification but not trusted, we can use this method.

    * Open Console
    * type "dotnet ooo-certs https --trust"
    {% asset_img 03.png %}
    * Select yes in the import windows.
    {% asset_img 02.png %}

- ## Opt-out of HTTPS on project creation

    Start a new project without HTTPS

    * Open console.
    * type "dotnet new webapp --no-https" 
    {% asset_img 05.png %}

    * We can create a new project without HTTPS from UI as well.
    {% asset_img 08.png %}

- ## Disable SSL in debug mode.

  If we had choosed the "Configure for HTTPS" but actually we didn't want to use it. We can use this method.

  * Open the project property page.
  * Go to debug tab.
  * Uncheck Enable SSL.
  {% asset_img 07.png %}


### After Settle down the environment. The website should run properly.
  {% asset_img 06.png %}


# Link
---
- {% link "Enforce HTTPS in ASP.NET Core" https://docs.microsoft.com/en-us/aspnet/core/security/enforcing-ssl?view=aspnetcore-2.2&tabs=visual-studio%}

- {% link "讓 .NET Core 的 HttpClientFactory 不驗證 Https 憑證" https://blog.yowko.com/dotnet-core-httpclientfactory-invalid-certificate/%}