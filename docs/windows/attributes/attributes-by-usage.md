---
title: 按用法分的特性
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
ms.openlocfilehash: dcbed019f8cd08ddbf4ab6b4756a59f7fcbabc4b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361335"
---
# <a name="attributes-by-usage"></a>按用法分的特性

本主题根据属性应用C++语言元素列出属性。

如果属性位于不在属性作用域中的元素前面，则属性块将被视为注释。

|特性|描述|
|---------------|-----------------|
|[模块特性](module-attributes.md)|应用于[模块](module-cpp.md)属性。|
|[接口特性](interface-attributes.md)|适用于[__interfaceC++](../../cpp/interface.md)关键字。|
|[类特性](class-attributes.md)|应用于C++关键字。|
|[方法特性](method-attributes.md)|应用于类、类或接口中的方法。|
|[参数属性](parameter-attributes.md)|应用于类或接口中方法的参数。|
|[数据成员特性](data-member-attributes.md)|应用于类、coclass 或接口中的数据成员。|
|[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)|适用于C++关键字。|
|[数组特性](array-attributes.md)|适用于数组或`SAFEARRAY`s。|
|[独立特性](stand-alone-attributes.md)|操作方式更像一行代码，但不对C++关键字进行操作。 独立属性语句需要在行尾使用分号。|
|[自定义属性](custom-attributes-cpp.md)|允许用户扩展元数据。|

## <a name="module-attributes"></a>模块特性

以下属性只能应用于[模块](module-cpp.md)属性。

|特性|描述|
|---------------|-----------------|
|[helpstringdll](helpstringdll.md)|指定用于执行文档字符串查找（本地化）的 DLL 的名称。|

## <a name="interface-attributes"></a>接口特性

以下属性适用于C++关键字的[接口（或__interface）。](../../cpp/interface.md)

|特性|描述|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|指定指示 MIDL 编译器定义 COM 接口的同步和异步版本的 UUID。|
|[自 定义](custom-cpp.md)|允许您定义自己的属性。|
|[不合一](dispinterface.md)|将一个接口作为调度接口置于 .idl 文件中。|
|[双](dual.md)|将接口作为双接口放在 .idl 文件中。|
|[出口](export.md)|导致数据结构放置在 .idl 文件中。|
|[helpcontext](helpcontext.md)|指定一个上下文 ID，允许用户在帮助文件中查看有关此元素的信息。|
|[帮助文件](helpfile.md)|设置类型库的帮助文件的名称。|
|[helpstring](helpstring.md)|指定一个字符串，用于描述应用该字符串的元素。|
|[helpstringcontext](helpstringcontext.md)|指定 .hlp 或 .chm 文件中帮助主题的 ID。|
|[helpstringdll](helpstringdll.md)|指定用于执行文档字符串查找（本地化）的 DLL 的名称。|
|[隐藏](hidden.md)|指示该项目存在，但不应在面向用户的浏览器中显示。|
|[library_block](library-block.md)|将构造放在 .idl 文件的库块中。|
|[local](local-cpp.md)|允许您在接口标头中使用 MIDL 编译器作为标头生成器。 在单个函数中使用时，指定不为其生成存根的本地过程。|
|[nonextensible](nonextensible.md)|指定`IDispatch`实现仅包括接口描述中列出的属性和方法，并且在运行时不能使用其他成员进行扩展。 此属性仅在[双](dual.md)接口上有效。|
|[奥德尔](odl.md)|将接口标识为对象描述语言 （ODL） 接口。|
|[对象](object-cpp.md)|标识自定义接口。|
|[oleautomation](oleautomation.md)|指示接口与自动化兼容。|
|[pointer_default](pointer-default.md)|指定除参数列表中显示的顶级指针之外的所有指针的默认指针属性。|
|[Ptr](ptr.md)|将指针指定为完整指针。|
|[限制](restricted.md)|指定不能任意调用库的成员。|
|[uuid](uuid-cpp-attributes.md)|提供库的唯一 ID|

定义接口时必须遵守以下规则：

- 默认调用约定[__stdcall](../../cpp/stdcall.md)。

- 如果您不提供 GUID，则为您提供 GUID。

- 不允许使用重载方法。

如果不指定[uuid](uuid-cpp-attributes.md)属性并在不同的属性项目中使用相同的接口名称时，将生成相同的 GUID。

## <a name="see-also"></a>另请参阅

[C++ COM 和 .NET 的属性](cpp-attributes-com-net.md)<br/>
[按组分的特性](attributes-by-group.md)<br/>
[按字母顺序的特性参考](attributes-alphabetical-reference.md)
