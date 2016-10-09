
## 一. DOL框架描述 ##


The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.



## 二. DOL安装笔记 ##


### 安装一些必要的环境 ###

* sudo apt-get update

* sudo apt-get install ant.

* sudo apt-get install openjdk-8-jdk

* sudo apt-get install unzip


###解压文件###

* 新建dol的文件夹 : mkdir dol

* 将dolethz.zip解压到dol文件夹中 : unzip dol_ethz.zip -d dol

* 解压systemc : tar -zxvf systemc-2.3.1.tgz


### 编译systemc ###

* 解压后进入systemc-2.3.1的目录下 ; $	cd systemc-2.3.1

* 新建一个临时文件夹objdir : $	mkdir objdir

* 进入该文件夹objdir : $	cd objdir

* 运行configure(能根据系统的环境设置一下参数，用于编译)
 ../configure CXX=g++ --disable-async-updates

* 编译: $	sudo make install

* 记录当前的工作路径 : $	pwd(我的为/home/haoyf/systemc-2.3.1/objdir)



### 编译dol ###
* 进入刚刚dol的文件夹:$	cd ../dol

* 修改build_zip.xml文件

property name="systemc.inc" value="YYY/include"/

property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/

把YYY改成上页pwd的结果

(我的)property name="systemc.inc" value="/home/haoyf/systemc-2.3.1/objdir/include"/

property name="systemc.lib" value="/home/haoyf/systemc-2.3.1/objdir/lib-linux64/libsystemc.a"/

* 编译：$	ant -f build_zip.xml all
若成功会显示build successful

## 三. 感想心得 ##


配置过程非常不顺利。。。师兄看来我原来配置的虚拟机，说版本不好很容易出现问题，没用的话就重新装一个Ubuntu吧，又建了新虚拟机之后开始配置。

第一条语句sudo apt-get update的时候就出现了文件夹lock。师兄教我下次碰到就直接删除lock文件，语句为 sudo rm -f /var/lib/dpkg/lock 。之后还是碰到很多很多lock，一步步做下去没有什么问题。最后面$	cd ../dol的时候又显示no such file，问了别人，他说我开错文件夹了，开了正确的文件夹后终于build成功了，历时两天。

虽然虚拟机在上学期操作系统实验课上用到了，但都是在固定的文件里面改代码，但对于Linux还是非常陌生，一些最基本的操作都不懂什么意思，很茫然一直在求助。师兄们人很好，每个问题都耐心解答，也和师兄交流怎样学好计算机。还是要多学多做，主动去学，主动找资料，不能总等着别人来教，遇到困难自己先想解决办法，才能有所提高。





