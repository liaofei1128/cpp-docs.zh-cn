---
title: 何时初始化 CWnd 对象
ms.date: 11/04/2016
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
ms.openlocfilehash: aa396ade2e8ab4e1245e161423de7bd5bfafaaf8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405711"
---
# <a name="when-to-initialize-cwnd-objects"></a>何时初始化 CWnd 对象

无法创建你自己的子窗口或调用的构造函数中的任何 Windows API 函数`CWnd`-派生的对象。 这是因为`HWND`为`CWnd`尚未创建对象。 必须完成最特定于 Windows 的初始化，如添加子窗口[OnCreate](../mfc/reference/cwnd-class.md#oncreate)消息处理程序。

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [创建文档框架窗口](../mfc/creating-document-frame-windows.md)

- [文档/视图创建](../mfc/document-view-creation.md)

## <a name="see-also"></a>请参阅

[使用框架窗口](../mfc/using-frame-windows.md)
