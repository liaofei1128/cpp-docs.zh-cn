---
title: 字符值的范围
ms.date: 11/04/2016
ms.assetid: 15ae9781-ec21-4333-bba8-6d2383bbf7f1
ms.openlocfilehash: 8cb2609aca910056b5243fddc868710581e576e7
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480908"
---
# <a name="range-of-char-values"></a>字符值的范围

ANSI 3.2.1.1：纯 char 的值范围与 signed char或 unsigned char 的值范围是否相同    

所有带符号的字符值的范围都介于 -128 和 127 之间。 所有无符号的字符值的范围介于 0 和 255 之间。

[`/J`](../build/reference/j-default-char-type-is-unsigned.md) 编译器选项将 char 的默认类型从 signed char 更改为 unsigned char    。

## <a name="see-also"></a>请参阅

[字符](../c-language/characters.md)
