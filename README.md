## XPS9360_Hackintosh
XPS9360_Hackintosh_8250u使用笔记

* 安装macOS
  * 1.下载镜像
  * 2.写入U盘
      * win工具：etcher https://www.balena.io/etcher/
      * macOS 工具：终端命令 sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume                            /Volumes/USB   --applicationpath /Applications/Install\ macOS\ Mojave.app --nointeraction
  * 3.替换efi
      * https://github.com/the-darkvoid/XPS9360-macOS
      * https://github.com/0xHJK/XPS13-9360-i5-8250U-macOS
  * 4.后续
      * 运行终端，cd到该目录下，运行如下几条命令：
        bash XPS9360.sh --compile-dsdt 
        bash XPS9360.sh --enable-3rdparty
        bash XPS9360.sh --disable-touchid
      * 修复声音 
        * 方法一：
        * sudo ./XPS9360.sh --patch-hda , 同时删除EFI/kexts/AppleAlc.kext
        * 方法二(推荐)：
        * 对比方法一，无底噪，无插入时的短暂刺响，解决了唤醒时耳机无效问题
        * 移动AppleAlc.kext至clover/kexts/other , commcode注入/Library/Extensions/目录 ，修改ssdt alcid=13
      * 获取三码
      * 蓝牙设置  把EFI/kexts/Library-Extensions里面的蓝牙kext文件安装到/Library/Extensions/目录
      * 参照 https://github.com/0xHJK/XPS13-9360-i5-8250U-macOS

* 插件配置
  * 1.iterm2配置
      * 参照 
      * https://www.cnblogs.com/diyxiaoshitou/p/9017413.html(推荐)
      * https://blog.csdn.net/gangyin5071/article/details/79601132
  * 2.JDK配置
      * 参照 
      * https://blog.csdn.net/deliciousion/article/details/78046007
      * export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_192.jdk/Contents/Home
  * 3.mysql配置
      * export PATH=${PATH}:/usr/local/mysql/bin
  * 4.python安装
      * python3直接下载安装即可
  * 5.idea pycharm默认配置
