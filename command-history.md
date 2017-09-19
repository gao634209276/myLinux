##任务加载栏下移
	gsettings set com.canonical.Unity.Launcher launcher-position Bottom
	gsettings set com.canonical.Unity.Launcher launcher-position Left

##用户home下文件夹修改
	vim .config/user-dirs.dirs
##openssh安装
	sudo apt-get install openssh-server
	ps -e | grep ssh
	netstat -tlp
##ssh免密码
	ssh-keygen -t rsa -P ''
	ssh-copy-id localhost
	scp ~/.ssh/id_rsa.pub ip:~/.ssh/authorized_keys

## sudo
	%admin ALL=(ALL) NOPASSWD: ALL
	
##win qq安装
	sudo dpkg –I fonts-wqy-microhei_0.2.0-beta-2_all.deb
	sudo dpkg –I ttf-wqy-microhei_0.2.0-beta-2_all.deb
	sudo dpkg –I wine-qqintl_0.1.3-2_i386.deb
	sudo dpkg -i fonts-wqy-microhei_0.2.0-beta-2_all.deb ttf-wqy-microhei_0.2.0-beta-2_all.deb wine-qqintl_0.1.3-2_i386.deb 
	修复：
	sudo apt-get install -f 
	卸载
	sudo dpkg -l|grep qq
	sudo dpkg -r wine-qqintl
	sudo dpkg --purge  xx
##ubuntu安装和查看已安装
	http://www.cnblogs.com/forward/archive/2012/01/10/2318483.html

## 微信
	https://github.com/geeeeeeeeek/electronic-wechat/releases
	
## 温度监控
	http://blog.csdn.net/skykingf/article/details/46637609
## wine
	开启 32 位架构支持：
    sudo dpkg --add-architecture i386 
	添加ppa源
	sudo add-apt-repository ppa:wine/wine-builds  
	更新软件列表
	sudo apt-get update
	安装wine
	sudo apt-get install winehq-devel
		或先刷新包缓存再安装 Wine 1.8
		sudo apt-get install --install-recommends winehq-devel 
	##wineQQ8.9_19990.tar.xz
	http://blog.csdn.net/ysy950803/article/details/52958538
	tar xvf wineQQ8.9_19990.tar.xz -C ~/
	卸载qq的方法：
	rm -rf ~/.wine
	rm -rf ~/.local/share/applications/wine-QQ.desktop
	rm -rf ~/.local/share/icons/hicolor/256x256/apps/QQ.png
	rm -rf ~/.fonts/simsun.ttc
	通过上面的4条命令，就可以将我们刚刚安装好的qq完全删除掉。

##安装unity-tweak-tool主题
	http://www.jianshu.com/p/5b80711f304f
	sudo apt-get install unity-tweak-tool
	unity-tweak-tool
## 视图调整
	外观:
		启动器图标 18
		行为:隐藏启动器,左上角显示,开启工作区,菜单在敞口标题栏,鼠标炫富显示
	文本输入:
		汉语+英语,ctrl+shift切换源
	语言:汉语,Englist,fcitx输入法
	快捷键:截图修改,注销锁屏
	显示:最高分辨率,菜单/标题缩放比例为1,边缘关闭,
	系统-->通用辅助功能:大号字体 打开
	
##profile set
	http://www.2cto.com/os/201301/184129.html

## git 账号设置
	git config --global user.name "noah"
	git config --global user.email "634209276@qq.com"
	~/.ssh/config
	ssh -T xxx.xxx
	## git 2.0以前defult为matching，push时推送所有branch
	# git config --global push.default matching
	## git 2.0后可选simple,push时推送当前branch
	git config --global push.default simple
	##关于区别See：git help config

## 快捷键
	锁屏：Ctrl+Alt+L --> win+L
	注销：Ctrl+Alt+Del

## grup2启动顺序
	sudo gedit /etc/default
	GRUB_DEFAULT=2

## 修改从win系统复制的文件权限
	find ./ -type f | xargs -i chmod -x {}
	find ./ -type d | xargs -i chmod o-w {}

## 批量修改文件
	sed -i "s/old/new/g" `grep -rl "old" path`

## svn
	sudo apt-get install subversion
	vim ~/.subversion/config
	store-passwords = yes

