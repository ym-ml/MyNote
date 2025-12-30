1. 初始化
	git init
	touch .gitignore    creat .gitignore,then can use 'code' to open
	touch README.md<br>
	git add .
	git commit -m 'init'<br>
	git remote add *name(eg:origin)* https:// or ssh
	git push -u origin master/main 
2. 
	git remote -v  查看所有远程仓库
	git branch -vv  查看当前分支的上游远程仓库
	git branch -u [origin/master] 更改上游
3. 
	git push和git pull默认行为不同,git push gitee可以实现,但是git pull gitee不对,必须加上master,即git pull gitee master

4. 不小心上传了'垃圾'文件到仓库:
 *下文是从历史中彻底删除:
	1. 确保 .trash 已添加到 .gitignore
		echo ".trash/" >> .gitignore
	2. 从Git中删除追踪（但保留本地文件）
		git rm -r --cached .trash/
	3. 提交删除
		git commit -m "移除 .trash 目录的版本控制"
	4. 推送到远程
		git push gitee master
	5. 清理本地Git缓存
		git reflog expire --expire=now --all
		git gc --prune=now


5. 强制恢复到远程仓库的状态:
	先暂存任何未提交的修改
	git stash
	
	git fetch origin 获取origin
	强制重置到 origin 的最新状态
	git reset --hard origin/master
	
	恢复暂存的修改（如果有）
	git stash pop
 
6. 
	强制推送:
	git push gitee master --force

7. 
	git reset 撤回add加入到缓存的文件  可以有git reset file.txt 针对一个文件
	
	默认是--mixed模式,即撤销缓存,不丢弃更改
