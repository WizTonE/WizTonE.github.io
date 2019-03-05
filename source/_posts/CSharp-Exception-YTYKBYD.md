---
title: 'C# Exception'
tags:
  - 'C#'
  - Exception
date: 2019-03-05 18:34:49
---


# -- 那些以為知道, 實際上卻不知道的事 --

身為工程師, 在 **必要時** 設置try catch then throw exception是很合理的事
<!-- More -->

但是當 **~~共用~~** 的元件變多之後, 彼此間的try catch轉拋exception就顯得複雜許多

尤其是踩到提供元件的同事 **~~無心~~** 留下的bug時

這時候throw exception指出的位置, 未必是真正錯誤的程式碼

譬如以下程式碼{% asset_img 1.png %}


他指出錯誤的地方會是在行數19, 而不是真正錯誤碼的位置行數25{% asset_img 2.png %}

## 因為 throw ex; 會重置拋出點位置, 導致偵錯不易

此時可採用以下兩種方式取代throw ex;

* **Throw**

    這時候單純throw 機制, {% asset_img 3.png %} 

    便能正確反映出錯誤位置所在
    {% asset_img 4.png %}

---

* **Inner Exception**

    如果要加入客製化錯誤訊息, 可以採用 inner exception,
    {% asset_img 5.png %}

    也可確保拋出點不被重置
    {% asset_img 6.png %}

所以 **不要** 在最外層, 將stack整段印出當作exception log, 完全沒有幫助

## You think you know but you don't
