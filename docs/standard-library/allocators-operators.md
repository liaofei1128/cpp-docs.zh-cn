---
title: '&lt;allocators&gt; 运算符'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 7bc37e98ed85582cac8fc7ae21e54a6d5da9e06f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364961"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 运算符

这些是分配器中&lt;定义的全局模板运算符函数。&gt; 有关类成员运算符函数，请参阅类文档。

|||
|-|-|
|[操作员！](#op_neq)|[运算符*](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>操作员！

测试指定类的分配器对象之间是否不相等。

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*离开*|要测试是否不相等的其中一个分配器对象。|
|*对*|要测试是否不相等的其中一个分配器对象。|

### <a name="return-value"></a>返回值

如果分配器对象不相等，则为 **true**；如果分配器对象相等，则为 **false**。

### <a name="remarks"></a>备注

模板运算符返回 `!(left == right)`。

## <a name="operator"></a><a name="op_eq_eq"></a>运算符*

测试指定类的分配器对象之间是否相等。

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*离开*|要测试是否相等的其中一个分配器对象。|
|*对*|要测试是否相等的其中一个分配器对象。|

### <a name="return-value"></a>返回值

如果分配器对象相等，则为 **true**；如果分配器对象不相等，则为 **false**。

### <a name="remarks"></a>备注

此模板运算符返回 `left.equals(right)`。

## <a name="see-also"></a>另请参阅

[\<分配器>](../standard-library/allocators-header.md)
