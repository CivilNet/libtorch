# libtorch
build libtorch for various platform.

一些平台的预编译库我会放到该项目的release页面下。

# Build libtorch AAR for Android
请访问：[使用PyTorch 1.6 for Android](https://zhuanlan.zhihu.com/p/299736532)

# Build libtorch for iOS

# Build libtorch static library for x86 Linux.

# Build libtorch shared library for x86 Linux.

# Build libtorch static library for ARM Linux.


# Removing unused functions and dead code to reduce binary size
The operation of eliminating the unused code and data from the final executable is directly performed by the linker.

In order to do this, it has to work with objects compiled with the following options: `-ffunction-sections' `-fdata-sections'.

These options are usable with C and Ada files. They will place respectively each function or data in a separate section in the resulting object file.

Once the objects and static libraries are created with these options, the linker can perform the dead code elimination. You can do this by setting the `-Wl,–gc-sections' option to gcc command or in the `-largs' section of `gnatmake'. This will perform a garbage collection of code and data never referenced.

- -Wl,-static:
Link against static libraries. Required for dead-code elimination.
- -fvtable-gc:
C++ virtual method table instrumented with garbage collection information for the linker.
- -fdata-sections:
Keeps data in separate data sections, so they can be discarded if unused.
- -ffunction-sections:
Keeps funcitons in separate data sections, so they can be discarded if unused.
- -Wl,–gc-sections:
Tell the linker to garbage collect and discard unused sections.
- -s:
Strip the debug information, so as to make the code as small as possible.


