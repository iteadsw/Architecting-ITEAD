# Architecting-ITEAD
### 天下事只在人力作为，到水尽山穷之时自有路走，只要切实去办
--------------------------------------------------------------------------------

# 当前

- [Okay]ITEADOS NAND 烧写
- [Okay]IteadOS全部源码托管到Github

- [Okay]SDK更新到2.9.2

- [Okay]SDK更到新2.9.5

- 编写SDK的Python接口

- 更新SDK到2.9.6

- 更新镜像从2.0.7到2.0.9：

    - 在新镜像中安装最新SDK，python-tk, python-dev

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

- 了解github账户与组织的差别，建立协作与贡献代码的框架
- Linux共享目录根本解决，提高工作效率
- 搜集更多更全Linux命令，提高工作效率
- Debian下的更多应用程序探索与尝试，提高工作效率



--------------------------------------------------------------------------------

# 提示： 更新SDK的git操作

## 下载最新的SDK并修改

    git clone https://github.com/iteadsw/SDK.git SDK-new
    
    cd SDK-new
    
    修改SDK

## 提交之前的检查

- 修改iteadcompile中的版本号
- 如果需要，修改README.md
- 如果需要，修改config.mk
- 执行make distclean
- 确保在每个example下没有编译过可执行文件
- 有关二进制文件，即在diff补丁中无效的文件要手动添加或删除
- 更新代码的同时，注意更新注释

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
    
    git push origin --tags
    
    git push origin master:master

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
