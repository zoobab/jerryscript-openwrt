# About

This is my frst attempt to make an OpenWRT package for Jerryscript.

# Problems

* Still have to pass build options to not use jerry-libc
* Built with cmake, it does not find strip of the toolchain, ends up with an error like command not found:

```
[ 60%] Linking CXX executable release.linux-mem_stats
/home/zoobab/soft/openwrt/staging_dir/host/bin/cmake -E cmake_link_script CMakeFiles/release.linux-mem_stats.dir/link.txt --verbose=1
/home/zoobab/soft/openwrt/staging_dir/toolchain-arm_cortex-a8+vfpv3_gcc-5.2.0_musl-1.1.12_eabi/bin/arm-openwrt-linux-muslgnueabi-g++   -Os -pipe -march=armv7-a -mtune=cortex-a8 -mfpu=vfpv3-d16 -fno-caller-saves -fno-plt -fhonour-copts -Wno-error=unused-but-set-variable -Wno-error=unused-result -mfloat-abi=hard -iremap /home/zoobab/soft/openwrt/build_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/jerryscript:jerryscript -Wformat -Werror=format-security -fstack-protector -D_FORTIFY_SOURCE=1 -Wl,-z,now -Wl,-z,relro   -DNDEBUG  -L/home/zoobab/soft/openwrt/staging_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/usr/lib -L/home/zoobab/soft/openwrt/staging_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/lib -L/home/zoobab/soft/openwrt/staging_dir/toolchain-arm_cortex-a8+vfpv3_gcc-5.2.0_musl-1.1.12_eabi/usr/lib -L/home/zoobab/soft/openwrt/staging_dir/toolchain-arm_cortex-a8+vfpv3_gcc-5.2.0_musl-1.1.12_eabi/lib -znow -zrelro -fno-builtin -flto -fno-fat-lto-objects -fno-stack-protector -g -gdwarf-4 -Wall -Werror=all -Wextra -Werror=extra -Wformat-nonliteral -Werror=format-nonliteral -Winit-self -Werror=init-self -Wconversion -Werror=conversion -Wsign-conversion -Werror=sign-conversion -Wformat-security -Werror=format-security -Wmissing-declarations -Werror=missing-declarations -pedantic -Wno-stack-protector -Wno-attributes -Wlogical-op -Werror=logical-op -std=c++11 -fno-exceptions -fno-rtti -fno-implicit-templates -fno-implicit-inline-templates -Os -Wl,-z,noexecstack -nostdlib -flto -Xlinker -Map -Xlinker jerry.map  -static CMakeFiles/release.linux-mem_stats.dir/main-unix.cpp.o  -o release.linux-mem_stats  jerry-core/librelease-mem_stats.jerry-core.a jerry-libc/librelease.jerry-libc.linux.lib.a third-party/fdlibm/librelease-mem_stats.jerry-fdlibm.third_party.lib.a /home/zoobab/soft/openwrt/staging_dir/toolchain-arm_cortex-a8+vfpv3_gcc-5.2.0_musl-1.1.12_eabi/lib/gcc/arm-openwrt-linux-muslgnueabi/5.2.0/libgcc.a /home/zoobab/soft/openwrt/staging_dir/toolchain-arm_cortex-a8+vfpv3_gcc-5.2.0_musl-1.1.12_eabi/lib/gcc/arm-openwrt-linux-muslgnueabi/5.2.0/libgcc_eh.a 
./: /home/zoobab/soft/openwrt/build_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/jerryscript/release.linux-mem_stats
make[5]: ./:: Command not found
CMakeFiles/release.linux-mem_stats.dir/build.make:99: recipe for target 'release.linux-mem_stats' failed
make[5]: *** [release.linux-mem_stats] Error 127
make[5]: *** Deleting file 'release.linux-mem_stats'
make[5]: Leaving directory '/home/zoobab/soft/openwrt/build_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/jerryscript'
CMakeFiles/Makefile2:1788: recipe for target 'CMakeFiles/release.linux-mem_stats.dir/all' failed
make[4]: *** [CMakeFiles/release.linux-mem_stats.dir/all] Error 2
make[4]: Leaving directory '/home/zoobab/soft/openwrt/build_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/jerryscript'
Makefile:83: recipe for target 'all' failed
make[3]: *** [all] Error 2
make[3]: Leaving directory '/home/zoobab/soft/openwrt/build_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/jerryscript'
Makefile:73: recipe for target '/home/zoobab/soft/openwrt/build_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/jerryscript/.built' failed
make[2]: *** [/home/zoobab/soft/openwrt/build_dir/target-arm_cortex-a8+vfpv3_musl-1.1.12_eabi/jerryscript/.built] Error 2
make[2]: Leaving directory '/home/zoobab/soft/openwrt/feeds/packages/lang/jerryscript'
package/Makefile:192: recipe for target 'package/feeds/packages/jerryscript/compile' failed
make[1]: *** [package/feeds/packages/jerryscript/compile] Error 2
make[1]: Leaving directory '/home/zoobab/soft/openwrt'
/home/zoobab/soft/openwrt/include/toplevel.mk:192: recipe for target 'package/jerryscript/compile' failed
make: *** [package/jerryscript/compile] Error 2
```

# Usage

Add some usage here.

# Links

* https://github.com/Samsung/jerryscript/pull/822/files
* https://github.com/Samsung/jerryscript/commit/db6caf3c4830c352bc45a9178a43aba909574ba8
* https://github.com/qdk0901/iotjs-openwrt
