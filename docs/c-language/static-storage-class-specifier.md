---
title: 静态存储类说明符
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: ef85ee4d757cb9579431427fba7b46a0e5ac905f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157937"
---
# <a name="static-storage-class-specifier"></a>静态存储类说明符

使用 **static** 存储类说明符在内部级别声明的变量具有全局生存期，但它仅在声明它的块中可见。 对于常量字符串，使用 **static** 会很有用，因为它减少了频繁初始化经常调用的函数的开销。

## <a name="remarks"></a>备注

如果不显式初始化 **static** 变量，则默认情况下它将初始化为 0。 在函数内，**static** 会导致存储被分配并用作定义。 内部静态变量仅提供对单个函数可见的私有永久存储。

## <a name="see-also"></a>请参阅

[C 存储类](c-storage-classes.md)<br/>
[存储类 (C++)](../cpp/storage-classes-cpp.md)
