---
title: boxing-unboxing
date: 2019-02-14 09:15:42
tags:
---


# [C#] Boxing & Unboxing

## -- 那些以為知道, 實際上卻不知道的事 --

{% blockquote %}

### Boxing, Unboxing

    簡單來說
    * Boxing : Value Type -> Object
    * Unboxing : Object -> Value Type
{% endblockquote %}
<!-- More -->
舉個例子
Boxing:
{% asset_img 3.png %}

Unboxing:
{% asset_img 4.png %}


>其中Boxing前的 valueTypeI 記憶體位置與 
>
>Unboxing後的 unBoxingValueTypeJ記憶體位置會不相同, 這是因為Value Type的因素

有了以上的概念, 我們可以來挑戰一下以下幾種情形會有什麼結果
{% asset_img 5.png %}

答案是:
{% asset_img 6.png %}

    解題:
    objA == objB 比的是reference
    objA.Equals(objB)比的是值
- - -

另一題比較有挑戰性
{% asset_img 7.png %}

答案是:
{% asset_img 8.png %}

    解題:
    第一次(Counter)project.counter Unboxing後的ValueType記憶體位置與
    第二次(Counter)project.counter Unboxing後的記憶體位置不同
    所以第一次Increase()的結果不可能帶到第二次 Unboxing後的記憶體位置
    所以才會是這個結果

你答對了嗎?