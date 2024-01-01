---
title: Ubuntu安装Jekyll
author: Wilson
date: 2023-12-14 22:00:10 +0800
categories: [七零八落的爱好, Jekyll]
tags: [Jekyll]
pin: true
---


## 安装依赖

安装依赖项[永久链接](https://jekyllrb.com/docs/installation/ubuntu/#install-dependencies)

安装 Ruby 和其他[先决条件](https://jekyllrb.com/docs/installation/#requirements)：

```
sudo apt-get install ruby-full build-essential zlib1g-dev
```

避免以 root 用户身份安装 RubyGems 包（称为 gems）。相反，为您的用户帐户设置一个 gem 安装目录。以下命令会将环境变量添加到您的`~/.bashrc`文件中以配置gem安装路径：

```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

## 安装 Jekyll 和 Bundler（官方）

最后，安装 Jekyll 和 Bundler（此步为官方，直接看下面安装）：

```
gem install jekyll bundler
```

就是这样！您已准备好开始使用 Jekyll。

## 安装 Jekyll 和 Bundler（自定义）

```
git clone https://github.com/cotes2020/jekyll-theme-chirpy.git   #拉去代码
cd jekyll-theme-chirpy   #进入目录
ruby --version   #查看ruby版本
bundle install   #安装bundle
npm i && npm run build
jekyll s   #运行jekyll，默认端口号4000，自定义端口号 --port 4001
```

## Github推送文章

```
git remote -v   #查看当前远程仓库的详细信息
git remote remove origin   #移除当前远程仓库关联
git remote add origin git@github.com:nrjycyd/nrjycyd.github.io.git   #添加远程仓库关联
git push -u origin master   #第一次将本地仓库推送到远程仓库master分支
git status   #查看工作目录的状态
git add/rm <file>   #将更改的工作目录添加到暂存区，准备提交
git commit -m "add/rm <file>"   #描述此次提交的内容
git push   #将本地仓库的更改同步到远程仓库
```

### 参考文档

[Jekyll on Ubuntu (jekyllrb.com)](https://jekyllrb.com/docs/installation/ubuntu/)

[使用 Jekyll 部署 GitHub Pages_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1C14y187Nh/?spm_id_from=333.337.search-card.all.click&vd_source=429a3471dab07d1f8a77684b3a2ffe13)

