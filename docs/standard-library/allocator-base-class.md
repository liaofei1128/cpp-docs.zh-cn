---
title: allocator_base 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
helpviewer_keywords:
- stdext::allocator_base [C++]
- stdext::allocators [C++], allocator_base
- stdext::allocator_base [C++], const_pointer
- stdext::allocator_base [C++], const_reference
- stdext::allocator_base [C++], difference_type
- stdext::allocator_base [C++], pointer
- stdext::allocator_base [C++], reference
- stdext::allocator_base [C++], size_type
- stdext::allocator_base [C++], value_type
- stdext::allocator_base [C++], _Charalloc
- stdext::allocator_base [C++], _Chardealloc
- stdext::allocator_base [C++], address
- stdext::allocator_base [C++], allocate
- stdext::allocator_base [C++], construct
- stdext::allocator_base [C++], deallocate
- stdext::allocator_base [C++], destroy
- stdext::allocator_base [C++], max_size
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
ms.openlocfilehash: f93c8ff53452fc98415e194966960254e7b44143
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364987"
---
# <a name="allocator_base-class"></a>allocator_base 类

定义基类和常用函数需要从同步筛选器创建一个用户定义的分配器。

## <a name="syntax"></a>语法

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*Type*|由分配器分配元素类型。|
|*同步*|分配器的同步策略有 [sync_none 类](../standard-library/sync-none-class.md)、[sync_per_container 类](../standard-library/sync-per-container-class.md)、[sync_per_thread 类](../standard-library/sync-per-thread-class.md)或 [sync_shared 类](../standard-library/sync-shared-class.md)。|

### <a name="constructors"></a>构造函数

