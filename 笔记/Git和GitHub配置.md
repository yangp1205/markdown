### Git和GitHub配置

_代码同步和历史版本控制_

```bash
# 生成密钥
ssh-keygen -t rsa
# git基础配置
git init
git status
git push origin master #同步上传
git pull origin master #下载同步
git checkout . # 取消本地修改
git add . # 添加修改缓存
git commit -m "init" # 提交修改并添加说明
git commit -a

# git远程连接
git remote add origin master git@ #通过ssh链接远程服务
git remote remove origin # del origin
# 可通过ssh连接到远程
git remote --track branch origin https:// #追踪某一远程分支branch
git fetch origin # 更新origin的索引
git pull origin master:localmaster # 将远程分支master拉取到本地laoclmaster
git push origin localmaster:master #将本地的分支loaclmaster推送到远程master
git push origin :branch # 删除远程分支

# git分支管理
git branch -b branchname # 新建 branch
git checkout branch # change to branch
git checkout -t orgin/branchname # track origin branch
git merge branch #合并分支bracnc到当前分支
git branch # 查看分支
git branch -d branchname #删除branch
git branch -D branchname # 强制删除
git branch --set-upstream-to=origin/development #将本地的分支同步的远程分支修改

# git全局配置 config
git config --gabal user.name ""
git config --gobal user.email ""
git config

# git查看历史和恢复版本
git log
git reset
git reset --hard HEAD@{n} 
```
