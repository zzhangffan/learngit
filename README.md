readme

## 文件状态 ##
* 已跟踪
被纳入版本控制的文件，它们的状态可能处于未修改、已修改或已放入暂存区
* 未跟踪
除已跟踪之外的文件都属于未跟踪文件。
> 初次克隆某个仓库的时候，工作目录中的文件都属于已跟踪文件，并处于未修改状态
自上次提交后对某些文件进行编辑后，这些文件被标记为已修改文件（已修改），将这些修改后的文件放入暂存区（已暂存），然后提交所有暂存的修改（未修改）

```
	$ git status #检查文件状态
	On branch master #当前所在分支
	nothing to commit, working tree clean #工作区干净（所有已跟踪文件从上次提交后没有被更改过，不存在未跟踪的新文件）
```

## 基本命令 ##
* 仓库
``` 
	git init #初始化仓库
	git clone <url> #克隆远程仓库
	git remote #显示关联远程仓库
				-v #显示仓库简写及url
				add <shortname> <url> #添加远程仓库
				rename <old-name> <new-name> #修改远程仓库引用名字
				rm <shortname> #移除远程仓库
	git fetch [remote-name] #拉取远程仓库数据(本地没有的数据，不主动合并)
	git pull [remote-name] [branch-name] #拉取远程仓库数据（主动合并当当前分支或指定分支）
	git push [remote-name] [branch-name] #推送到远程仓库
```

* 基本操作
``` 
	git add <file>... #跟踪新文件
	git commit -m '' #提交更新
			 	-a #跳过暂存（将所有已跟踪文件暂存并提交）
			 	--amend #重新提交
	git rm <file>... #删除文件
		--cached #保留在磁盘
		-f #强制执行
	git mv <file_from> <file_to> #移动文件、重命名
	git reset HEAD <file>... #取消暂存文件
	git checkout -- <file>... #撤销对文件的修改
	git log #查看提交历史
			-p #显示内容差异
			-n #显示最近n条
			--stat #显示统计信息
			--pretty #指定格式
			--graph #图形表示分支合并历史
			--before #指定时间之前
			--after #指定时间之后
			--author #指定作者相关提交
			--decorate #查看各分支当前所指对象
	git diff <file>... #查看未暂存修改
			--staged #查看已暂存修改
	git config #配置
				--global #全局
				alias.<alias-name> '' #命令别名
```

## 分支 ##
>HEAD指向当前所在的分支并随着提交操作自动向前移动

```	
	git branch <branch-name> #创建分支（在当前提交对象上创建一个新指针）
				-d <branch-name> #删除分支
				-D <branch-name> #强制删除
				--merged #列出已合并到当前分支
				--no-merged #列出未合并到当前分支的
	git checkout <branch-name> #切换分支
	git merge <branch-name> #合并分支
	git rebase <branch-name> #合并分支（重播）
```