## ubuntu jinfo
	解决方法:
	方法1、
	sudo tee /proc/sys/kernel/yama/ptrace_scope
	该方法在下次重启前有效。
	方法2、
	永久有效方法
	sudo vi /etc/sysctl.d/10-ptrace.conf
	编辑下面这行:
	kernel.yama.ptrace_scope = 1
	修改为:
	kernel.yama.ptrace_scope = 0
	重启系统，使修改生效。

## vim 
	bundle
	git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
	markdowm
	cd ~/.vim/bundle
	git clone https://github.com/plasticboy/vim-markdown.git
	vim 配置文件 ，高亮+自动缩进+行号+折叠+优化
	http://www.cnblogs.com/wangj08/archive/2013/03/13/2957309.html
	http://blog.csdn.net/simple_the_best/article/details/51901361
	http://blog.csdn.net/u013920085/article/details/46953293

## atom
	https://atom.io/
	https://github.com/atom/atom

## remarkable
	https://github.com/jamiemcg/remarkable
	https://remarkableapp.github.io/linux.html
	https://remarkableapp.github.io/linux/download.html
	https://remarkableapp.github.io/files/remarkable_1.87_all.deb
	https://aur.archlinux.org/packages/remarkable/
	
## c语言以及c++类库
	GCC系统自带,然后安装必须头文件build-essential,
	这个包会自动安装上g++,libc6-dev,Linux-libc-dev,libstdc++6-4.1-dev等
	一些必须的软件和头文件的库。
	sudo apt-get install build-essential
	
## qt-creator
	qt-creator已经渐渐地称为了VS之外的最佳C/C++ IDE
	关于gtk和qt:
		gtk开发速度慢而且丑，qt开发速度快而且漂亮。
		QtQuick出现以后，Qt性能甩开GTK好几条街，GTK社区没有拿出相对应的解决方案
		Qt核心活跃开发者基本上是GTK的4+倍, 
		GTK+不支持“分辨率无关”开发
		Qt还支持几乎所有主流智能手机操作系统
	sudo apt-get install build-essential
	安装 5.7.0 for Linux 64-bit (715 MB) 或者更高版本
	http://download.qt.io/official_releases/qt/5.7/5.7.0/qt-opensource-linux-x64-5.7.0.run

## nixnote2(印象笔记)
	https://github.com/baumgarr/nixnote2
	sudo add-apt-repository ppa:nixnote/nixnote2-daily
	sudo apt update
    sudo apt install nixnote2

## wizNote
	http://www.wiz.cn/compile-client.html
	安装 5.7.0 for Linux 64-bit (715 MB) 或者更高版本
	http://download.qt.io/official_releases/qt/5.7/5.7.0/qt-opensource-linux-x64-5.7.0.run
    sudo apt-get install build-essential
    sudo apt-get install cmake
    sudo apt-get install zlib1g-dev

	
##  c/c++ ide
	http://www.csdn.net/article/2014-02-27/2818564-best-compilers-and-ides-for-c-programmers
	1) Best IDE for C/C++ –  kDevelop
	Kdevelop是一个专为C/C++及其他语言的开源扩展插件IDE。它基于KDevPlatform平台，这是一款可用于IDE基础开源库。
	https://www.kdevelop.org/
	https://www.kdevelop.org/download
	wget -O KDevelop.AppImage https://download.kde.org/stable/kdevelop/5.1.0/bin/linux/KDevelop-5.1.0-x86_64.AppImage
	或者:
	sudo apt-get install kdevelop
	2) Best IDE for C/C++ –  Anjuta
	Anjuta Devstudio是另外一款强大的开发工具，拥有先进的编程特性包括项目管理、应用程序向导、交互式调试器、源码编辑器、版本控制，GUI设计、分析器等等。这款工具为C/C++开发者提供强大的用户界面接口。
	https://download.gnome.org/sources/anjuta/3.18/
	http://download.gnome.org/sources/anjuta/3.18/anjuta-3.18.0.tar.xz
	xz -d **.tar.zx
	tar -xvf **.tar

## wps for linux
	http://linux.wps.cn/
	未安装

## starUML
	http://staruml.io/download/release/v2.8.0/StarUML-v2.8.0-64-bit.deb


## idea
	http://idea.imsxm.com/
	http://idea.iteblog.com/key.php
	jrebel:
	https://my.jrebel.com/account/how-to-activate
	Ft2yNDRVL5Pq4Y8orLrXFWqsvn5NKjUZ0qFq4Z6QINfmNRBFvjXa8KK/G9U/PASS6YEpZcyQMTTv6Ev3oE8eZXwezW1OTWSrOjrLlHvy2lSmSHcKbIbZW2R6YLOaag2t/9YvQw==
	
	
	http://idea.lanyus.com/ilanyu
	lanyu19950316@gmail.com

	
