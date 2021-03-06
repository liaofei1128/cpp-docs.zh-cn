---
title: alignment_of 类
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: d241848edf57fe4876c35e22f1762abf5d6888fa
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302310"
---
# <a name="alignment_of-class"></a>alignment_of 类

获取指定类型的对齐方式。 此结构根据 [alignof](../cpp/alignment-cpp-declarations.md) 来实现。 当你只需查询对齐值时，请直接使用**alignof** 。 需要整数常量时（例如在执行标记调度时），可使用 alignment_of。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>参数

*Ty*\
要查询的类型。

## <a name="remarks"></a>备注

类型查询保存类型*Ty*的对齐方式的值。

## <a name="requirements"></a>需求

**标头：** \<type_traits >

**命名空间：** std

## <a name="see-also"></a>另请参阅

[<type_traits>](../standard-library/type-traits.md)\
[aligned_storage 类](../standard-library/aligned-storage-class.md)
