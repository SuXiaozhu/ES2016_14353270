# ES2016_14353270
README
DOL开发环境配置

- 安装一些必要的环境
  - $ sudo apt-get update
  - $ sudo apt-get install ant
  - $ sudo apt-get install openjdk-7-jdk
  - $ sudo apt-get install unzip

- 下载文件
  - dol_ethz.zip
  - systemc-2.3.1.tgz
- 解压文件
  - 新建dol的文件夹
          $ mkdir dol
  - 将dolethz.zip解压到 dol文件夹中
          $ unzip dol_ethz.zip -d dol
  - 解压systemc
         $ tar -zxvf systemc-2.3.1.tgz
- 编译systemc
  - 解压后进入systemc-2.3.1的目录下
         $ cd systemc-2.3.1
  - 新建一个临时文件夹objdir
         $ mkdir objdir
  - 进入该文件夹objdir
         $ cd objdir
  - 运行configure(能根据系统的环境设置一下参数，用于编译)
         $ ../configure CXX=g++ --disableasync-updates
  - 编译
    $ sudo make install
  - 记录当前的工作路径
    $ pwd
- 编译dol
  - 进入刚刚dol的文件夹
    $ cd ../dol
  - 修改build_zip.xml文件
    找到下面这段代码
    <property name="systemc.inc" value="YYY/include"/>
    <property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
    把YYY改成pwd的结果
  - 然后是编译
    $ ant -f build_zip.xml all
- 试运行第一个例子
  - 进入build/bin/mian路径下
    $ cd build/bin/main
  - 然后运行第一个例子
    $ sudo ant -f runexample.xml -Dnumber=1
    
  
  
  

  




