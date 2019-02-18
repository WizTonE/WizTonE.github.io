---
title: value-type-and-reference-type
date: 2019-02-13 02:27:48
tags:
---


# [C#] Value Type vs Reference Type

## -- 那些以為知道, 實際上卻不知道的事 --

對資深程式員來說, Value Type 跟 Reference Type的差異應該略知一二

但要能完整的解釋其中的差異, 卻沒這麼容易, 下面會舉幾個容易忽略的部份
<!-- More -->
{% blockquote %}

### Value Type 與 Reference Type的判別方式

    最容易判別的方式便是追朔該型別的原始型別

    * struct : Value Type
    * class : Reference Type
{% endblockquote %}

譬如 string 的原始型別是 class, 便是Reference Type
{% asset_img 1.png %}

Int32的原始型別是struct, 便是Value Type
{% asset_img 2.png %}

- - -