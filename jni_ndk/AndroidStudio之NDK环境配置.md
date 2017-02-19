## 目录

* [mac系统](#mac系统)
* [windows系统](#windows系统)





### mac系统

- ndk下载地址

https://dl.google.com/[Android](http://lib.csdn.net/base/android)/ndk/android-ndk-r10d-darwin-x86_64.bin

- 下载完成之后，在cmd命令中解压文件

  - cd  命令进入下载后ndk存放的目录

    ```shell
    cd /Users/apple/tools/ndk
    ```

  - 获取ndk目录的权限

    ```shell
    chmod a+x android-ndk-r10d-darwin-x86_64.bin
    ```

  - 执行解压命令

    ```shell
    ./android-ndk-r10d-darwin-x86_64.bin
    ```

    按下回车后，可以看到一直有信息在跑，表示解压成功，解压之后会看到一个文件夹。

- 打开终端使用命令指定ndk路径

  - 输入以下命令，回车

    ```shell
    pico .bash_profile
    ```

  - 在里面添加如下指令，最后保存（按 control＋X ） 选 Y ，回车

    ```shell
    export PATH=${PATH}:/Users/apple/tools/sdk/platform-tools 
    export NDK_ROOT=/Users/apple/tools/ndk/android-ndk-r10d
    export PATH=$PATH:$NDK_ROOT
    ```

  - 输入以下命令更新刚配置的环境变量

    ```shell
    source .bash_profile
    ```

- 检查是否配置成功

  终端进入到ndk下面的samples目录下的hello-jni项目

  ```shell
  cd /Users/apple/tools/ndk/android-ndk-r10d/samples/hello-jni
  ```

  执行ndk-build命令出现一堆信息表示配置成功了。

  ```shell
  ➜  hello-jni ndk-build
  [arm64-v8a] Gdbserver      : [aarch64-linux-android-4.9] libs/arm64-v8a/gdbserver
  [arm64-v8a] Gdbsetup       : libs/arm64-v8a/gdb.setup
  [x86_64] Gdbserver      : [x86_64-4.9] libs/x86_64/gdbserver
  [x86_64] Gdbsetup       : libs/x86_64/gdb.setup
  [mips64] Gdbserver      : [mips64el-linux-android-4.9] libs/mips64/gdbserver
  [mips64] Gdbsetup       : libs/mips64/gdb.setup
  [armeabi-v7a] Gdbserver      : [arm-linux-androideabi-4.8] libs/armeabi-v7a/gdbserver
  [armeabi-v7a] Gdbsetup       : libs/armeabi-v7a/gdb.setup
  [armeabi] Gdbserver      : [arm-linux-androideabi-4.8] libs/armeabi/gdbserver
  [armeabi] Gdbsetup       : libs/armeabi/gdb.setup
  [x86] Gdbserver      : [x86-4.8] libs/x86/gdbserver
  [x86] Gdbsetup       : libs/x86/gdb.setup
  [mips] Gdbserver      : [mipsel-linux-android-4.8] libs/mips/gdbserver
  [mips] Gdbsetup       : libs/mips/gdb.setup
  [arm64-v8a] Install        : libhello-jni.so => libs/arm64-v8a/libhello-jni.so
  [x86_64] Install        : libhello-jni.so => libs/x86_64/libhello-jni.so
  [mips64] Install        : libhello-jni.so => libs/mips64/libhello-jni.so
  [armeabi-v7a] Install        : libhello-jni.so => libs/armeabi-v7a/libhello-jni.so
  [armeabi] Install        : libhello-jni.so => libs/armeabi/libhello-jni.so
  [x86] Install        : libhello-jni.so => libs/x86/libhello-jni.so
  [mips] Install        : libhello-jni.so => libs/mips/libhello-jni.so
  ```

  ​