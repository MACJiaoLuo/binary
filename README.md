# binary
安卓termux交叉编译的一些软件，能不能用看脸
备份
--prefix=/system
-l:libxxx.a

编译Shadowsocks-libev 安卓版
```  
git clone https://github.com/shadowsocks/shadowsocks-libev.git
cd shadowsocks-libev
git submodule update --init --recursive 
./autogen.sh
./configure --disable-documentation
```  
编译好各个依赖库文件。不通过可以试试cmake编译器
Makefile文件加入 -llog 链接库不然报错。
然后就编译会显示报错源码文件，在那个文件报错就改那个
大多数是判断__ANDROID__应该是针对ndk编译器的
注释掉local.c源码中的
``` 
//char *log         = profile.log;
//USE_LOGFILE(log);
```  
然后其他的看编译器报错出处，按需修改或者注释。  
链接静态库文件编译。  
收工。