|构造函数|说明|
|-|-|
|[allocator_base](#allocator_base)|构造 `allocator_base` 类型的对象。|

### <a name="typedefs"></a>Typedef

|类型名称|说明|
|-|-|
|[const_pointer](#const_pointer)|提供指向由分配器管理的对象类型的常量指针的类型。|
|[const_reference](#const_reference)|提供对由分配器管理的对象类型的常量引用的类型。|
|[difference_type](#difference_type)|有符号的整型，可以表示指向由分配器管理的对象类型的指针值之间的差异。|
|[指针 (pointer)](#pointer)|提供指向由分配器管理的对象类型的指针的类型。|
|[参考](#reference)|提供指向对分配器管理的对象类型的引用的类型。|
|[size_type](#size_type)|一种未签名的积分类型，可以表示类型`allocator_base`对象可以分配的任何序列的长度。|
|[value_type](#value_type)|由分配器管理的类型。|

### <a name="member-functions"></a>成员职能

|成员函数|说明|
|-|-|
|[_Charalloc](#charalloc)|为**类型字符**的数组分配存储。|
|[_Chardealloc](#chardealloc)|释放包含**字符**类型元素的数组的存储。|
|[地址](#address)|查找指定了其值的对象的地址。|
|[分配](#allocate)|分配大小足以存储至少某个指定数量的元素的内存块。|
|[构建](#construct)|在使用指定值初始化的指定地址处构造特定类型的对象。|
|[去分配](#deallocate)|从指定位置开始从存储中释放指定数量的的对象。|
|[摧毁](#destroy)|调用对象析构函数而不释放存储对象的内存。|
|[max_size](#max_size)|在可用内存用完之前，返回可以由类分配器的对象分配的类型 *Type* 的元素数。|

## <a name="requirements"></a>要求

**标头：** \<allocators>

**命名空间：** stdext

## <a name="allocator_base_charalloc"></a><a name="charalloc"></a>allocator_base：_Charalloc

为**类型字符**的数组分配存储。

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*count*|数组中要分配的元素数目。|

### <a name="return-value"></a>返回值

指向已分配对象的指针。

### <a name="remarks"></a>备注

在使用无法编译重新绑定的编译器进行编译时，容器使用此成员函数。 它通过返回调用同步筛选器的 `allocate` 函数的结果来为用户定义的分配器实现 `_Charalloc`。

## <a name="allocator_base_chardealloc"></a><a name="chardealloc"></a>allocator_base：：_Chardealloc

释放包含**字符**类型元素的数组的存储。

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*Ptr*|指向要从存储中释放的第一个对象的指针。|
|*count*|要从存储中释放的对象数量。|

### <a name="remarks"></a>备注

在使用无法编译重新绑定的编译器进行编译时，容器使用此成员函数。 它通过调用同步筛选器的 `deallocate` 函数来为用户定义的分配器实现 `_Chardealloc`。 指针 ptr 必须由分配器对象调用 `_Charalloc` 在较早时间返回，分配器对象应与 `*this`（分配具有同一大小和类型的数组对象）相等。 `_Chardealloc` 绝不会引发异常。

## <a name="allocator_baseaddress"></a><a name="address"></a>allocator_base：地址

查找指定了其值的对象的地址。

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>参数

*瓦尔*\
要搜索其地址的对象的常量或非常量值。

### <a name="return-value"></a>返回值

指向所找到的各自常量或非常量值的对象的常量或非常量指针。

### <a name="remarks"></a>备注

通过返回 `&val` 为用户定义的分配器执行此成员函数。

## <a name="allocator_baseallocate"></a><a name="allocate"></a>allocator_base：：分配

分配大小足以存储至少某个指定数量的元素的内存块。

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*_Nx*|数组中要分配的元素数目。|
|*_Hint*|该参数将被忽略。|

### <a name="return-value"></a>返回值

指向已分配对象的指针。

### <a name="remarks"></a>备注

成员函数为用户定义的分配器实现内存分配，其方法是通过返回调用同步筛选器类型 Type `*` if `_Nx == 1` 的 `allocate` 函数的结果，否则，则通过返回调用 `operator new(_Nx * sizeof(Type))` 强制转换为类型 Type `*` 的结果。

## <a name="allocator_baseallocator_base"></a><a name="allocator_base"></a>allocator_base：allocator_base

构造 `allocator_base` 类型的对象。

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*对*|要复制的分配器对象。|

### <a name="remarks"></a>备注

第一个构造函数构造 [allocator_base](../standard-library/allocator-base-class.md) 实例。 第二个构造函数构造 `allocator_base` 实例，从而对任何 `allocator_base<Type, _Sync>` 实例 `a`，`allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a`。

## <a name="allocator_baseconst_pointer"></a><a name="const_pointer"></a>allocator_base：：const_pointer

提供指向由分配器管理的对象类型的常量指针的类型。

```cpp
typedef const Type *const_pointer;
```

## <a name="allocator_baseconst_reference"></a><a name="const_reference"></a>allocator_base：const_reference

提供对由分配器管理的对象类型的常量引用的类型。

```cpp
typedef const Type& const_reference;
```

## <a name="allocator_baseconstruct"></a><a name="construct"></a>allocator_base：构造

在使用指定值初始化的指定地址处构造特定类型的对象。

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*Ptr*|指向要构造对象的位置的指针。|
|*瓦尔*|要进行初始化的要构造的对象的值。|

### <a name="remarks"></a>备注

通过调用 `new((void*)ptr Type(val)` 为用户定义的分配器执行此成员函数。

## <a name="allocator_basedeallocate"></a><a name="deallocate"></a>allocator_base：:d分配

从指定位置开始从存储中释放指定数量的的对象。

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*Ptr*|指向要从存储中释放的第一个对象的指针。|
|*_Nx*|要从存储中释放的对象数量。|

### <a name="remarks"></a>备注

通过调用同步筛选器 `Sync` if `_Nx == 1` 上的 `deallocate(ptr)` 为用户定义的分配器执行此成员函数，否则，调用 `operator delete(_Nx * ptr)`。

## <a name="allocator_basedestroy"></a><a name="destroy"></a>allocator_base：:d

调用对象析构函数而不释放存储对象的内存。

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>参数

|参数|说明|
|---------------|-----------------|
|*Ptr*|指定要销毁的对象的地址的指针。|

### <a name="remarks"></a>备注

通过调用 `ptr->~Type()` 为用户定义的分配器执行此成员函数。

## <a name="allocator_basedifference_type"></a><a name="difference_type"></a>allocator_base：:d

有符号的整型，可以表示指向由分配器管理的对象类型的指针值之间的差异。

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="allocator_basemax_size"></a><a name="max_size"></a>allocator_base：：max_size

在可用内存用完之前，返回可以由类分配器的对象分配的类型 `Type` 的元素数。

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>返回值

可分配的元素数量。

### <a name="remarks"></a>备注

如果 `0 < (size_t)-1 / sizeof(Type)`，则通过返回 `(size_t)-1 / sizeof(Type)` 为用户定义的分配器执行此成员函数，否则 `1`。

## <a name="allocator_basepointer"></a><a name="pointer"></a>allocator_base：:p奥米特

提供指向由分配器管理的对象类型的指针的类型。

```cpp
typedef Type *pointer;
```

## <a name="allocator_basereference"></a><a name="reference"></a>allocator_base：参考

提供指向对分配器管理的对象类型的引用的类型。

```cpp
typedef Type& reference;
```

## <a name="allocator_basesize_type"></a><a name="size_type"></a>allocator_base：size_type

一种未签名的积分类型，可以表示类型`allocator_base`对象可以分配的任何序列的长度。

```cpp
typedef std::size_t size_type;
```

## <a name="allocator_basevalue_type"></a><a name="value_type"></a>allocator_base：value_type

由分配器管理的类型。

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>另请参阅

[\<分配器>](../standard-library/allocators-header.md)
