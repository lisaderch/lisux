![Alt](./doc/manual/logo-mini.png "GLM Logo")

# GLM 1.0.0 Manual

![Alt](./doc/manual/g-truc.png "G-Truc Logo")

---
<div style="page-break-after: always;"> </div>

## Table of Contents

+ [0. Licenses](#section0)
+ [1. Getting started](#section1)
+ [1.1. Using global headers](#section1_1)
+ [1.2. Using separated headers](#section1_2)
+ [1.3. Using extension headers](#section1_3)
+ [1.4. Dependencies](#section1_4)
+ [1.5. Finding GLM with CMake](#section1_5)
+ [2. Preprocessor configurations](#section2)
+ [2.1. GLM\_FORCE\_MESSAGES: Platform auto detection and default configuration](#section2_1)
+ [2.2. GLM\_FORCE\_PLATFORM\_UNKNOWN: Force GLM not to detect the build platform](#section2_2)
+ [2.3. GLM\_FORCE\_COMPILER\_UNKNOWN: Force GLM not to detect the C++ compiler](#section2_3)
+ [2.4. GLM\_FORCE\_ARCH\_UNKNOWN: Force GLM not to detect the build architecture](#section2_4)
+ [2.5. GLM\_FORCE\_CXX\_UNKNOWN: Force GLM not to detect the C++ standard](#section2_5)
+ [2.6. GLM\_FORCE\_CXX**: C++ language detection](#section2_6)
+ [2.7. GLM\_FORCE\_EXPLICIT\_CTOR: Requiring explicit conversions](#section2_7)
+ [2.8. GLM\_FORCE\_INLINE: Force inline](#section2_8)
+ [2.9. GLM\_FORCE\_ALIGNED\_GENTYPES: Force GLM to enable aligned types](#section2_9)
+ [2.10. GLM\_FORCE\_DEFAULT\_ALIGNED\_GENTYPES: Force GLM to use aligned types by default](#section2_10)
+ [2.11. GLM\_FORCE\_INTRINSICS: Using SIMD optimizations](#section2_11)
+ [2.12. GLM\_FORCE\_PRECISION\_**: Default precision](#section2_12)
+ [2.13. GLM\_FORCE\_SINGLE\_ONLY: Removed explicit 64-bits floating point types](#section2_13)
+ [2.14. GLM\_FORCE\_SWIZZLE: Enable swizzle operators](#section2_14)
+ [2.15. GLM\_FORCE\_XYZW\_ONLY: Only exposes x, y, z and w components](#section2_15)
+ [2.16. GLM\_FORCE\_LEFT\_HANDED: Force left handed coordinate system](#section2_16)
+ [2.17. GLM\_FORCE\_DEPTH\_ZERO\_TO\_ONE: Force the use of a clip space between 0 to 1](#section2_17)
+ [2.18. GLM\_FORCE\_SIZE\_T\_LENGTH: Vector and matrix static size type](#section2_18)
+ [2.19. GLM\_FORCE\_UNRESTRICTED\_GENTYPE: Removing genType restriction](#section2_19)
+ [2.20. GLM\_FORCE\_SILENT\_WARNINGS: Silent C++ warnings from language extensions](#section2_20)
+ [2.21. GLM\_FORCE\_QUAT\_DATA\_WXYZ: Force GLM to store quat data as w,x,y,z instead of x,y,z,w](#section2_21)
+ [3. Stable extensions](#section3)
+ [3.1. Scalar types](#section3_1)
+ [3.2. Scalar functions](#section3_2)
+ [3.3. Vector types](#section3_3)
+ [3.4. Vector types with precision qualifiers](#section3_4)
+ [3.5. Vector functions](#section3_5)
+ [3.6. Matrix types](#section3_6)
+ [3.7. Matrix types with precision qualifiers](#section3_7)
+ [3.8. Matrix functions](#section3_8)
+ [3.9. Quaternion types](#section3_9)
+ [3.10. Quaternion types with precision qualifiers](#section3_10)
+ [3.11. Quaternion functions](#section3_11)
+ [4. Recommended extensions](#section4)
+ [4.1. GLM_GTC_bitfield](#section4_1)
+ [4.2. GLM_GTC_color_space](#section4_2)
+ [4.3. GLM_GTC_constants](#section4_3)
+ [4.4. GLM_GTC_epsilon](#section4_4)
+ [4.5. GLM_GTC_integer](#section4_5)
+ [4.6. GLM_GTC_matrix_access](#section4_6)
+ [4.7. GLM_GTC_matrix_integer](#section4_7)
+ [4.8. GLM_GTC_matrix_inverse](#section4_8)
+ [4.9. GLM_GTC_matrix_transform](#section4_9)
+ [4.10. GLM_GTC_noise](#section4_10)
+ [4.11. GLM_GTC_packing](#section4_11)
+ [4.12. GLM_GTC_quaternion](#section4_12)
+ [4.13. GLM_GTC_random](#section4_13)
+ [4.14. GLM_GTC_reciprocal](#section4_14)
+ [4.15. GLM_GTC_round](#section4_15)
+ [4.16. GLM_GTC_type_alignment](#section4_16)
+ [4.17. GLM_GTC_type_precision](#section4_17)
+ [4.18. GLM_GTC_type_ptr](#section4_18)
+ [4.19. GLM_GTC_ulp](#section4_19)
+ [4.20. GLM_GTC_vec1](#section4_20)
+ [5. OpenGL interoperability](#section5)
+ [5.1. GLM Replacements for deprecated OpenGL functions](#section5_1)
+ [5.2. GLM Replacements for GLU functions](#section5_2)
+ [6. Known issues](#section6)
+ [6.1. Not function](#section6_1)
+ [6.2. Precision qualifiers support](#section6_2)
+ [7. FAQ](#section7)
+ [7.1 Why GLM follows GLSL specification and conventions?](#section7_1)
+ [7.2. Does GLM run GLSL programs?](#section7_2)
+ [7.3. Does a GLSL compiler build GLM codes?](#section7_3)
+ [7.4. Should I use 'GTX' extensions?](#section7_4)
+ [7.5. Where can I ask my questions?](#section7_5)
+ [7.6. Where can I find the documentation of extensions?](#section7_6)
+ [7.7. Should I use 'using namespace glm;'?](#section7_7)
+ [7.8. Is GLM fast?](#section7_8)
+ [7.9. When I build with Visual C++ with /w4 warning level, I have warnings...](#section7_9)
+ [7.10. Why some GLM functions can crash because of division by zero?](#section7_10)
+ [7.11. What unit for angles us used in GLM?](#section7_11)
+ [7.12. Windows headers cause build errors...](#section7_12)
+ [7.13. Constant expressions support](#section7_13)
+ [8. Code samples](#section8)
+ [8.1. Compute a triangle normal](#section8_1)
+ [8.2. Matrix transform](#section8_2)
+ [8.3. Vector types](#section8_3)
+ [8.4. Lighting](#section8_4)
+ [9. Contributing to GLM](#section9)
+ [9.1. Submitting bug reports](#section9_1)
+ [9.2. Contributing to GLM with pull request](#section9_2)
+ [9.3. Coding style](#section9_3)
+ [10. References](#section10)
+ [10.1. OpenGL specifications](#section10_1)
+ [10.2. External links](#section10_2)
+ [10.3. Projects using GLM](#section10_3)
+ [10.4. Tutorials using GLM](#section10_4)
+ [10.5. Equivalent for other languages](#section10_5)
+ [10.6. Alternatives to GLM](#section10_6)
+ [10.7. Acknowledgements](#section10_7)

---
<div style="page-break-after: always;"> </div>

## <a name="section0"></a> Licenses

### The Happy Bunny License (Modified MIT License)

Copyright (c) 2005 - G-Truc Creation

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

Restrictions: By making use of the Software for military purposes, you
choose to make a Bunny unhappy.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

![](./doc/manual/frontpage1.png)

### The MIT License

Copyright (c) 2005 - G-Truc Creation

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

![](./doc/manual/frontpage2.png)

---
<div style="page-break-after: always;"> </div>

## <a name="section1"></a> 1. Getting started

### <a name="section1_1"></a> 1.1. Using global headers

GLM is a header-only library, and thus does not need to be compiled. We can use GLM's implementation of GLSL's mathematics functionality by including the `<glm/glm.hpp>` header:

```cpp
#include <glm/glm.hpp>
```

To extend the feature set supported by GLM and keeping the library as close to GLSL as possible, new features are implemented as extensions that can be included through a separate header:

```cpp
// Include all GLM core / GLSL features
#include <glm/glm.hpp> // vec2, vec3, mat4, radians

// Include all GLM extensions
#include <glm/ext.hpp> // perspective, translate, rotate

glm::mat4 transform(glm::vec2 const& Orientation, glm::vec3 const& Translate, glm::vec3 const& Up)
{
    glm::mat4 Proj = glm::perspective(glm::radians(45.f), 1.33f, 0.1f, 10.f);
    glm::mat4 ViewTranslate = glm::translate(glm::mat4(1.f), Translate);
    glm::mat4 ViewRotateX = glm::rotate(ViewTranslate, Orientation.y, Up);
    glm::mat4 View = glm::rotate(ViewRotateX, Orientation.x, Up);
    glm::mat4 Model = glm::mat4(1.0f);
    return Proj * View * Model;
}
```

*Note: Including `<glm/glm.hpp>` and `<glm/ext.hpp>` is convenient but pull a lot of code which will significantly increase build time, particularly if these files are included in all source files. We may prefer to use the approaches described in the two following sections to keep the project build fast.*

### <a name="section1_2"></a> 1.2. Using separated headers

GLM relies on C++ templates heavily, and may significantly increase compilation times for projects that use it. Hence, user projects could only include the features they actually use. Following is the list of all the core features, based on GLSL specification, headers:

```cpp
#include <glm/vec2.hpp>               // vec2, bvec2, dvec2, ivec2 and uvec2
#include <glm/vec3.hpp>               // vec3, bvec3, dvec3, ivec3 and uvec3
#include <glm/vec4.hpp>               // vec4, bvec4, dvec4, ivec4 and uvec4
#include <glm/mat2x2.hpp>             // mat2, dmat2
#include <glm/mat2x3.hpp>             // mat2x3, dmat2x3
#include <glm/mat2x4.hpp>             // mat2x4, dmat2x4
#include <glm/mat3x2.hpp>             // mat3x2, dmat3x2
#include <glm/mat3x3.hpp>             // mat3, dmat3
#include <glm/mat3x4.hpp>             // mat3x4, dmat3x4
#include <glm/mat4x2.hpp>             // mat4x2, dmat4x2
#include <glm/mat4x3.hpp>             // mat4x3, dmat4x3
#include <glm/mat4x4.hpp>             // mat4, dmat4
#include <glm/common.hpp>             // all the GLSL common functions: abs, min, mix, isnan, fma, etc.
#include <glm/exponential.hpp>        // all the GLSL exponential functions: pow, log, exp2, sqrt, etc.
#include <glm/geometric.hpp>          // all the GLSL geometry functions: dot, cross, reflect, etc.
#include <glm/integer.hpp>            // all the GLSL integer functions: findMSB, bitfieldExtract, etc.
#include <glm/matrix.hpp>             // all the GLSL matrix functions: transpose, inverse, etc.
#include <glm/packing.hpp>            // all the GLSL packing functions: packUnorm4x8, unpackHalf2x16, etc.
#include <glm/trigonometric.hpp>      // all the GLSL trigonometric functions: radians, cos, asin, etc.
#include <glm/vector_relational.hpp>  // all the GLSL vector relational functions: equal, less, etc.
```

The following is a code sample using separated core headers and an extension:

```cpp
// Include GLM core features
#include <glm/vec2.hpp>           // vec2
#include <glm/vec3.hpp>           // vec3
#include <glm/mat4x4.hpp>         // mat4
#include <glm/trigonometric.hpp>  //radians

// Include GLM extension
#include <glm/ext/matrix_transform.hpp>     // translate, rotate
#include <glm/ext/matrix_clip_space.hpp>    // perspective

glm::mat4 transform(glm::vec2 const& Orientation, glm::vec3 const& Translate, glm::vec3 const& Up)
{
    glm::mat4 Proj = glm::perspective(glm::radians(45.f), 1.33f, 0.1f, 10.f);
    glm::mat4 ViewTranslate = glm::translate(glm::mat4(1.f), Translate);
    glm::mat4 ViewRotateX = glm::rotate(ViewTranslate, Orientation.y, Up);
    glm::mat4 View = glm::rotate(ViewRotateX, Orientation.x, Up);
    glm::mat4 Model = glm::mat4(1.0f);
    return Proj * View * Model;
}
```

### <a name="section1_3"></a> 1.3. Using extension headers

Using GLM through split headers to minimize the project build time:

```cpp
// Include GLM vector extensions:
#include <glm/ext/vector_float2.hpp>                // vec2
#include <glm/ext/vector_float3.hpp>                // vec3
#include <glm/ext/vector_trigonometric.hpp>         // radians

// Include GLM matrix extensions:
#include <glm/ext/matrix_float4x4.hpp>              // mat4
#include <glm/ext/matrix_transform.hpp>             // translate, rotate
#include <glm/ext/matrix_clip_space.hpp>            // perspective

glm::mat4 transform(glm::vec2 const& Orientation, glm::vec3 const& Translate, glm::vec3 const& Up)
{
    glm::mat4 Proj = glm::perspective(glm::radians(45.f), 1.33f, 0.1f, 10.f);
    glm::mat4 ViewTranslate = glm::translate(glm::mat4(1.f), Translate);
    glm::mat4 ViewRotateX = glm::rotate(ViewTranslate, Orientation.y, Up);
    glm::mat4 View = glm::rotate(ViewRotateX, Orientation.x, Up);
    glm::mat4 Model = glm::mat4(1.0f);
    return Proj * View * Model;
}
```

### <a name="section1_4"></a> 1.4. Dependencies

GLM does not depend on external libraries or headers such as `<GL/gl.h>`, [`<GL/glcorearb.h>`](http://www.opengl.org/registry/api/GL/glcorearb.h), `<GLES3/gl3.h>`, `<GL/glu.h>`, or `<windows.h>`.

### <a name="section1_5"></a> 1.5. Finding GLM with CMake

When installed, GLM provides the CMake package configuration files `glmConfig.cmake` and `glmConfigVersion.cmake`.

To use these configurations files, you may need to set the `glm_DIR` variable to the directory containing the configuration files `<installation prefix>/lib/cmake/glm/`.

Use the `find_package` CMake command to load the configurations into your project. Lastly, either link your executable against the `glm::glm` target or add `${GLM_INCLUDE_DIRS}` to your target's include directories:

```cmake
set(glm_DIR <installation prefix>/lib/cmake/glm) # if necessary
find_package(glm REQUIRED)
target_link_libraries(<your executable> glm::glm)
```

To use GLM as a submodule in a project instead, use `add_subdirectory` to expose the same target, or add the directory to your target's include directories:

```cmake
add_subdirectory(glm)
target_link_libraries(<your executable> glm::glm)
# or
target_include_directories(<your executable> glm)
```

---
<div style="page-break-after: always;"> </div>

## <a name="section2"></a> 2. Preprocessor configurations

### <a name="section2_1"></a> 2.1. GLM\_FORCE\_MESSAGES: Platform auto detection and default configuration

When included, GLM will first automatically detect the compiler used, the C++ standard supported, the compiler arguments used to configure itself matching the build environment.

For example, if the compiler arguments request AVX code generation, GLM will rely on its code path providing AVX optimizations when available.

We can change GLM configuration using specific C++ preprocessor defines that must be declared before including any GLM headers.

Using `GLM_FORCE_MESSAGES`, GLM will report the configuration as part of the build log.

```cpp
#define GLM_FORCE_MESSAGES // Or defined when building (e.g. -DGLM_FORCE_SWIZZLE)
#include <glm/glm.hpp>
```

Example of configuration log generated by `GLM_FORCE_MESSAGES`:

```plaintext
GLM: version 0.9.9.1
GLM: C++ 17 with extensions
GLM: Clang compiler detected
GLM: x86 64 bits with AVX instruction set build target
GLM: Linux platform detected
GLM: GLM_FORCE_SWIZZLE is undefined. swizzling functions or operators are disabled.
GLM: GLM_FORCE_SIZE_T_LENGTH is undefined. .length() returns a glm::length_t, a typedef of int following GLSL.
GLM: GLM_FORCE_UNRESTRICTED_GENTYPE is undefined. Follows strictly GLSL on valid function genTypes.
GLM: GLM_FORCE_DEPTH_ZERO_TO_ONE is undefined. Using negative one to one depth clip space.
GLM: GLM_FORCE_LEFT_HANDED is undefined. Using right handed coordinate system.
```

The following subsections describe each configurations and defines.

### <a name="section2_2"></a> 2.2. GLM\_FORCE\_PLATFORM\_UNKNOWN: Force GLM not to detect the build platform

`GLM_FORCE_PLATFORM_UNKNOWN` prevents GLM from detecting the build platform.

### <a name="section2_3"></a> 2.3. GLM\_FORCE\_COMPILER\_UNKNOWN: Force GLM not to detect the C++ compiler

`GLM_FORCE_COMPILER_UNKNOWN` prevents GLM from detecting the C++ compiler.

### <a name="section2_4"></a> 2.4. GLM\_FORCE\_ARCH\_UNKNOWN: Force GLM not to detect the build architecture

`GLM_FORCE_ARCH_UNKNOWN` prevents GLM from detecting the build target architecture.

### <a name="section2_5"></a> 2.5. GLM\_FORCE\_CXX\_UNKNOWN: Force GLM not to detect the C++ standard

`GLM_FORCE_CXX_UNKNOWN` prevents GLM from detecting the C++ compiler standard support.

### <a name="section2_6"></a> 2.6. GLM\_FORCE\_CXX**: C++ language detection

GLM will automatically take advantage of compilers' language extensions when enabled. To increase cross platform compatibility and to avoid compiler extensions, a programmer can define `GLM_FORCE_CXX17` before
any inclusion of `<glm/glm.hpp>` to restrict the language feature set C++17:

```cpp
#define GLM_FORCE_CXX17
#include <glm/glm.hpp>
```

For C++17 and C++20 equivalent defines are available:

* `GLM_FORCE_CXX17`
* `GLM_FORCE_CXX20`

```cpp
#define GLM_FORCE_CXX11
#include <glm/glm.hpp>

// If the compiler doesn't support C++11, compiler errors will happen.
```

`GLM_FORCE_CXX17` overrides `GLM_FORCE_CXX14`; `GLM_FORCE_CXX14` overrides `GLM_FORCE_CXX11`; and `GLM_FORCE_CXX11` overrides `GLM_FORCE_CXX98` defines.

### <a name="section2_7"></a> 2.7. GLM\_FORCE\_EXPLICIT\_CTOR: Requiring explicit conversions

GLSL supports implicit conversions of vector and matrix types. For example, an ivec4 can be implicitly converted into `vec4`.

Often, this behaviour is not desirable but following the spirit of the library, this is the default behavior in GLM. However, GLM 0.9.6 introduced the define `GLM_FORCE_EXPLICIT_CTOR` to require explicit conversion for GLM types.

```cpp
#include <glm/glm.hpp>

void foo()
{
    glm::ivec4 a;
    ...

    glm::vec4 b(a); // Explicit conversion, OK
    glm::vec4 c = a; // Implicit conversion, OK
    ...
}
```

With `GLM_FORCE_EXPLICIT_CTOR` define, implicit conversions are not allowed:

```cpp
#define GLM_FORCE_EXPLICIT_CTOR
#include <glm/glm.hpp>

void foo()
{
    glm::ivec4 a;
    ...

    glm::vec4 b(a); // Explicit conversion, OK
    glm::vec4 c = a; // Implicit conversion, ERROR
    ...
}
```

### <a name="section2_8"></a> 2.8. GLM\_FORCE\_INLINE: Force inline

To push further the software performance, a programmer can define `GLM_FORCE_INLINE` before any inclusion of `<glm/glm.hpp>` to force the compiler to inline GLM code.

```cpp
#define GLM_FORCE_INLINE
#include <glm/glm.hpp>
```

### <a name="section2_9"></a> 2.9. GLM\_FORCE\_ALIGNED\_GENTYPES: Force GLM to enable aligned types

Every object type has the property called alignment requirement, which is an integer value (of type `std::size_t`, always a power of 2) representing the number of bytes between successive addresses at which objects of this type can be allocated. The alignment requirement of a type can be queried with alignof or `std::alignment_of`. The pointer alignment function `std::align` can be used to obtain a suitably-aligned pointer within some buffer, and `std::aligned_storage` can be used to obtain suitably-aligned storage.

Each object type imposes its alignment requirement on every object of that type; stricter alignment (with larger alignment requirement) can be requested using C++11 `alignas`.

In order to satisfy alignment requirements of all non-static members of a class, padding may be inserted after some of its members.

GLM supports both packed and aligned types. Packed types allow filling data structure without inserting extra padding. Aligned GLM types align addresses based on the size of the value type of a GLM type.

```cpp
#define GLM_FORCE_ALIGNED_GENTYPES
#include <glm/glm.hpp>
#include <glm/gtc/type_aligned.hpp>

typedef glm::aligned_vec4 vec4a;
typedef glm::packed_vec4 vec4p;
```

### <a name="section2_10"></a> 2.10. GLM\_FORCE\_DEFAULT\_ALIGNED\_GENTYPES: Force GLM to use aligned types by default

GLM allows using aligned types by default for vector types using `GLM_FORCE_DEFAULT_ALIGNED_GENTYPES`:

```cpp
#define GLM_FORCE_DEFAULT_ALIGNED_GENTYPES
#include <glm/glm.hpp>

struct MyStruct
{
    glm::vec4 a;
    float b;
    glm::vec3 c;
};

void foo()
{
    printf("MyStruct requires memory padding: %d bytes\n", sizeof(MyStruct));
}

>>> MyStruct requires memory padding: 48 bytes
```

```cpp
#include <glm/glm.hpp>

struct MyStruct
{
    glm::vec4 a;
    float b;
    glm::vec3 c;
};

void foo()
{
    printf("MyStruct is tightly packed: %d bytes\n", sizeof(MyStruct));
}

>>> MyStruct is tightly packed: 32 bytes
```

*Note: GLM SIMD optimizations require the use of aligned types.*

### <a name="section2_11"></a> 2.11. GLM\_FORCE\_INTRINSICS: Using SIMD optimizations

GLM provides some SIMD optimizations based on [compiler intrinsics](https://msdn.microsoft.com/en-us/library/26td21ds.aspx).
These optimizations will be automatically thanks to compiler arguments when `GLM_FORCE_INTRINSICS` is defined before including GLM files.
For example, if a program is compiled with Visual Studio using `/arch:AVX`, GLM will detect this argument and generate code using AVX instructions automatically when available.

It's possible to avoid the instruction set detection by forcing the use of a specific instruction set with one of the following define:
`GLM_FORCE_SSE2`, `GLM_FORCE_SSE3`, `GLM_FORCE_SSSE3`, `GLM_FORCE_SSE41`, `GLM_FORCE_SSE42`, `GLM_FORCE_AVX`, `GLM_FORCE_AVX2` or `GLM_FORCE_AVX512`.

The use of intrinsic functions by GLM implementation can be avoided using the define `GLM_FORCE_PURE` before any inclusion of GLM headers. This can be particularly useful if we want to rely on C++14 `constexpr`.

```cpp
#define GLM_FORCE_PURE
#include <glm/glm.hpp>

static_assert(glm::vec4::length() == 4, "Using GLM C++ 14 constexpr support for compile time tests");

// GLM code will be compiled using pure C++ code without any intrinsics
```

```cpp
#define GLM_FORCE_SIMD_AVX2
#include <glm/glm.hpp>

// If the compiler doesn't support AVX2 intrinsics, compiler errors will happen.
```

Additionally, GLM provides a low level SIMD API in glm/simd directory for users who are really interested in writing fast algorithms.

### <a name="section2_12"></a> 2.12. GLM\_FORCE\_PRECISION\_**: Default precision

C++ does not provide a way to implement GLSL default precision selection (as defined in GLSL 4.10 specification section 4.5.3) with GLSL-like syntax.

```glsl
precision mediump int;
precision highp float;
```

To use the default precision functionality, GLM provides some defines that need to added before any include of `glm.hpp`:

```cpp
#define GLM_FORCE_PRECISION_MEDIUMP_INT
#define GLM_FORCE_PRECISION_HIGHP_FLOAT
#include <glm/glm.hpp>
```

Available defines for floating point types (`glm::vec\*`, `glm::mat\*`):

* `GLM_FORCE_PRECISION_LOWP_FLOAT`: Low precision
* `GLM_FORCE_PRECISION_MEDIUMP_FLOAT`: Medium precision
* `GLM_FORCE_PRECISION_HIGHP_FLOAT`: High precision (default)

Available defines for floating point types (`glm::dvec\*`, `glm::dmat\*`):

* `GLM_FORCE_PRECISION_LOWP_DOUBLE`: Low precision
* `GLM_FORCE_PRECISION_MEDIUMP_DOUBLE`: Medium precision
* `GLM_FORCE_PRECISION_HIGHP_DOUBLE`: High precision (default)

Available defines for signed integer types (`glm::ivec\*`):

* `GLM_FORCE_PRECISION_LOWP_INT`: Low precision
* `GLM_FORCE_PRECISION_MEDIUMP_INT`: Medium precision
* `GLM_FORCE_PRECISION_HIGHP_INT`: High precision (default)

Available defines for unsigned integer types (`glm::uvec\*`):

* `GLM_FORCE_PRECISION_LOWP_UINT`: Low precision
* `GLM_FORCE_PRECISION_MEDIUMP_UINT`: Medium precision
* `GLM_FORCE_PRECISION_HIGHP_UINT`: High precision (default)

### <a name="section2_13"></a> 2.13. GLM\_FORCE\_SINGLE\_ONLY: Removed explicit 64-bits floating point types

Some platforms (Dreamcast) doesn't support double precision floating point values. To compile on such platforms, GCC has the `--m4-single-only` build argument. When defining `GLM_FORCE_SINGLE_ONLY` before including GLM headers, GLM releases the requirement of double precision floating point values support. Effectively, all the float64 types are no longer defined and double behaves like float.

### <a name="section2_14"></a> 2.14. GLM\_FORCE\_SWIZZLE: Enable swizzle operators

Shader languages like GLSL often feature so-called swizzle expressions, which may be used to freely select and arrange a vector's components. For example, `variable.x`, `variable.xzy` and `variable.zxyy` respectively form a scalar, a 3D vector and a 4D vector.  The result of a swizzle expression in GLSL can be either an R-value or an L-value. Swizzle expressions can be written with characters from exactly one of `xyzw` (usually for positions), `rgba` (usually for colors), and `stpq` (usually for texture coordinates).

```glsl
vec4 A;
vec2 B;

B.yx = A.wy;
B = A.xx;
vec3 C = A.bgr;
vec3 D = B.rsz; // Invalid, won't compile
```

GLM supports some of this functionality. Swizzling can be enabled by defining `GLM_FORCE_SWIZZLE`.

*Note: Enabling swizzle expressions will massively increase the size of your binaries and the time it takes to compile them!*

GLM has two levels of swizzling support described in the following subsections.

#### 2.14.1. Swizzle functions for standard C++ 98

When compiling GLM as C++98, R-value swizzle expressions are simulated through member functions of each vector type.

```cpp
#define GLM_FORCE_SWIZZLE // Or defined when building (e.g. -DGLM_FORCE_SWIZZLE)
#include <glm/glm.hpp>

void foo()
{
    glm::vec4 const ColorRGBA = glm::vec4(1.0f, 0.5f, 0.0f, 1.0f);
    glm::vec3 const ColorBGR = ColorRGBA.bgr();

    glm::vec3 const PositionA = glm::vec3(1.0f, 0.5f, 0.0f);
    glm::vec3 const PositionB = PositionA.xyz() * 2.0f;

    glm::vec2 const TexcoordST = glm::vec2(1.0f, 0.5f);
    glm::vec4 const TexcoordSTPQ = TexcoordST.stst();
}
```

Swizzle operators return a **copy** of the component values, and thus *can't* be used as L-values to change a vector's values.

```cpp
#define GLM_FORCE_SWIZZLE
#include <glm/glm.hpp>

void foo()
{
  glm::vec3 const A = glm::vec3(1.0f, 0.5f, 0.0f);

  // No compiler error, but A is not modified.
  // An anonymous copy is being modified (and then discarded).
  A.bgr() = glm::vec3(2.0f, 1.5f, 1.0f); // A is not modified!
}
```

#### 2.14.2. Swizzle operations for C++ 98 with language extensions

Visual C++, GCC and Clang support, as a _non-standard language extension_, anonymous `struct`s as `union` members. This permits a powerful swizzling implementation that both allows L-value swizzle expressions and GLSL-like syntax. To use this feature, the language extension must be enabled by a supporting compiler and `GLM_FORCE_SWIZZLE` must be `#define`d.

```cpp
#define GLM_FORCE_SWIZZLE
#include <glm/glm.hpp>

// Only guaranteed to work with Visual C++!
// Some compilers that support Microsoft extensions may compile this.
void foo()
{
  glm::vec4 ColorRGBA = glm::vec4(1.0f, 0.5f, 0.0f, 1.0f);

  // l-value:
  glm::vec4 ColorBGRA = ColorRGBA.bgra;

  // r-value:
  ColorRGBA.bgra = ColorRGBA;

  // Both l-value and r-value
  ColorRGBA.bgra = ColorRGBA.rgba;
}
```

This version returns implementation-specific objects that _implicitly convert_ to their respective vector types.  As a consequence of this design, these extra types **can't be directly used** as C++ function arguments; they must be converted through constructors or `operator()`.

```cpp
#define GLM_FORCE_SWIZZLE
#include <glm/glm.hpp>

using namespace glm;

void foo()
{
  vec4 Color = vec4(1.0f, 0.5f, 0.0f, 1.0f);

  // Generates compiler errors. Color.rgba is not a vector type.
  vec4 ClampedA = clamp(Color.rgba, 0.f, 1.f); // ERROR

  // Explicit conversion through a constructor
  vec4 ClampedB = clamp(vec4(Color.rgba), 0.f, 1.f); // OK

  // Explicit conversion through operator()
  vec4 ClampedC = clamp(Color.rgba(), 0.f, 1.f); // OK
}
```

*Note: The implementation has a caveat: Swizzle operator types must be different on both size of the equal operator or the operation will fail. There is no known fix for this issue to date.*

### <a name="section2_15"></a> 2.15. GLM\_FORCE\_XYZW\_ONLY: Only exposes x, y, z and w components

Following GLSL specifications, GLM supports three sets of components to access vector types member: x, y, z, w; r, g, b, a; and s, t, p, q.
Also, this is making vector component very expressive in the code, it may make debugging vector types a little cumbersome as the debuggers will typically display three times the value for each component due to the existence of the three sets.

To simplify vector types, GLM allows exposing only x, y, z and w components thanks to `GLM_FORCE_XYZW_ONLY` define.

### <a name="section2_16"></a> 2.16. GLM\_FORCE\_LEFT\_HANDED: Force left handed coordinate system

By default, OpenGL is using a right handed coordinate system. However, others APIs such as Direct3D have done different choice and relies on the left handed coordinate system.

GLM allows switching the coordinate system to left handed by defining `GLM_FORCE_LEFT_HANDED`.

### <a name="section2_17"></a> 2.17. GLM\_FORCE\_DEPTH\_ZERO\_TO\_ONE: Force the use of a clip space between 0 to 1

By default, OpenGL is using a -1 to 1 clip space in Z-axis. However, others APIs such as Direct3D relies on a clip space between 0 to 1 in Z-axis.

GLM allows switching the clip space in Z-axis to 0 to 1 by defining `GLM_FORCE_DEPTH_ZERO_TO_ONE`.

### <a name="section2_18"></a> 2.18. GLM\_FORCE\_SIZE\_T\_LENGTH: Vector and matrix static size

GLSL supports the member function .length() for all vector and matrix types.

```cpp
#include <glm/glm.hpp>

void foo(vec4 const& v)
{
    int Length = v.length();
    ...
}
```

This function returns an `int` however this function typically interacts with STL `size_t` based code. GLM provides `GLM_FORCE_SIZE_T_LENGTH` pre-processor configuration so that member functions `length()` return a `size_t`.

Additionally, GLM defines the type `glm::length_t` to identify `length()` returned type, independently from `GLM_FORCE_SIZE_T_LENGTH`.

```cpp
#define GLM_FORCE_SIZE_T_LENGTH
#include <glm/glm.hpp>

void foo(vec4 const& v)
{
    glm::length_t Length = v.length();
    ...
}
```

### <a name="section2_19"></a> 2.19. GLM\_FORCE\_UNRESTRICTED\_GENTYPE: Removing genType restriction

GLSL has restrictions on types supported by certain functions that may appear excessive.
By default, GLM follows the GLSL specification as accurately as possible however it's possible to relax these rules using `GLM_FORCE_UNRESTRICTED_GENTYPE` define.

```cpp
#include <glm/glm.hpp>

float average(float const A, float const B)
{
    return glm::mix(A, B, 0.5f); // By default glm::mix only supports floating-point types
}
```

By defining GLM\_FORCE\_UNRESTRICTED\_GENTYPE, we allow using integer types:

```cpp
#define GLM_FORCE_UNRESTRICTED_GENTYPE
#include <glm/glm.hpp>

int average(int const A, int const B)
{
    return glm::mix(A, B, 0.5f); // integers are ok thanks to GLM_FORCE_UNRESTRICTED_GENTYPE
}
```

### <a name="section2_20"></a> 2.20. GLM\_FORCE\_SILENT\_WARNINGS: Silent C++ warnings from language extensions

When using /W4 on Visual C++ or -Wpedantic on GCC, for example, the compilers will generate warnings for using C++ language extensions (/Za with Visual C++) such as anonymous struct.
GLM relies on anonymous structs for swizzle operators and aligned vector types. To silent those warnings define `GLM_FORCE_SILENT_WARNINGS` before including GLM headers.

### <a name="section2_21"></a> 2.21. GLM\_FORCE\_QUAT\_DATA\_XYZW: Force GLM to store quat data as x,y,z,w instead of w,x,y,z

By default GLM stores quaternion components with the w, x, y, z order. `GLM_FORCE_QUAT_DATA_XYZW` allows switching the quaternion data storage to the x, y, z, w order.

---
<div style="page-break-after: always;"> </div>

## <a name="section3"></a> 3. Stable extensions

### <a name="section3_1"></a> 3.1. Scalar types

#### 3.1.1. GLM_EXT_scalar_int_sized

This extension exposes sized and signed integer types.

Include `<glm/ext/scalar_int_sized.hpp>` to use these features.

#### 3.1.2. GLM_EXT_scalar_uint_sized

This extension exposes sized and unsigned integer types.

```cpp
#include <glm/ext/scalar_common.hpp>

glm::uint64 pack(glm::uint32 A, glm::uint16 B, glm::uint8 C, glm::uint8 D)
{
	glm::uint64 ShiftA = 0;
	glm::uint64 ShiftB = sizeof(glm::uint32) * 8;
	glm::uint64 ShiftC = (sizeof(glm::uint32) + sizeof(glm::uint16)) * 8;
	glm::uint64 ShiftD = (sizeof(glm::uint32) + sizeof(glm::uint16) + sizeof(glm::uint8)) * 8;
	return (glm::uint64(A) << ShiftA) | (glm::uint64(B) << ShiftB) | (glm::uint64(C) << ShiftC) | (glm::uint64(D) << ShiftD);
}
```

Include `<glm/ext/scalar_uint_sized.hpp>` to use these features.

### <a name="section3_2"></a> 3.2. Scalar functions

#### 3.2.1. GLM_EXT_scalar_common

This extension exposes support for `min` and `max` functions taking more than two scalar arguments. Also, it adds `fmin` and `fmax` variants which prevents `NaN` propagation.

```cpp
#include <glm/ext/scalar_common.hpp>

float positiveMax(float const a, float const b)
{
    return glm::fmax(a, b, 0.0f);
}
```

Include `<glm/ext/scalar_common.hpp>` to use these features.

#### 3.2.2. GLM_EXT_scalar_relational

This extension exposes `equal` and `notEqual` scalar variants which takes an epsilon argument.

```cpp
#include <glm/ext/scalar_relational.hpp>

bool epsilonEqual(float const a, float const b)
{
    float const CustomEpsilon = 0.0001f;
    return glm::equal(a, b, CustomEpsilon);
}
```

Include `<glm/ext/scalar_relational.hpp>` to use these features.

#### 3.2.3. GLM_EXT_scalar_constants

This extension exposes useful constants such as `epsilon` and `pi`.

```cpp
#include <glm/ext/scalar_constants.hpp>

float circumference(float const Diameter)
{
    return glm::pi<float>() * Diameter;
}
```

```cpp
#include <glm/common.hpp> // abs
#include <glm/ext/scalar_constants.hpp> // epsilon

bool equalULP1(float const a, float const b)
{
    return glm::abs(a - b) <= glm::epsilon<float>();
}
```

Include `<glm/ext/scalar_constants.hpp>` to use these features.

#### 3.2.4. GLM_EXT_scalar_ulp

This extension exposes functions that measure accuracy in numeric calculations.

```cpp
#include <glm/ext/scalar_ulp.hpp>

bool test_ulp(float x)
{
    float const a = glm::next_float(x); // return a float a ULP away from the float argument.
    return float_distance(a, x) == 1; // check both float are a single ULP away.
}
```

Include `<glm/ext/scalar_ulp.hpp>` to use these features.

### <a name="section3_3"></a> 3.3. Vector types

#### 3.3.1. GLM_EXT_vector_float1

This extension exposes single-precision floating point vector with 1 component: `vec1`.

Include `<glm/ext/vector_float1.hpp>` to use these features.

#### 3.3.2. GLM_EXT_vector_float2

This extension exposes single-precision floating point vector with 2 components: `vec2`.

Include `<glm/ext/vector_float2.hpp>` to use these features.

#### 3.3.3. GLM_EXT_vector_float3

This extension exposes single-precision floating point vector with 3 components: `vec3`.

Include `<glm/ext/vector_float3.hpp>` to use these features.

#### 3.3.4. GLM_EXT_vector_float4

This extension exposes single-precision floating point vector with 4 components: `vec4`.

Include `<glm/ext/vector_float4.hpp>` to use these features.

#### 3.3.5. GLM_EXT_vector_double1

This extension exposes double-precision floating point vector with 1 component: `dvec1`.

Include `<glm/ext/vector_double1.hpp>` to use these features.

#### 3.3.6. GLM_EXT_vector_double2

This extension exposes double-precision floating point vector with 2 components: `dvec2`.

Include `<glm/ext/vector_double2.hpp>` to use these features.

#### 3.3.7. GLM_EXT_vector_double3

This extension exposes double-precision floating point vector with 3 components: `dvec3`.

Include `<glm/ext/vector_double3.hpp>` to use these features.

#### 3.3.8. GLM_EXT_vector_double4

This extension exposes double-precision floating point vector with 4 components: `dvec4`.

Include `<glm/ext/vector_double4.hpp>` to use these features.

#### 3.3.9. GLM_EXT_vector_int1

This extension exposes signed integer vector with 1 component: `ivec1`.

Include `<glm/ext/vector_int1.hpp>` to use these features.

#### 3.3.10. GLM_EXT_vector_int2

This extension exposes signed integer vector with 2 components: `ivec2`.

Include `<glm/ext/vector_int2.hpp>` to use these features.

#### 3.3.11. GLM_EXT_vector_int3

This extension exposes signed integer vector with 3 components: `ivec3`.

Include `<glm/ext/vector_int3.hpp>` to use these features.

#### 3.3.12. GLM_EXT_vector_int4

This extension exposes signed integer vector with 4 components: `ivec4`.

Include `<glm/ext/vector_int4.hpp>` to use these features.

#### 3.3.13. GLM_EXT_vector_int1

This extension exposes unsigned integer vector with 1 component: `uvec1`.

Include `<glm/ext/vector_uint1.hpp>` to use these features.

#### 3.3.14. GLM_EXT_vector_uint2

This extension exposes unsigned integer vector with 2 components: `uvec2`.

Include `<glm/ext/vector_uint2.hpp>` to use these features.

#### 3.3.15. GLM_EXT_vector_uint3

This extension exposes unsigned integer vector with 3 components: `uvec3`.

Include `<glm/ext/vector_uint3.hpp>` to use these features.

#### 3.3.16. GLM_EXT_vector_uint4

This extension exposes unsigned integer vector with 4 components: `uvec4`.

Include `<glm/ext/vector_uint4.hpp>` to use these features.

#### 3.3.17. GLM_EXT_vector_bool1

This extension exposes boolean vector with 1 component: `bvec1`.

Include `<glm/ext/vector_bool1.hpp>` to use these features.

#### 3.3.18. GLM_EXT_vector_bool2

This extension exposes boolean vector with 2 components: `bvec2`.

Include `<glm/ext/vector_bool2.hpp>` to use these features.

#### 3.3.19. GLM_EXT_vector_bool3

This extension exposes boolean vector with 3 components: `bvec3`.

Include `<glm/ext/vector_bool3.hpp>` to use these features.

#### 3.3.20. GLM_EXT_vector_bool4

This extension exposes boolean vector with 4 components: `bvec4`.

Include `<glm/ext/vector_bool4.hpp>` to use these features.

### <a name="section3_4"></a> 3.4. Vector types with precision qualifiers

#### 3.4.1. GLM_EXT_vector_float1_precision

This extension exposes single-precision floating point vector with 1 component using various precision in term of ULPs: `lowp_vec1`, `mediump_vec1` and `highp_vec1`.

Include `<glm/ext/vector_float1_precision.hpp>` to use these features.

#### 3.4.2. GLM_EXT_vector_float2_precision

This extension exposes single-precision floating point vector with 2 components using various precision in term of ULPs: `lowp_vec2`, `mediump_vec2` and `highp_vec2`.

Include `<glm/ext/vector_float2_precision.hpp>` to use these features.

#### 3.4.3. GLM_EXT_vector_float3_precision

This extension exposes single-precision floating point vector with 3 components using various precision in term of ULPs: `lowp_vec3`, `mediump_vec3` and `highp_vec3`.

Include `<glm/ext/vector_float3_precision.hpp>` to use these features.

#### 3.4.4. GLM_EXT_vector_float4_precision

This extension exposes single-precision floating point vector with 4 components using various precision in term of ULPs: `lowp_vec4`, `mediump_vec4` and `highp_vec4`.

Include `<glm/ext/vector_float4_precision.hpp>` to use these features.

#### 3.4.5. GLM_EXT_vector_double1_precision

This extension exposes double-precision floating point vector with 1 component using various precision in term of ULPs: `lowp_dvec1`, `mediump_dvec1` and `highp_dvec1`.

Include `<glm/ext/vector_double1_precision.hpp>` to use these features.

#### 3.4.6. GLM_EXT_vector_double2_precision

This extension exposes double-precision floating point vector with 2 components using various precision in term of ULPs: `lowp_dvec2`, `mediump_dvec2` and `highp_dvec2`.

Include `<glm/ext/vector_double2_precision.hpp>` to use these features.

#### 3.4.7. GLM_EXT_vector_double3_precision

This extension exposes double-precision floating point vector with 3 components using various precision in term of ULPs: `lowp_dvec3`, `mediump_dvec3` and `highp_dvec3`.

Include `<glm/ext/vector_double3_precision.hpp>` to use these features.

#### 3.4.8. GLM_EXT_vector_double4_precision

This extension exposes double-precision floating point vector with 4 components using various precision in term of ULPs: `lowp_dvec4`, `mediump_dvec4` and `highp_dvec4`.

Include `<glm/ext/vector_double4_precision.hpp>` to use these features.

### <a name="section3_5"></a> 3.5. Vector functions

#### 3.5.1. GLM_EXT_vector_common

This extension exposes support for `min` and `max` functions taking more than two vector arguments. Also, it adds `fmin` and `fmax` variants which prevents `NaN` propagation.

```cpp
#include <glm/ext/vector_float2.hpp> // vec2
#include <glm/ext/vector_common.hpp> // fmax

float positiveMax(float const a, float const b)
{
    return glm::fmax(a, b, 0.0f);
}
```

Include `<glm/ext/vector_common.hpp>` to use these features.

#### 3.5.2. GLM_EXT_vector_relational

This extension exposes `equal` and `notEqual` vector variants which takes an epsilon argument.

```cpp
#include <glm/ext/vector_float2.hpp> // vec2
#include <glm/ext/vector_relational.hpp> // equal, all

bool epsilonEqual(glm::vec2 const& A, glm::vec2 const& B)
{
    float const CustomEpsilon = 0.0001f;
    return glm::all(glm::equal(A, B, CustomEpsilon));
}
```

Include `<glm/ext/vector_relational.hpp>` to use these features.

#### 3.5.3. GLM_EXT_vector_ulp

This extension exposes function that measure of accuracy in numeric calculations.

```cpp
#include <glm/ext/vector_ulp.hpp>
#include <glm/ext/vector_float4.hpp>
#include <glm/ext/vector_int4.hpp>

bool test_ulp(glm::vec4 const& x)
{
    glm::vec4 const a = glm::next_float(x); // return a float a ULP away from the float argument.
    return glm::all(float_distance(a, x) == glm::ivec4(1)); // check both float are a single ULP away.
}
```

Include `<glm/ext/vector_ulp.hpp>` to use these features.

### <a name="section3_6"></a> 3.6. Matrix types

#### 3.6.1. GLM_EXT_matrix_float2x2

This extension exposes single-precision floating point vector with 2 columns by 2 rows: `mat2x2`.

Include `<glm/ext/matrix_float2x2.hpp>` to use these features.

#### 3.6.2. GLM_EXT_matrix_float2x3

This extension exposes single-precision floating point vector with 2 columns by 3 rows: `mat2x3`.

Include `<glm/ext/matrix_float2x3.hpp>` to use these features.

#### 3.6.3. GLM_EXT_matrix_float2x4

This extension exposes single-precision floating point vector with 2 columns by 4 rows: `mat2x4`.

Include `<glm/ext/matrix_float2x4.hpp>` to use these features.

#### 3.6.4. GLM_EXT_matrix_float3x2

This extension exposes single-precision floating point vector with 3 columns by 2 rows: `mat3x2`.

Include `<glm/ext/matrix_float3x2.hpp>` to use these features.

#### 3.6.5. GLM_EXT_matrix_float3x3

This extension exposes single-precision floating point vector with 3 columns by 3 rows: `mat3x3`.

Include `<glm/ext/matrix_float3x3.hpp>` to use these features.

#### 3.6.6. GLM_EXT_matrix_float3x4

This extension exposes single-precision floating point vector with 3 columns by 4 rows: `mat3x4`.

Include `<glm/ext/matrix_float3x4.hpp>` to use these features.

#### 3.6.7. GLM_EXT_matrix_float4x2

This extension exposes single-precision floating point vector with 4 columns by 2 rows: `mat4x2`.

Include `<glm/ext/matrix_float4x2.hpp>` to use these features.

#### 3.6.8. GLM_EXT_matrix_float4x3

This extension exposes single-precision floating point vector with 4 columns by 3 rows: `mat4x3`.

Include `<glm/ext/matrix_float4x3.hpp>` to use these features.

#### 3.6.9. GLM_EXT_matrix_float4x4

This extension exposes single-precision floating point vector with 4 columns by 4 rows: `mat4x4`.

Include `<glm/ext/matrix_float4x4.hpp>` to use these features.

#### 3.6.10. GLM_EXT_matrix_double2x2

This extension exposes double-precision floating point vector with 2 columns by 2 rows: `dmat2x2`.

Include `<glm/ext/matrix_double2x2.hpp>` to use these features.

#### 3.6.11. GLM_EXT_matrix_double2x3

This extension exposes double-precision floating point vector with 2 columns by 3 rows: `dmat2x3`.

Include `<glm/ext/matrix_double2x3.hpp>` to use these features.

#### 3.6.12. GLM_EXT_matrix_double2x4

This extension exposes double-precision floating point vector with 2 columns by 4 rows: `dmat2x4`.

Include `<glm/ext/matrix_double2x4.hpp>` to use these features.

#### 3.6.13. GLM_EXT_matrix_double3x2

This extension exposes double-precision floating point vector with 3 columns by 2 rows: `dmat3x2`.

Include `<glm/ext/matrix_double3x2.hpp>` to use these features.

#### 3.6.14. GLM_EXT_matrix_double3x3

This extension exposes double-precision floating point vector with 3 columns by 3 rows: `dmat3x3`.

Include `<glm/ext/matrix_double3x3.hpp>` to use these features.

#### 3.6.15. GLM_EXT_matrix_double3x4

This extension exposes double-precision floating point vector with 3 columns by 4 rows: `dmat3x4`.

Include `<glm/ext/matrix_double3x4.hpp>` to use these features.

#### 3.6.16. GLM_EXT_matrix_double4x2

This extension exposes double-precision floating point vector with 4 columns by 2 rows: `dmat4x2`.

Include `<glm/ext/matrix_double4x2.hpp>` to use these features.

#### 3.6.17. GLM_EXT_matrix_double4x3

This extension exposes double-precision floating point vector with 4 columns by 3 rows: `dmat4x3`.

Include `<glm/ext/matrix_double4x3.hpp>` to use these features.

#### 3.6.18. GLM_EXT_matrix_double4x4

This extension exposes double-precision floating point vector with 4 columns by 4 rows: `dmat4x4`.

Include `<glm/ext/matrix_double4x4.hpp>` to use these features.

### <a name="section3_7"></a> 3.7. Matrix types with precision qualifiers

#### 3.7.1. GLM_EXT_matrix_float2x2_precision

This extension exposes single-precision floating point vector with 2 columns by 2 rows using various precision in term of ULPs: `lowp_mat2x2`, `mediump_mat2x2` and `highp_mat2x2`.

Include `<glm/ext/matrix_float2x2_precision.hpp>` to use these features.

#### 3.7.2. GLM_EXT_matrix_float2x3_precision

This extension exposes single-precision floating point vector with 2 columns by 3 rows using various precision in term of ULPs: `lowp_mat2x3`, `mediump_mat2x3` and `highp_mat2x3`.

Include `<glm/ext/matrix_float2x3_precision.hpp>` to use these features.

#### 3.7.3. GLM_EXT_matrix_float2x4_precision

This extension exposes single-precision floating point vector with 2 columns by 4 rows using various precision in term of ULPs: `lowp_mat2x4`, `mediump_mat2x4` and `highp_mat2x4`.

Include `<glm/ext/matrix_float2x4_precision.hpp>` to use these features.

#### 3.7.4. GLM_EXT_matrix_float3x2_precision

This extension exposes single-precision floating point vector with 3 columns by 2 rows using various precision in term of ULPs: `lowp_mat3x2`, `mediump_mat3x2` and `highp_mat3x2`.

Include `<glm/ext/matrix_float3x2_precision.hpp>` to use these features.

#### 3.7.5. GLM_EXT_matrix_float3x3_precision

This extension exposes single-precision floating point vector with 3 columns by 3 rows using various precision in term of ULPs: `lowp_mat3x3`, `mediump_mat3x3` and `highp_mat3x3`.

Include `<glm/ext/matrix_float3x3_precision.hpp>` to use these features.

#### 3.7.6. GLM_EXT_matrix_float3x4_precision

This extension exposes single-precision floating point vector with 3 columns by 4 rows using various precision in term of ULPs: `lowp_mat3x4`, `mediump_mat3x4` and `highp_mat3x4`.

Include `<glm/ext/matrix_float3x4_precision.hpp>` to use these features.

#### 3.7.7. GLM_EXT_matrix_float4x2_precision

This extension exposes single-precision floating point vector with 4 columns by 2 rows using various precision in term of ULPs: `lowp_mat4x2`, `mediump_mat4x2` and `highp_mat4x2`.

Include `<glm/ext/matrix_float4x2_precision.hpp>` to use these features.

#### 3.7.8. GLM_EXT_matrix_float4x3_precision

This extension exposes single-precision floating point vector with 4 columns by 3 rows using various precision in term of ULPs: `lowp_mat4x3`, `mediump_mat4x3` and `highp_mat4x3`.

Include `<glm/ext/matrix_float4x3_precision.hpp>` to use these features.

#### 3.7.9. GLM_EXT_matrix_float4x4_precision

This extension exposes single-precision floating point vector with 4 columns by 4 rows using various precision in term of ULPs: `lowp_mat4x4`, `mediump_mat4x4` and `highp_mat4x4`.

Include `<glm/ext/matrix_float4x4_precision.hpp>` to use these features.

#### 3.7.10. GLM_EXT_matrix_double2x2_precision

This extension exposes double-precision floating point vector with 2 columns by 2 rows using various precision in term of ULPs: `lowp_dmat2x2`, `mediump_dmat2x2` and `highp_dmat2x2`.

Include `<glm/ext/matrix_double2x2_precision.hpp>` to use these features.

#### 3.7.11. GLM_EXT_matrix_double2x3_precision

This extension exposes double-precision floating point vector with 2 columns by 3 rows using various precision in term of ULPs: `lowp_dmat2x3`, `mediump_dmat2x3` and `highp_dmat2x3`.

Include `<glm/ext/matrix_double2x3_precision.hpp>` to use these features.

#### 3.7.12. GLM_EXT_matrix_double2x4_precision

This extension exposes double-precision floating point vector with 2 columns by 4 rows using various precision in term of ULPs: `lowp_dmat2x4`, `mediump_dmat2x4` and `highp_dmat2x4`.

Include `<glm/ext/matrix_double2x4_precision.hpp>` to use these features.

#### 3.7.13. GLM_EXT_matrix_double3x2_precision

This extension exposes double-precision floating point vector with 3 columns by 2 rows using various precision in term of ULPs: `lowp_dmat3x2`, `mediump_dmat3x2` and `highp_dmat3x2`.

Include `<glm/ext/matrix_double3x2_precision.hpp>` to use these features.

#### 3.7.14. GLM_EXT_matrix_double3x3_precision

This extension exposes double-precision floating point vector with 3 columns by 3 rows using various precision in term of ULPs: `lowp_dmat3x3`, `mediump_dmat3x3` and `highp_dmat3x3`.

Include `<glm/ext/matrix_double3x3_precision.hpp>` to use these features.

#### 3.7.15. GLM_EXT_matrix_double3x4_precision

This extension exposes double-precision floating point vector with 3 columns by 4 rows using various precision in term of ULPs: `lowp_dmat3x4`, `mediump_dmat3x4` and `highp_dmat3x4`.

Include `<glm/ext/matrix_double3x4_precision.hpp>` to use these features.

#### 3.7.16. GLM_EXT_matrix_double4x2_precision

This extension exposes double-precision floating point vector with 4 columns by 2 rows using various precision in term of ULPs: `lowp_dmat4x2`, `mediump_dmat4x2` and `highp_dmat4x2`.

Include `<glm/ext/matrix_double4x2_precision.hpp>` to use these features.

#### 3.7.17. GLM_EXT_matrix_double4x3_precision

This extension exposes double-precision floating point vector with 4 columns by 3 rows using various precision in term of ULPs: `lowp_dmat4x3`, `mediump_dmat4x3` and `highp_dmat4x3`.

Include `<glm/ext/matrix_double4x3_precision.hpp>` to use these features.

#### 3.7.18. GLM_EXT_matrix_double4x4_precision

This extension exposes double-precision floating point vector with 4 columns by 4 rows using various precision in term of ULPs: `lowp_dmat4x4`, `mediump_dmat4x4` and `highp_dmat4x4`.

Include `<glm/ext/matrix_double4x4_precision.hpp>` to use these features.

### <a name="section3_8"></a> 3.8. Matrix functions
