---
title: importidl （C++ COM 特性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 6e41a98bef079c92b6df6e7eff203301aa9ceae4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166817"
---
# <a name="importidl"></a>importidl

将指定的 .idl 文件插入生成的 .idl 文件。

## <a name="syntax"></a>语法

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>parameters

*idl_file*<br/>
标识要与将为应用程序生成的 .idl 文件合并的 .idl 文件的名称。

## <a name="remarks"></a>备注

**Importidl** C++属性将库块外的部分（在*idl_file*中）放入程序的生成的 .idl 文件中，并将库部分（在*idl_file*中）放入程序生成的 .idl 文件的库部分。

例如，如果想要在生成的 .idl 文件中使用手编码的 .idl 文件，则可能需要使用**importidl**。

## <a name="example"></a>示例

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
```

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|任何位置|
|**可重复**|否|
|**必需的特性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另请参阅

[编译器特性](compiler-attributes.md)<br/>
[独立特性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