## pycharm
	http://xidea.online


## myeclipse 
	/usr/share/themes/Radiance/gtk-2.0
	gtk-color-scheme = "base_color:#ffffff\nfg_color:#4c4c4c\ntooltip_fg_color:#ffffff\nselected_bg_color:#f07746\nselected_fg_color:#FFFFFF\ntext_color:#3C3C3C\nbg_color:#f6f4f2\ntooltip_bg_color:#000000\nlink_color:#DD4814"

gtk-color-scheme = "base_color:#C7EDCC\n
fg_color:#4c4c4c\n
tooltip_fg_color:#000000\n
selected_bg_color:#fff0f5\n
selected_fg_color:#FF6600\n
text_color:#3C3C3C\n
bg_color:#f6f4f2\n
tooltip_bg_color:#f2edbc\n
link_color:#DD4814"

## user group wireshark
sudo groupadd  wireshark
sudo chgrp wireshark /usr/bin/dumpcap
sudo chmod 4755 /usr/bin/dumpcap
sudo usermod -a -G wireshark noah
newgrp wireshark


## r rstudio
sudo apt install r-base-core r-base r-base-dev
sudo apt-get install libgstreamer0.10-0
sudo apt-get install libgstreamer-plugins-base0.10-0
	安装ggplot2包之前需要先安装其它的依赖包： 
	plyr , digest , gtable , reshape2 , scales ,  proto , 
	在Rstudio的命令窗口分别执行以下命令。
		install.packages('plyr')
		install.packages('digest')
		install.packages('gtable')
		install.packages('reshape2')
		install.packages('scales')
		install.packages('proto')
	然后，安装 ‘ ggplot2 ’ 包 , 安装成功后就可以使用了。
		install.packages('ggplot2')
## macbuntu
	添加macbuntu资源
	$sudo add-apt-repository ppa:noobslab/macbuntu
	安装mac窗口主题。
	$sudo apt-get install  macbuntu-os-ithemes-lts-v7
	安装mac图标主题。
	$sudo apt-get install  macbuntu-os-icons-lts-v7 
	卸载:
	cd /usr/share/icons/mac-cursors && sudo ./uninstall-mac-cursors.sh
	sudo apt-get remove macbuntu-os-icons-lts-v7 macbuntu-os-ithemes-lts-v7
	安装unity-tweak-tools配置主题工具
	$sudo apt-get install  unity-tweak-tools

	安装 Slingscold（替代Launchpad）
	sudo apt-get install slingscold
		安装 Plank Dock
		sudo apt-get install plank
		安装plank与对应plank的mac主题。
		$sudo apt-get install  macbuntu-os-plank-itheme-lts-v7 
		卸载:
		sudo apt-get autoremove plank macbuntu-os-plank-theme-lts-v7

	安装Docky
	sudo apt-get install docky
	这里docky安装完毕后，没办法直接添加程序到docky栏中，需要将程序打开，然后在docky中固定图标即可
		启动器图标更改
		wget -O launcher_bfb.png http://www.linuxidc.com/files/2017/03/launcher_bfb.png
		sudo mv launcher_bfb.png /usr/share/unity/icons/
		试了试没有成功，需要自己将图标下载下来，然后修改权限，将图标转移到/usr/share/unity/icons/

## python lib opencv
	See: http://blog.csdn.net/yehuohan/article/details/51327465
	sudo apt-get install build-essential
	sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
	sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
	opencv 官网源码下载:
	http://opencv.org/opencv-3-2.html
	# 生成后的Makefile在build文件夹中，而需要的CMakeLists.txt在 ".."中，即上一级文件夹中（opencv-3.2.0）
	cd opencv-3.2.0 && mkdir build && cd build
	cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local ..
	# 7个线程编译 和 安装
	make -j7 && sudo make install

## scikit-learn
	scikit-learn依赖
	sudo apt-get install build-essential python-dev python-numpy python-setuptools python-scipy libatlas-dev libatlas3-base 
	安装matplotlib
	sudo apt-get install python-matplotlib 
	安装pip
	sudo apt-get install python-pip 
	安装scikit-learn
	sudo pip install -U scikit-learn 
	安装spyder
	sudo apt-get install spyder 
	from:http://blog.csdn.net/laizhenghong2012/article/details/70256818


