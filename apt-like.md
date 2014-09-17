# apt-like

> 这里记录一些与debian安装包管理器相关的东西，例如apt-get命令，aptitude命令，
> dpkg命令等。针对于linux下的安装包管理，真的是个非常头疼的事，不过目前的apt系列
> 已经做得很好了，只是我还不会用而已。加油。

--------------------------------------------------------------------------------
# apt-get 

- 为 apt-get 加上 -d 参数，使其只下载而不安装


--------------------------------------------------------------------------------
# dpkg

列出与该软件包相关的文件：

    dpkg -L package
    
搜索该文件所属的安装包：

    dpkg --search abs_file_path

- dpkg -X foo.deb :是将 deb 包的内容文件释放出来
- dpkg -e foo.deb :是将 deb 包的控制信息释放出来
- dpkg -I foo.deb :查看 foo.deb 的控制信息
- dpkg -c foo.deb :查看 foo.deb 包含了什么文件
- sudo dpkg -i foo.deb :安装 foo.deb。
- sudo dpkg -r foo.deb :卸载 foo.deb。
- sudo dpkg -P foo.deb :卸载(清除用户配置数据) foo.deb。

--------------------------------------------------------------------------------
# aptitude

- aptitude 图形界面管理
- aptitude show package_name
- aptitude search part_name 自动搜索
    - p,i,v,c
- aptitude install package_name
- aptitude purge package_name
- aptitude remove package_name

 
--------------------------------------------------------------------------------
# 安全升级的命令

    sudo aptitude safe-upgrade # 推荐使用
    sudo aptitude dist-upgrade
    sudo aptitude full-upgrade

--------------------------------------------------------------------------------
# 以下内容来自 <http://www.2cto.com/os/201302/191854.html>


    apt-get指令的autoclean,clean,autoremove的区别
     
    下面总结一下有关apt-get的常用但容易混淆的指令:
    
    apt-get autoclean:
        如果你的硬盘空间不大的话，可以定期运行这个程序，将已经删除了的软件包的.deb
        安装文件从硬盘中删除掉。如果你仍然需要硬盘空间的话，可以试试apt-get clean，
        这会把你已安装的软件包的安装包也删除掉，当然多数情况下这些包没什么用了，
        因此这是个为硬盘腾地方的好办法。
     
    apt-get clean:
        类似上面的命令，但它删除包缓存中的所有包。这是个很好的做法，因为多数情况下这
        些包没有用了。但如果你是拨号上网的话，就得重新考虑了。
     
    apt-get autoremove:
        删除为了满足其他软件包的依赖而安装的，但现在不再需要的软件包。

    apt-get remove 软件包名称：
        删除已安装的软件包（保留配置文件）。
    apt-get --purge remove 软件包名称：
         删除已安装包（不保留配置文件)。
 
