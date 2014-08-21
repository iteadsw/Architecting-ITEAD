# Architecting
### 天下事只在人力作为，到水尽山穷之时自有路走，只要切实去办

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
> 
> 阳
> 
> 文明其精神，野蛮其体魄
> 
> 当人们在诚实劳动中创造生活，勇气不灭。
> 
> 天将降大任于是人也，必先苦其心志，劳其筋骨，饿其体肤，空乏其身，行拂乱其所为，所以动心
> 忍性，曾益其所不能。
> 
> 人，生而未知。凡事总有一个认知过程。疑问、不解必然一直存在，因为知与不知必定同时存在，
> 人必定时刻处于知与不知的过程中。知晓宇宙与阴阳的关系，才能勇敢前行。

--------------------------------------------------------------------------------

# [Okay] 使IteadOS SDK支持中断
# [Okay] 将SDK和FBTFT打包为.deb
# 逻辑分析仪代码分析Python学习
# WxPython学习
# SDK GUI设计
# IteadOS全部源码托管到Github


# 提示： 博客

- 本月博客1：
- 本月博客2：
- 本月博客3：
- 本月博客4：
- 本月博客5：整理优雅实用的Markdown语法，制作Markdown简易教程，以后的博客都使用md格式
  来写，要整理一篇博客标准md格式。

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