## IPython Notebook
	sudo apt-get install python-pip ipython ipython-notebook
	终端启动 ipython notebook
	sudo pip install jupyter
	# Jupyter其他基本配置,生成 notebook 配置文件
	jupyter notebook --generate-config
	vim ~/.jupyter/jupyter_notebook_config.py
	c.NotebookApp.notebook_dir = '/home/noah/workspaces/jupyter'
	c.NotebookApp.open_browser = False
	c.NotebookApp.token = ''
	
## python2和python3共存的Jupyter Notebook
	# 安装python和python-pip
	sudo apt-get install python python3 python-pip python3-pip
	sudo pip install --upgrade pip  #更新pip
	sudo pip3 install --upgrade pip
	# 安装jupyter-notebook
	sudo pip install jupyter
	sudo pip3 install jupyter
	# 配置可以同时使用python2和python3内核
	sudo ipython kernel install--user
	sudo python3 -m ipykernel install--user
	sudo pip2 install -U ipykernel
	sudo python2 -m ipykernel install--user
	jupyter kernelspec list
	# 添加到环境变量并运行
	export PATH=$PATH:~/.local/bin  #当前会话生效
	sudo jupyter-notebook 或者
	~/.local/bin/jupyter-notebook #运行，会自动打开web界面，可以同时运行python2，python3，ctrl+c结束
	把export PATH=$PATH:~/.local/bin 添加到的最后一行 ~/.bashrc ，永久生效
	# 参考:
		http://www.cnblogs.com/v5captain/p/6688494.html
		http://www.cnblogs.com/knmax/p/6605560.html

## Jupyter Notebook kernel With scala_2.10
	git clone git@github.com:jupyter-scala/jupyter-scala.git
	/home/noah/.local/share/jupyter/kernels
	#https://oss.sonatype.org/content/repositories/snapshots/com/github/alexarchambault/jupyter/jupyter-scala-cli_2.10.5/0.2.0-SNAPSHOT/jupyter-scala_2.10.5-0.2.0-SNAPSHOT.tar.xz

# 基于Scala spark的jupyter notebook
	http://blog.csdn.net/xmo_jiao/article/details/72674687?utm_source=itdadao&utm_medium=referral
	#https://github.com/apache/incubator-toree
	sudo pip install toree-0.2.0.dev1.tar.gz
	jupyter toree install --spark_opts='--master=yarn' --user --kernel_name=Spark2.0 --spark_home=/app/sinova/spark-2.0.2


## Xgboost
	git clone方式:
		git clone --recursive https://github.com/dmlc/xgboost
		# 建立共享库（此过程需要一点时间，请耐心等待）
		cd xgboost; make -j4
		# Python package的安装
		cd python-package; sudo python setup.py install
		# python依赖项的安装
		sudo apt-get install python-setuptools
		# 设置环境变量，告诉Python去哪里找库
		export PYTHONPATH=~/xgboost/python-package
	pip方式:
	sudo pip install xgboost
	
##　python scipy stack:
	sudo apt-get install python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy python-nose  

## python wx 模块
	apt-get install python-wxtools
	
## python pywt 模块 小波变换
	pip install PyWavelets
	https://pywavelets.readthedocs.io/en/latest/#install
	
## python gumis


## ubuntu 思维导图 MindManager --> XMind
	http://tonybai.com/2010/08/25/move-to-ubuntu-thoroughly/
	
	http://www.xmind.net/blog/en/2016/11/ui-does-not-work-properly-in-ubuntu-16-04/

## tracker-extract 资源消耗太高解决
    echo -e "\nHidden=true\n" | sudo tee --append /etc/xdg/autostart/tracker-extract.desktop /etc/xdg/autostart/tracker-miner-apps.desktop /etc/xdg/autostart/tracker-miner-fs.desktop /etc/xdg/autostart/tracker-miner-user-guides.desktop /etc/xdg/autostart/tracker-store.desktop > /dev/null
    gsettings set org.freedesktop.Tracker.Miner.Files crawling-interval -2  
    gsettings set org.freedesktop.Tracker.Miner.Files enable-monitors false  
    tracker reset --hard  

    from:
    https://askubuntu.com/questions/346211/tracker-store-and-tracker-miner-fs-eating-up-my-cpu-on-every-startup

## fcitx 资源消耗太高重启
    先用top或者system monitor杀掉ficix进程，再用如下命令重启即可。
    fcitx &
    fcitx-qimpanel &

