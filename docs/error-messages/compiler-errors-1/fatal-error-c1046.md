---
title: 错误 C1046
ms.date: 11/04/2016
f1_keywords:
- C1046
helpviewer_keywords:
- C1046
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
ms.openlocfilehash: e8b3a7fdb5e34d32495a182aed198cf781410f0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204524"
---
# <a name="fatal-error-c1046"></a>错误 C1046

编译器限制：结构嵌套太深

结构、联合或类超出了15个级别的嵌套限制。 重写定义以降低嵌套级别。 通过使用 `typedef` 来定义一个或多个嵌套结构，将结构、联合或类拆分为两个或多个部分。
