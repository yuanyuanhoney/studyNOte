

#### 角度和三角函数



 标识为angle的函数参数假定以弧度为单位。这些函数不可能出现被0除的情况，如果被除数为0，结果是未定义的。

- radian函数是将角度转换为弧度;

- degrees函数是将弧度转换为角度;

- sin, cos, tan都是标准的三角函数;

- asin, acos, atan是反三角函数

  

#### 指数函数

genType有点像面向对象中泛型，即如果genType是float型的，那么genType pow (genType x, genType y)就变成了：float pow (float x, float y)



-  genType pow (genType x, genType y)

​         x的y次方。如果x小于0，结果是未定义的。同样，如果x=0并且y<=0,结果也是未定义的。使用时应特别注意。

- genType exp (genType x)

  e的x次方

- genType log (genType x)

  计算满足x等于e的y次方的y的值。如果x的值小于0，结果是未定义的。

- genType exp2 (genType x)

  计算2的x次方

- genType log2 (genType x)

​         计算满足x等于2的y次方的y的值。如果x的值小于0，结果是未定义的。

- genType sqrt (genType x)

  =计算x的开方。如果x小于0，结果是未定义的

- genType inversesqrt (genType x)

  计算x的开方之一的值，如果x小于等于0，结果是未定义的。



#### 常用函数

- genType abs (genType x)

​			返回x的绝对值

- genType sign (genType x)

  如果x>0，返回1.0；如果x=0，返回0，如果x<0，返回-1.0

- genType floor (genType x)

  返回小于等于x的最大整数值

- genType ceil (genType x)

  返回大于等于x的最小整数值

- genType fract (genType x)

  返回x-floor(x)，即返回x的小数部分

- genType mod (genType x, float y)、genType mod (genType x, genType y)

  返回x – y * floor (x/y)，即求模计算%

- genType min (genType x, genType y)，genType min (genType x, float y)

  返回x和y的值较小的那个值。

- genType max (genType x, genType y)，genType max (genType x, float y)

  返回x和y的值较大的那个值。

- genType clamp (genType x, genType minVal, genType maxVal)、genType clamp (genType x, float minVal, float maxVal)

  clamp翻译为夹具，就叫夹具函数吧，这个函数是什么意思呢？看看解释的意思是：获取x和minVal之间较大的那个值，然后再拿较大的那个值和最后那个最大的值进行比较然后获取较小的那个，意思就明白了，clamp实际上是获得三个参数中大小处在中间的那个值。函数有个说明：如果minVal > minMax的话，函数返回的结果是未定的。也就是说x的值大小没有限制，但是minval的值必须比maxVal小。

- genType mix (genType x, genType y, genType a)、genType mix (genType x, genType y, float a)

  返回线性混合的x和y，如：x⋅(1−a)+y⋅a

- genType step (genType edge, genType x)，genType step (float edge, genType x)

  如果x < edge，返回0.0，否则返回1.0

- genType smoothstep (genType edge0,genType edge1,genType x)，genType smoothstep (float edge0,float edge1,genType x)

  如果x <= edge0，返回0.0 ；如果x >= edge1 返回1.0；如果edge0 < x < edge1，则执行0~1之间的平滑埃尔米特差值。如果edge0 >= edge1，结果是未定义的。

  

#### 向量相关的函数

- bool any(bvec x)

  如果向量x的任何组件为true，则结果返回true。

- bool all(bvec x)

  如果向量x的所有组件均为true，则结果返回true。

- bvec not(bvec x)

  返回向量x的互补矩阵

内建函数基本上可以分为一下三类：

1. 它们使用一些简便的方式提供必要的硬件功能，如材质贴图。这些函数单独通过着色器是无法模拟出来的。

2. 它们展示了一些可以常简单的写入的繁琐操作（clamp， mix等），但是这些操作非常普遍，并且提供直接对硬件的支持。对于编译器来说，将表达式映射到复杂的装配线指令上是非常困难的。

