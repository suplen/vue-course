配置：
	name
		git config --global user.name "suplen"
	email
		git config --global user.email "429732421@qq.com"
		
使用Git：
	git status
		- 查看当前仓库的状态
	git init
		- 初始化仓库
		
	刚刚添加到项目中的文件处于未跟踪状态：
		未跟踪 ---> 暂存
			git add <filename> 将文件切换到暂存的状态
			git add * 将所有已修改(未跟踪)的文件暂存
		暂存 ---> 未修改
			git commit -m "xxx" 将暂存的文件存储到仓库中
			git commit -a -m "xxx" 提交所有已修改的文件(未跟踪的文件不会提交)
		未修改 ---> 修改
			修改代码后，文件会变为修改状态
			
	git log 查看提交的记录
	
	常用的命令：
		git restore <filename>
			恢复到上一次commit的状态
		git restore * 所有文件都恢复到上一次commit的状态
		git restore --staged <filename> 从暂存状态取消
			再用恢复恢复文件
		
		git rm <filename> 删除文件
		git rm <filename> -f 强制删除文件
		
		git mv from(filename) to(filename) 移动文件 重命名文件
		
		分支与分支相互独立
		git branch 查看分支
		git branch <branch name> 创建分支
		git branch -d <branch name> 删除分支
		
		git switch <branch name> 切换分支
		
		git switch -c <branch name> 创建并切换分支
		
		git merge <branch name>  在主分支上合并该分支
		
		git rebase <branch name>  把当前分支的基设置到该分支上
		
		变基和merge对于合并分支来说最终的结果是一样的，但是变基会使得代码的提交记录更整洁更清晰
		注意：大部分情况下合并和变基是可以互换的，但是如果分支已经提交给了远程仓库，那么这时尽量不要变基
		
		…or push an existing repository from the command line
		git remote add <remote name> <remote url>
		git remote add origin https://github.com/suplen/git-demo.git
		修改分支的名字为main
		git branch -M main
		git push -u <remote name> <branch name>  将代码上传到服务器上
		git push -u origin main
		
		cd existing_git_repo
		git remote add gitee https://gitee.com/suplen/git-demo.git
		git push -u gitee main
			
		克隆库里的代码
		git clone https://github.com/suplen/git-demo.git
		
		远程库的操作命令
		git remote 列出当前关联的远程库
		git remote add <远程库名> <远程库url> 关联远程仓库 （把库名代替url方便编写）
		git remote remove <远程库名> 移除关联远程库
		git remote -v 显示上传和下载远程库的地址
		git push -u <远程库名> <分支名> 向远程库推送代码，并和当前分支关联
		git clone <url> （下载到指定的文件夹中<filename>） 从远程库下载代码
		
		注意：如果本地库的版本低于远程库的，push默认是推不上去的
			要想推送成功，必须先确保本地库和远程库的版本一致
			git fetch 它会从远程仓库下载所有代码
			但是它不会将代码和当前分支自动合并
			使用fetch拉取代码后，必须要手动对代码进行合并
			是本地分支和远程库分支合并
			git merge <远程库名>/<远程库分支名>
			然后打开代码选取合并的选项
			保存，添加暂存，提交， 然后可以git push
			
			git filter-branch 慎用



		
			
			
			
			
			
			
			
			
			
			
			
			
			