### 安卓编译步骤

- 安装对应版本 java sdk ndk

- 安装msys2 https://www.msys2.org/

  ```
  pacman -S mingw-w64-x86_64-cmake
  pacman -S git
  ```

- 打开 MSYS2 MinGW x64

- 执行命令

  ```
  export PATH=$JAVA_HOME/bin:$PATH
  
  mkdir build-android
  cd build-android
  cmake -DBUILD_ANDROID=On -DANDROID_ABI=armeabi-v7a -G "MinGW Makefiles" ..
  mingw32-make
  
  cmake -DBUILD_ANDROID=On -DANDROID_ABI=arm64-v8a -G "MinGW Makefiles" ..
  mingw32-make
  ```
  
- 可参考文章 https://zhuanlan.zhihu.com/p/339673291
  
  - 一些重要命令
  
      ```
      pacman -S mingw-w64-x86_64-cmake
      pacman -S mingw-w64-x86_64-make
      pacman -S mingw-w64-x86_64-gcc
      pacman -S git
      ```
  
      ```
      mkdir build-android
      cd build-android
      cmake -DBUILD_ANDROID=On -DANDROID_ABI=armeabi-v7a -G "MinGW Makefiles" ..
      mingw32-make -j20
      
      mkdir build-android64
      cd build-android64
      cmake -DBUILD_ANDROID=On -DANDROID_ABI=arm64-v8a -G "MinGW Makefiles" ..
      mingw32-make -j20
      ```



