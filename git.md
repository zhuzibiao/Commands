1、提交
git status 看哪些文件被修改、暂存或未跟踪
git diff 查看未暂存的修改
git diff --staged	查看 add 之后、commit 之前的差异
git add <文件>	添加指定文件到暂存区
git add .	添加当前目录所有改动
git commit -m "说明"	提交暂存区内容
git commit --amend -m "说明"	未推送前可修改提交信息
git log --oneline	简洁查看提交记录
2、分支
git branch	查看本地分支
git branch -a	包含远程分支
git switch -c 分支名	推荐新写法
git switch 分支名	替代 git checkout
git branch -d 分支名	安全删除
git branch -D 分支名	未合并也会删，慎用
git branch -m 新分支名	重命名当前分支
git merge 分支名	把指定分支合并到当前分支
git rebase -i HEAD~N	合并/修改最近 N 条提交
3、远程
git clone <地址>	拉取远程仓库
git remote -v	查看远程仓库配置
git fetch origin	只下载，不合并
git pull	相当于 fetch + merge
git push	推送到远程
git push -u origin 分支名	建立上游跟踪关系
git push origin --delete 分支名	删除远程分支
4、提交回退
git restore <文件>	撤销未暂存的改动
git restore --staged <文件>	撤销 add
git reset --soft HEAD~1	保留代码和暂存区
git reset HEAD~1	默认 mixed，保留工作区
git reset --hard HEAD~1	会丢失未提交改动，慎用
git revert <commit>	生成新提交来撤销，适合已推送
git restore --source=<commit> --staged --worktree -- <文件>	只恢复指定文件
git reflog	找回 reset/rebase 前的提交
5、临时保存
git stash	功能做一半需要切分支时用
git stash list	查看保存记录
git stash pop	恢复最近一次暂存并删除记录
git tag	查看版本标签
git tag v1.0	给当前提交打标签
git push origin v1.0	推送指定标签到远程
