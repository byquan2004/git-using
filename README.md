# git-using

## **基础命令**

|命令|作用|注意|
| :- | :- | :- |
|git -v|查看 git 版本||
|git init|初始化 git 仓库||
|git add 文件标识|暂存某个文件|文件标识以终端为起始的相对路径|
|git add .|暂存所有文件||
|git commit-m '说明注释'|提交产生版本记录|每次提交，把暂存区内容快照一份|
|git status|查看文件状态 - 详细信息||
|git status -s|查看文件状态 - 简略信息|第一列是暂存区状态，第二列是工作区状态|
|git ls-files|查看暂存区文件列表||
|git restore 文件标识|从暂存区恢复到工作区|如果文件标识为 . 则恢复所有文件|
|git rm --cached 文件标识|从暂存区移除文件|不让 git 跟踪文件变化|
|git log|查看提交记录 - 详细信息||
|git log --oneline|查看提交记录 - 简略信息|版本号 分支指针 提交时说明注释|
|git reflog --oneline|查看完整历史 - 简略消息|包括提交，切换，回退等所有记录|
|git reset 版本号|切换代码到暂存区和工作区|--soft 模式保留暂存区和工作区原本内容 --hard 模式不保留暂存区和工作区原本内容 --mixed 模式不保留暂存区，工作区保留（默认）先覆盖到暂存区，再用暂存区对比覆盖工作区|
|git branch 分支名|创建分支||
|git branch|查看本地分支||
|git branch -d 分支名|删除分支|请确保记录已经合并到别的分下，再删除分支|
|git checkout 分支名|切换分支||
|git checkout -b 分支名|创建并立刻切换分支||
|git merge 分支名|把分支提交历史记录合并到当前所在分支||

## **仓库命令**

|命令|作用|注意|
| :- | :- | :- |
|git remote add 远程仓库别名 远程仓库地址|添加远程仓库地址|别名唯一，地址是 .git 结尾的网址|
|git remote -v|查看远程仓库地址||
|git remote remove 远程仓库别名|删除远程仓库地址||
|git pull 远程仓库别名 分支名|拉取|完整写作：git pull 远程仓库别名 远程分支名:本地分支名 = git fetch 和 git merge|
|git push 远程仓库别名 分支名|推送|完整写作：git push 远程仓库别名 本地分支名:远程分支名 -u：建立通道后可以简写 git push|
|git pull --rebase 远程仓库别名 分支名|拉取合并|合并没有关系的记录|
|git clone 远程仓库地址|克隆|从0得到一个远程的Git仓库到本地使用|

## **语义化提交**

### **语义化前缀**

- 如果是添加新功能，使用 feat。
- 如果是修复 bug，使用 fix。
- 如果是样式更改，使用 style。
- 如果是重构代码，使用 refactor。
- 如果是性能改进，使用 perf。
- 如果是文档变更，使用 docs。
- 如果是添加或更新测试，使用 test。
- 如果是构建系统或外部依赖项的变更，使用 build。
- 如果是持续集成配置的变更，使用 ci。
- 如果是其他类型的变更，如脚本或工具的更新，使用 chore。

### **示例**

**添加新功能**
- feat(user): add email verification
- feat(auth): implement login with Google

**修复bug**
- fix(login): resolve incorrect redirection
- fix(api): handle null response

**文档变更**
- docs(readme): update installation instructions
- docs(contributing): add code of conduct reference

**样式更改**
- style(components): format using prettier
- style(+[pkg-name]): remove unused imports

**重构**
- refactor(service): simplify newsletter subscription flow
- refactor(+[navigation]): extract common navigation logic

**性能改进**
- perf(api): cache results to reduce db calls
- perf(components): optimize image loading

**测试**
- test(unit): add missing unit tests for components
- test(integration): ensure consistent test coverage

**其他任务**
- chore(deps): bump minor dependencies
- chore(ci): add deploy pipeline

**持续集成**
- ci(travis): update build script
- ci(circle): add new test job

**构建系统**
- build(webpack): upgrade webpack version
- build(scripts): improve build scripts

**回滚**
- revert("feat(auth): add two-factor authentication")


