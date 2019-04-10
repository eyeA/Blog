<center> 简单记录日常 </center>

### 1. 项目启动和运行方法
目前存在两个分支 `master` 和 `dev` <br>
其中：
- `master` 分支用来发布 `blog` 代码，也就是 `generate` 之后的项目文件；
- `dev` 分支用来本地编辑开发；
- 当前仓库的默认分支是 `dev` 分支，在 `dev` 分支开发完成后的步骤：
  - `hexo g` ==> 生成预览博客
  - `hexo s` ==> `4000` 端口本地预览博客
  - `hexo d` ==> 检查无误后，发布到仓库 `master` 分支(此时需要过几分钟刷新网站即可更新)
  - 将当前分支代码 `push` 到远程仓库 (此步骤保证多台设备你仍然可以使用这个项目，算是 `hexo` 的小坑)
    - `git add .`
    - `git commit -m "info"`
    - `git push origin dev`

### 2.添加文章的步骤
- 在 `dev` 分支下，


### 3.项目目录和说明
<small>参考文档: https://hexo.io/zh-cn/docs/setup </small>
-  _config.yml  // 网站的 配置 信息，您可以在此配置大部分的参数
- package.json  // 应用程序的信息
- scaffolds     // 模版 文件夹。当您新建文章时，Hexo 会根据 scaffold 来建立文件。
- source        // 资源文件夹是存放用户资源的地方。除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。
  - _drafts // 草稿
  - _posts  //
- themes       // 主题 文件夹。Hexo 会根据主题来生成静态页面
