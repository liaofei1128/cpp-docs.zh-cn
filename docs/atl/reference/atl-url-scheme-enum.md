---
title: ATL_URL_SCHEME 枚举
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 6d8307d6ea51c5ec7e63735360b8628a4c1ed782
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168574"
---
# <a name="atl_url_scheme"></a>ATL_URL_SCHEME

此枚举的成员为[曲线](curl-class.md)理解的方案提供常数。

## <a name="syntax"></a>语法

```cpp
enum ATL_URL_SCHEME{
   ATL_URL_SCHEME_UNKNOWN = -1,
   ATL_URL_SCHEME_FTP     = 0,
   ATL_URL_SCHEME_GOPHER  = 1,
   ATL_URL_SCHEME_HTTP    = 2,
   ATL_URL_SCHEME_HTTPS   = 3,
   ATL_URL_SCHEME_FILE    = 4,
   ATL_URL_SCHEME_NEWS    = 5,
   ATL_URL_SCHEME_MAILTO  = 6,
   ATL_URL_SCHEME_SOCKS   = 7
};
```

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="see-also"></a>另请参阅

[概念](../active-template-library-atl-concepts.md)<br/>
[卷曲：： SetScheme](curl-class.md#setscheme)<br/>
[卷曲：： GetScheme](curl-class.md#getscheme)
