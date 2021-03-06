---
title: 编译器警告 C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: f74c115a3cabb421ba5a9cf4c34696a0c223512e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165270"
---
# <a name="compiler-warning-c4394"></a>编译器警告 C4394

"function"：不应将每个 appdomain 符号标记 __declspec （dllexport）

使用[appdomain](../../cpp/appdomain.md)`__declspec` 修饰符标记的函数编译为 MSIL （而不是本机），并且托管函数不支持导出表（[export](../../windows/export.md)`__declspec` 修饰符）。

您可以将托管函数声明为具有公共可访问性。 有关详细信息，请参阅[类型可见性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)和[成员可见性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)。

C4394 始终作为错误发出。  你可以通过 `#pragma warning` 或 **/wd**关闭此警告;有关详细信息，请参阅[警告](../../preprocessor/warning.md)或[/w、/W0、/W1、/W2、/W3、/W4、/W1、/W2、/W3、/W4、/Wall、/wd、/we、/wo、/Wv、/Wx （警告等级）](../../build/reference/compiler-option-warning-level.md) 。

## <a name="example"></a>示例

下面的示例生成 C4394。

```cpp
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```
