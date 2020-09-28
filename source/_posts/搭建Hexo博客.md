---
title: 搭建hexo博客
date: 2020-09-28
---

记录搭建hexo博客的步骤。

默认安装好了node.js和git,如若没有:

[点击此处下载node.js](https://nodejs.org)

[点击此处下载git](https://git-scm.com)

<!-- more -->
### 基本功能
安装hexo
```sh
npm install hexo-cli.g
hexo init blog
cd blog

npm install hexo-deployer-git --save # 安装git插件
```

修改_config.xml
```yml
# URL
url: <your url>

# Deployment
depoly:
    type: git
    repo: git@<your repository>
```

初始化git
```sh
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

创建ssh秘钥
```sh
ssh-keygen -t rsa
cat /root/.ssh/id_rsa.pub # for Linux
type C:\\Users\<user's name>\.ssh\id_rsa.pub # for windows
```
简单命令
```sh
hexo s # server 创建本地服务器，打开https://localhost:4000即可查看
hexo g # generate 生成网页文件
hexo d # deploy 配置到github
hexo clean # 清理生成文件
```
### 主题相关
更换主题，以Next为例
```sh
git clone https://github.com/next-theme/hexo-theme-next themes/next
```

修改_config.xml
```yml
# Extensions
## Themes:
theme: next
```

配置主题themes/next/_config.yml。参见文档内注释即可


### 创建tags界面(categories同理)
```sh
hexo new page tags
```

在source/tags/index.md修改为
```markdown
---
title: tags
type: tags
---
```

### 数学模式

需要更换markdown引擎
```sh
npm uninstall hexo-renderer-marked --save
npm install hexo-renderer-kramed --save
```

在node_modules/kramed/lib/rules/inline.js中修改一些语义处理
```js
  //escape: /^\\([\\`*{}\[\]()#$+\-.!_>])/,
  escape: /^\\([`*\[\]()#$+\-.!_>])/,
  //em: /^\b_((?:__|[\s\S])+?)_\b|^\*((?:\*\*|[\s\S])+?)\*(?!\*)/,
  em: /^\*((?:\*\*|[\s\S])+?)\*(?!\*)/,
```

最后再在**主题配置**和**文件头**里打开mathjax即可

### 插图方式
打开本地配置_config.yml的开关
```yml
post_asset_folder: true
```

在source文件夹下建立images文件夹，将图片放于此文件夹下，引用时
```markdown
![<name>](/images/<pic-name>)
```

或者放在创建文章时的同名文件夹下，引用时直接使用名字

### 引用其他博文
将配置文件的永久链接修改为
```yml
permalink: :category/:title/
```
至此文件储存路径为"/目录/标题"，因此引用时可
```markdown
[](../<同级目录下的文件>)
[](/<绝对路径-目录>/<标题>)
```