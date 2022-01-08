# libbf win

&emsp;&emsp;[libbf](https://bellard.org/libbf/) is an awesome and tiny big float-number library. However, it's only support using GCC to compile.

&emsp;&emsp;This is a core version that can be compiled into DLL using gcc.

## Build

Install a suitable GCC:

```bash
gcc -D_LIBBF_EXPORT -O2 -Wall -ffunction-sections -fdata-sections -flto -MMD -c libbf.c -o libbf.o
gcc -D_LIBBF_EXPORT -O2 -Wall -ffunction-sections -fdata-sections -flto -MMD -c softfp.c -o softfp.o
gcc -D_LIBBF_EXPORT -O2 -Wall -ffunction-sections -fdata-sections -flto -MMD -c cutils.c -o cutils.o
gcc -D_LIBBF_EXPORT -s -Wall -shared -fPIC libbf.o softfp.o cutils.o -o libbf.dll "-Wl,--gc-sections,--output-def,libbf.def,--out-implib,libbf.lib"
```



