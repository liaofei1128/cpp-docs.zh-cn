---
title: DHtmlUrlEventMapEntry 结构
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: c9b58067a9c8b6a71cd22b654a2f82ba0f8bfe36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322730"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry 结构

`DHtmlUrlEventMapEntry`结构提供了多 URL 事件映射支持。

## <a name="syntax"></a>语法

```
struct DHtmlUrlEventMapEntry
{
LPCTSTR szUrl;
const DHtmlEventMapEntry *pEventMap;
};
```

#### <a name="parameters"></a>参数

*szUrl*<br/>
URL。

*pEventMap*<br/>
使用 URL 相关联的事件映射。

## <a name="requirements"></a>要求

**标头：** afxdhtml.h

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
