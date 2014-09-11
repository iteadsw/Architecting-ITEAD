# Architecting
### 天下事只在人力作为，到水尽山穷之时自有路走，只要切实去办
--------------------------------------------------------------------------------

# 当前

- [Okay]ITEADOS NAND 烧写
- [Okay]IteadOS全部源码托管到Github

- SDK更新
  - 删除中断模块，从IteadOS-3.0.0之后，itead_gpio_int.ko将在镜像中安装。无需在SDK里面。
  - 将SDK相关的GPIO对照表放在SDK/tools下面
  - 将IteadOS_A20_09051120_defconfig 更新为SDK/tool/iteaduino_plus_a20_defconfig
  - 在tool/final-.rule中添加对itead_gpio_int的权限控制
  - 替换IteadOS为ITEAD-OS

  - 添加注释，方便生成文档，并把当前版本的帮助文档放在SDK/doc目录下
  - 为SDK提供Python接口


- 更新镜像：在新镜像中安装最新SDK，python-tk

- 写文档
  - 目标：编写文档SDK相关
  - 目录

            1. ITEAD－SDK入门简介
            2. 板载IR使用演示（根据键值做出相应）
            3. I2C设备演示 （Python GUI）
            4. SPI设备演示 （Python GUI）
      
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
