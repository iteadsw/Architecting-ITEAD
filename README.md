# Architecting
### 天下事只在人力作为，到水尽山穷之时自有路走，只要切实去办
--------------------------------------------------------------------------------

# 当前

- ITEADOS NAND 烧写
- 更新镜像：在新镜像中安装最新SDK，python-tk
- 为SDK提供Python接口
- 串口WIFI库的评估
  - http://pan.baidu.com/s/1kToky7H
  - http://arduino.cc/en/Reference/WiFi
- OLED 屏幕的 Arduino library

# 长期

- [Okay] 使IteadOS SDK支持中断
- [Okay] 将SDK和FBTFT打包为.deb
- [On20] 逻辑分析仪代码分析Python学习
- WxPython学习
- SDK GUI设计

# 挂起

- Linux共享目录根本解决，提高工作效率
- 搜集更多更全Linux命令，提高工作效率
- Debian下的更多应用程序探索与尝试，提高工作效率
- IteadOS全部源码托管到Github


# 提示： 文档

- 9月4日ITEAD OS 安装说明WPF、Sherry 有在不同的系统下安装ITEAD OS 。。MAC、WIN、LinUX
- 9月5日ITEAD SDK入门简介WPF 部分SDK功能说明；SDK安装；SDK架构等等内容。。。
- 9月13日板载器件使用：IR WPF 无安装IR驱动，读取遥控键值，并根据键值做不同动作，比如，打开某个软件、关机等操作
- 9月9日板载器件使用：固定MAC地址Sherry 有现成文档
- 9月15日外接器件：Access The GPIO LIZQ、WPF 部分点亮LED ,读取Sensor Brick 数字量输出；中断；Python界面，控制LED等
- 9月9日外接器件：I2C：OLED SSD1306、SHT1x Jerry、WPF
  无使用电子积木、树莓ADD-on进行演示；Python界面；播放动画，读取CPU占用率；温度显示；
- 9月20日外接器件：SPI：nrf24l01+libnfc Jerry、WPF 无硬件连接、数据收发；Python界面直接显示收到的舒服、图形界面发送数据


# 提示： 更新SDK的git操作

## 下载最新的SDK并修改

    git clone https://github.com/iteadsw/SDK.git SDK-new
    
    cd SDK-new
    
    修改SDK

## 打补丁之前的检查

- 修改iteadcompile中的版本号
- 如果需要，修改README.md
- 如果需要，修改config.mk
- 执行make distclean
- 确保在每个example下没有编译过可执行文件

## 修改完后打补丁

    cd SDK-new && cd ../
    
    git clone https://github.com/iteadsw/SDK.git
    
    diff -wurNB --exclude=.* SDK SDK-new > new.patch

## 提交修改

    登录RDServer:github用户
    
    cd RDServer:/home/github/iteadsw/SDK
    
    git checkout master
    
    git pull
    
    patch -p1 < ../new.patch
    
    git add *
    
    git commit -a -m "Update SDK by Wu Pengfei"
    
    如果需要，则删除一个标签： git tag -d tag_name
    
    git tag -a tag_name -m "version x.x"
    
    如果需要，则删除一个分支： git branch -D branchname
    
    git branch IteadOS-SDK-tag_name tag_name
    
    git push origin --tags
    
    git push origin master:master
    
    git push origin IteadOS-SDK-tag_name:IteadOS-SDK-tag_name

## Well done !

> 
> 阴
> 
> 生命有限 跟随内心 择吾所爱 追求完美 求知若饥 虚心若愚 淡泊明志 宁静致远
> 
> 不迷失 不放弃 珍惜现有的 追寻想要的
> 
> 平凡的世界 不一样的人生 一生幸福 一职生涯 一事一春秋 是是一伟业 
> 
> 专注成就梦想 你就是你想要成为的那个人。
> 
> 阳
>
> 文明其精神，野蛮其体魄
>
> 当人们在诚实劳动中创造生活，勇气不灭。
> 
> 天将降大任于是人也，必先苦其心志，劳其筋骨，饿其体肤，空乏其身，行拂乱其所为
> , 所以动心忍性，曾益其所不能
> 
> 人，生而未知。凡事总有一个认知过程。疑问、不解必然一直存在，因为知与不知必定
> 同时存在，人必定时刻处于知与不知的过程中。知晓宇宙与阴阳的关系，才能勇敢前行。
>
