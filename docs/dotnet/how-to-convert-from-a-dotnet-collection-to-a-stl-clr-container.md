---
title: 如何：从 .NET 集合转换为 STL/CLR 容器
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
ms.openlocfilehash: 156b4162f742915939ebdfaec6a84d77afaad8cd
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545047"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>如何：从 .NET 集合转换为 STL/CLR 容器

本主题演示如何将 .NET 集合转换为其等效的 STL/CLR 容器。 作为示例，我们演示了如何将 .NET <xref:System.Collections.Generic.List%601> 转换为 STL/CLR[向量](../dotnet/vector-stl-clr.md)，以及如何将 .net <xref:System.Collections.Generic.Dictionary%602> 转换为 STL/clr[映射](../dotnet/map-stl-clr.md)，但该过程对于所有集合和容器都是类似的。

### <a name="to-create-a-container-from-a-collection"></a>从集合创建容器

1. 若要转换整个集合，请创建 STL/CLR 容器并将集合传递给构造函数。

   第一个示例演示了此过程。

\- 或 -

1. 通过创建[collection_adapter](../dotnet/collection-adapter-stl-clr.md)对象来创建泛型 STL/CLR 容器。 此模板类以 .NET 集合接口为参数。 若要验证支持的接口，请参阅[collection_adapter （STL/CLR）](../dotnet/collection-adapter-stl-clr.md)。

1. 将 .NET 集合的内容复制到容器中。 这可以通过使用 STL/CLR[算法](../dotnet/algorithm-stl-clr.md)，或循环访问 .net 集合并将每个元素的副本插入到 STL/clr 容器来完成。

   第二个示例演示了此过程。

## <a name="example"></a>示例

在此示例中，我们将创建一个通用 <xref:System.Collections.Generic.List%601>，并向其中添加5个元素。 然后，使用采用 <xref:System.Collections.Generic.IEnumerable%601> 作为参数的构造函数创建 `vector`。

```cpp
// cliext_convert_list_to_vector.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/vector>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    List<int> ^primeNumbersColl = gcnew List<int>();
    primeNumbersColl->Add(2);
    primeNumbersColl->Add(3);
    primeNumbersColl->Add(5);
    primeNumbersColl->Add(7);
    primeNumbersColl->Add(11);

    cliext::vector<int> ^primeNumbersCont =
        gcnew cliext::vector<int>(primeNumbersColl);

    Console::WriteLine("The contents of the cliext::vector are:");
    cliext::vector<int>::const_iterator it;
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)
    {
        Console::WriteLine(*it);
    }
}
```

```Output
The contents of the cliext::vector are:
2
3
5
7
11
```

## <a name="example"></a>示例

在此示例中，我们将创建一个通用 <xref:System.Collections.Generic.Dictionary%602>，并向其中添加5个元素。 接下来，我们创建一个 `collection_adapter` 将 <xref:System.Collections.Generic.Dictionary%602> 包装为一个简单的 STL/CLR 容器。 最后，我们创建一个 `map`，并通过循环访问 `collection_adapter`将 <xref:System.Collections.Generic.Dictionary%602> 的内容复制到 `map` 中。 在此过程中，我们将使用 `make_pair` 函数创建新对，并将新对直接插入 `map`。

```cpp
// cliext_convert_dictionary_to_map.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/map>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    System::Collections::Generic::Dictionary<float, int> ^dict =
        gcnew System::Collections::Generic::Dictionary<float, int>();
    dict->Add(42.0, 42);
    dict->Add(13.0, 13);
    dict->Add(74.0, 74);
    dict->Add(22.0, 22);
    dict->Add(0.0, 0);

    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);
    cliext::map<float, int> aMap;
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)
    {
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);
        aMap.insert(aPair);
    }

    Console::WriteLine("The contents of the cliext::map are:");
    cliext::map<float, int>::const_iterator it;
    for (it = aMap.begin(); it != aMap.end(); it++)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);
    }
}
```

```Output
The contents of the cliext::map are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>另请参阅

[STL/CLR 库参考](../dotnet/stl-clr-library-reference.md)<br/>
[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)<br/>
[如何：从 STL/CLR 容器转换为 .NET 集合](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)
