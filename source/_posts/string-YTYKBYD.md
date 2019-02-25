---
title: C# String
date: 2019-02-18 23:02:32
tags: [C#, String]
---

# -- 那些以為知道, 實際上卻不知道的事 --

String 一般操作上 與 Value Type類似 但String 為 **Reference Type** 且為 **Immutable Type**

String底層有個**string pool**的設計, 用來紀錄建立過得字串, 以便自動重用以建立過得字串實體, 減少記憶體消耗

<!-- More -->

## Immutable Type

    Immutable Type特性在於每次更改值, 他便會回傳新的實體

    String 之所以設計為Immutable Type, 原因是在於方便程式撰寫用途

譬如{% asset_img 1.png %}

假設 String是mutable type 設計, str1要是改了字串, str2與str3 勢必會跟著變動

如此一來 string使用上沒有這麼便利, 因此需要 immutable type的設計

## String pool

    String pool 會自動重用以建立過得字串實體

譬如{% asset_img 2.png %}

結果會是{% asset_img 3.png %}


綜合上述所說, 以下例子試著回答看看結果

{% asset_img 4.png %}


結果是
{% asset_img 5.png %}


# Link
---
- {% link "[.Net Concept]理解並善用String pool" http://larrynung.github.io/2011/06/30/30763/ %}


- {% link "String is Immutable in C#" https://www.c-sharpcorner.com/UploadFile/b1df45/string-is-immutable-in-C-Sharp/ %}