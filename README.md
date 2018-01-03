简单记录日常


### 项目启动和运行方法
目前存在两个分支 `master` `dev` <br>
其中：
- master 分支用来发布blog代码，也就是generate之后的项目文件；
- dev 分支用来本地编辑开发；
- 当前仓库的默认分支是`dev`分支，在`dev`分支开发完成后的步骤：
  - hexo g ==> 生成预览博客
  - hexo s ==> 4000端口本地预览博客
  - hexo d ==> 检查无误后，发布到仓库`master`分支
  - 将当前分支代码`push`到远程仓库(git add . -> git commit -m "info" -> git push origin dev)