3. 它们提供了对图形硬件的操作，并且在适当时候进行加速。三角函数就是一个很好的例子。

   ​    有些函数名称和常见的C库函数类似，但是它们支持向量的输入和更多的传统标量输入。

   ​    建议应用程序尽量使用内建函数而不是在着色器中实现相同的计算，因为内建函数是经过最大优化的（如，有些内建函数是直接操作硬件的）。

   ​    用户定义的代码可以重载内建函数，但最好不要重新定义它们。

   ​    内建函数的输入参数（和相应的输出的参数）可以是float, vec2, vec3, vec4。对于函数的任何特定应用，实际的类型必须和所有的参数和返回值相同。就像mat，必须为mat2, mat3, mat4.

   ​    参数和返回值的精度修饰符是隐藏的，对于材质函数，返回类型的精度必须和采样器类型匹配。



#### 角度和三角函数



 标识为angle的函数参数假定以弧度为单位。这些函数不可能出现被0除的情况，如果被除数为0，结果是未定义的。

- radian函数是将角度转换为弧度;

- degrees函数是将弧度转换为角度;

- sin, cos, tan都是标准的三角函数;

- asin, acos, atan是反三角函数

  

#### 指数函数

genType有点像面向对象中泛型，即如果genType是float型的，那么genType pow (genType x, genType y)就变成了：float pow (float x, float y)



- pow  genType pow (genType x, genType y)

​         x的y次方。如果x小于0，结果是未定义的。同样，如果x=0并且y<=0,结果也是未定义的。使用时应特别注意。

- genType exp (genType x)

  e的x次方

- genType log (genType x)

  计算满足x等于e的y次方的y的值。如果x的值小于0，结果是未定义的。

- genType exp2 (genType x)

   计算2的x次方

- genType log2 (genType x)

​         计算满足x等于2的y次方的y的值。如果x的值小于0，结果是未定义的。

- genType sqrt (genType x)

   =计算x的开方。如果x小于0，结果是未定义的

- genType inversesqrt (genType x)

   计算x的开方之一的值，如果x小于等于0，结果是未定义的。



#### 常用函数

- genType abs (genType x)

​			返回x的绝对值

- genType sign (genType x)

  如果x>0，返回1.0；如果x=0，返回0，如果x<0，返回-1.0

- genType floor (genType x)

  返回小于等于x的最大整数值

- genType ceil (genType x)

  返回大于等于x的最小整数值

- genType fract (genType x)

  返回x-floor(x)，即返回x的小数部分

- genType mod (genType x, float y)、genType mod (genType x, genType y)

  返回x – y * floor (x/y)，即求模计算%

- genType min (genType x, genType y)，genType min (genType x, float y)

  返回x和y的值较小的那个值。

- genType max (genType x, genType y)，genType max (genType x, float y)

  返回x和y的值较大的那个值。

- genType clamp (genType x, genType minVal, genType maxVal)、genType clamp (genType x, float minVal, float maxVal)

  clamp翻译为夹具，就叫夹具函数吧，这个函数是什么意思呢？看看解释的意思是：获取x和minVal之间较大的那个值，然后再拿较大的那个值和最后那个最大的值进行比较然后获取较小的那个，意思就明白了，clamp实际上是获得三个参数中大小处在中间的那个值。函数有个说明：如果minVal > minMax的话，函数返回的结果是未定的。也就是说x的值大小没有限制，但是minval的值必须比maxVal小。

- genType mix (genType x, genType y, genType a)、genType mix (genType x, genType y, float a)

  返回线性混合的x和y，如：x⋅(1−a)+y⋅a

- genType step (genType edge, genType x)，genType step (float edge, genType x)

  如果x < edge，返回0.0，否则返回1.0

- genType smoothstep (genType edge0,genType edge1,genType x)，genType smoothstep (float edge0,float edge1,genType x)

  如果x <= edge0，返回0.0 ；如果x >= edge1 返回1.0；如果edge0 < x < edge1，则执行0~1之间的平滑埃尔米特差值。如果edge0 >= edge1，结果是未定义的。
  
  

#### 向量相关的函数

- bool any(bvec x)

  如果向量x的任何组件为true，则结果返回true。

- bool all(bvec x)

   如果向量x的所有组件均为true，则结果返回true。

- bvec not(bvec x)

  返回向量x的互补矩阵