---
title: complex&lt;float&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<float>
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
ms.openlocfilehash: 7b49e63302ad0c26f393fdfd9dd443c77455a643
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688245"
---
# <a name="complexltfloatgt"></a>complex&lt;float&gt;

描述一个对象，该对象存储两个都为**float**类型的有序对象对，第一个对象表示复数的实部，第二个对象表示复数的虚部。

## <a name="syntax"></a>语法

```cpp
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as class template complex
};
```

### <a name="parameters"></a>参数

*_RealVal* \
正在构造的复数实部的 **float** 类型值。

*_ImagVal* \
正在构造的复数虚部的 **float** 类型值。

*complexNum* \
**Double**或**long double**类型的复数，其实部和虚部用于初始化正在构造的**float**类型的复数。

## <a name="return-value"></a>返回值

**float** 类型的复数。

## <a name="remarks"></a>备注

类型为**float**的复杂类复杂的类模板的显式专用化不同于它所定义的构造函数中的类模板。 从**float**到**double**类型的转换可以是隐式的，但从**float**到**long double**的不太安全转换必须是**显式**的。 使用**显式**转换可排除使用赋值语法启动类型转换。

有关类模板 `complex` 的详细信息，请参阅[Complex 类](../standard-library/complex-class.md)。 有关 `complex` 类模板的成员列表，请参见。

## <a name="example"></a>示例

```cpp
// complex_comp_flt.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <float> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type double
   complex <double> c2double ( 1.0 , 3.0 );
   complex <float> c2float ( c2double );
   cout << "Implicit conversion from type double to type float,"
        << endl << "gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << endl << "gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:"
        << endl << "arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type double to type float,
gives c2float = (1,3)
Explicit conversion from type long double to type float,
gives c3float = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>要求

**标头**：\<complex>

**命名空间:** std

## <a name="see-also"></a>请参阅

[complex 类](../standard-library/complex-class.md)\
[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
