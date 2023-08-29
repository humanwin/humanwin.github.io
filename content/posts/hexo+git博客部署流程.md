---
title: 个人github博客部署过程
date: 2022-11-27 16:45:21
tags: 
    - 博客搭建
categories: 
    - 计算机
archives: 
    - 2022
---
## 配置github密钥
1. git config --global user.name "你的GitHub用户名"
2. git config --global user.email "你的GitHub注册邮箱"
3. ssh-keygen -t rsa -C "你的GitHub注册邮箱"
4. 将生成的pub公钥添加到github的key中
## 安装nodejs & hexo
1. 安装nodejs
   - 安装node-v18.12.1-x64.msi安装包（默认路径就可以）
   - 命令行执行node -v，查看是否安装成功
2. 安装hexo和搜索、图片、部署插件
   - npm install -g hexo-cli 
   - npm install hexo -g
   - npm install hexo-generator-search --save
   - npm install https://github.com/humanwin/hexo-asset-image.git
   - npm install hexo-deployer-git --save
## 初始化博客、主题
1. hexo init blog
2. cd blog
3. git clone https://github.com/next-theme/hexo-theme-next.git themes/next
## 初始化博文和配置
1. git clone https://github.com/humanwin/blog_article.git
2. 将其中的文件夹复制一份到blog文件夹中覆盖
## 博文流程
1. 无图博文
   - cd blog
   - hexo n "文章名"
   - 在_posts下会生成"文章名.md"
2. 有图博文
   - cd blog
   - hexo n "文章名"
   - 在_posts下会生成"文章名.md"，此外还要在_posts下新建和"文章名"同名的目录，图片放于目录中
## 验证 
1. hexo g
2. hexo s
## 推到到远端
1. hexo d
