### How to build [libjpeg-turbo](https://github.com/libjpeg-turbo/libjpeg-turbo)

First, `mkdir build && cd build` then you can run `cmake`. Once you run cmake, open the generated solution (.sln), then build the `INSTALL` project to install the DLLs to your machine.

1. UWP x64

Let's first break down these arguments before copy/pasting other configurations.

cmake<br>
-G "Visual Studio 17 2022" <b>## Visual Studio Version</b><br> 
-A x64 <b>## Architecture</b><br>
-DCMAKE_BUILD_TYPE=Release <b>## Configuration</b><br> 
-DCMAKE_MSVC_RUNTIME_LIBRARY=MultiThreadedDLL<br>
-DCMAKE_SYSTEM_PROCESSOR=x64<br>
-DNEON_INTRINSICS=1<br>
-DBUILD_SHARED_LIBS=ON<br>
-DWITH_CRT_DLL=1<br>
<b>### START UWP ONLY ###</b><br>
-DCMAKE_SYSTEM_NAME=WindowsStore<br> -DCMAKE_SYSTEM_VERSION=10.0<br>
<b>### END UWP ONLY ###</b><br>
.. <b>## Go back one directory</b>

Copy the following command into your terminal:\
`cmake -G "Visual Studio 17 2022" -A x64 -DCMAKE_BUILD_TYPE=Release -DCMAKE_SYSTEM_NAME=WindowsStore -DCMAKE_SYSTEM_VERSION=10.0 -DCMAKE_MSVC_RUNTIME_LIBRARY=MultiThreadedDLL -DCMAKE_SYSTEM_PROCESSOR=x64 -DNEON_INTRINSICS=1 -DBUILD_SHARED_LIBS=ON -DWITH_CRT_DLL=1 ..`

2. UWP ARM

`cmake
-G "Visual Studio 17 2022"
-A ARM
-DCMAKE_BUILD_TYPE=Release
-DCMAKE_SYSTEM_NAME=WindowsStore
-DCMAKE_SYSTEM_VERSION=10.0
-DCMAKE_MSVC_RUNTIME_LIBRARY=MultiThreadedDLL
-DCMAKE_SYSTEM_PROCESSOR=arm
-DNEON_INTRINSICS=1
-DBUILD_SHARED_LIBS=ON
-DWITH_CRT_DLL=1
..`

3. x64

`cmake -G "Visual Studio 17 2022" -A x64 -DCMAKE_SYSTEM_VERSION=10.0 -DCMAKE_MSVC_RUNTIME_LIBRARY=MultiThreadedDLL -DCMAKE_SYSTEM_PROCESSOR=x64 -DNEON_INTRINSICS=1 -DBUILD_SHARED_LIBS=ON -DWITH_CRT_DLL=1 ..`