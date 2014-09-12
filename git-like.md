下面通过一些示例具体看一下检出命令的不同用法。

    $ git checkout branch
    
检出branch分支。要完成图中的三个步骤，更新HEAD以指向branch分支，以及用branch  指向的树更新暂存区和工作区。

    $ git checkout
汇总显示工作区、暂存区与HEAD的差异。

    $ git checkout HEAD
    
同上

    $ git checkout -- filename
    
用暂存区中filename文件来覆盖工作区中的filename文件。相当于取消自上次执行git add filename以来（如果执行过）的本地修改。

    $ git checkout branch -- filename
    
维持HEAD的指向不变。用branch所指向的提交中filename替换暂存区和工作区中相   应的文件。注意会将暂存区和工作区中的filename文件直接覆盖。

    $ git checkout -- . 或写作 git checkout .
    
注意git checkout 命令后的参数为一个点（“.”）。这条命令最危险！会取消所有本地的  修改（相对于暂存区）。相当于用暂存区的所有文件直接覆盖本地文件，不给用户任何       确认的机会！
