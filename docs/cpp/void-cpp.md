---
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: 2de019f908942a58b232877fcd9eebc4689d8e22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187474"
---
# <a name="void-c"></a>void (C++)

当用作函数返回类型时， **void**关键字指定函数不返回值。 用于函数的参数列表时， **void**指定该函数不采用任何参数。 当在指针的声明中使用 void 时， **void**指定指针为 "通用"。

如果指针的类型为**void\*** ，指针可以指向未使用**const**或**volatile**关键字声明的任何变量。 不能取消引用**void\*** 指针，除非它被强制转换为另一种类型。 **Void\*** 指针可以转换为任何其他类型的数据指针。

**Void**指针可以指向函数，但不能指向中C++的类成员。

不能声明**void**类型的变量。

## <a name="example"></a>示例

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>另请参阅

[关键字](../cpp/keywords-cpp.md)<br/>
[内置类型](../cpp/fundamental-types-cpp.md)
