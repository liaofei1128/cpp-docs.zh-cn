---
title: norm、normf、norml1
ms.date: 04/05/2018
api_name:
- norm
- normf
- norml
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
ms.openlocfilehash: 8deaa07d984a3840c73e594535ffffc9078d4716
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951322"
---
# <a name="norm-normf-norml"></a>norm、normf、norml1

检索复数的平方量值。

## <a name="syntax"></a>语法

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>参数

*z*<br/>
一个复数。

## <a name="return-value"></a>返回值

*Z*的平方量。

## <a name="remarks"></a>备注

由于C++允许重载，因此可以调用采用 **_Fcomplex**或 **_Lcomplex**值的**标准**重载，并返回**float**或**long double**值。 在 C 程序中，"**标准**" 始终采用 **_Dcomplex**值并返回一个**双精度**值。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**标准**、 **normf**、 **norml**|\<complex.h>|\<complex.h>|

**_Fcomplex**、 **_Dcomplex**和 **_Lcomplex**类型分别是特定于 Microsoft 的本机 C99 类型的等效项： **float _Complex**、 **double _Complex**和**long double _Complex**。  有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[按字母顺序的函数参考](crt-alphabetical-function-reference.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
