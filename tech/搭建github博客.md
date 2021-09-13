# 安装nodejs
windows上安装nodejs

# 安装Hexo
```bash
npm i hexo-cli -g # 安装Hexo
hexo -v #验证是否成功
hexo init #切换到对应的目录，然后初始化文件夹
npm install #安装必要组件
hexo g #生产静态网页
hexo s #打开本地服务器，然后浏览器打开localhost:4000预览博客
```

# 连接github到本地
首先登录自己的github，创建GitHub Pages
```bash
git config --global user.name "xxx" #配置github账户
git config --global user.email "xxx"
#复制公钥到github
```

# 修改hexo的配置文件
修改hexo目录下的配置文件：_config.yml
```yaml
deploy:
  type: git
  repository: https://github.com/xxx/xxx.github.io
  branch: master
```

# 写文章、发布文章
```bash
npm i hexo-deployer-git #安装扩展
hexo new post "name of you title" #新建文章并编辑，文件位于\source\_posts
hexo g #生产静态网页
hexo s #打开本地服务器并预览静态网页
hexo d #上传到github
```