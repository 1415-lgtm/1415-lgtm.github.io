# hugo的使用教程



# 静态网页 HUGO

## 第一步安装HUGO

官网地址

[The world's fastest framework for building websites](https://gohugo.io/)

选择版本地址

[Releases · gohugoio/hugo](https://github.com/gohugoio/hugo/releases)

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled.png)

选择此版本

extended为扩展版本

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%201.png)

解压到自己指定的目录

## 第二步配置环境变量

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%202.png)

测试是否安装成功

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%203.png)

## 第三步新建项目(创建新站点)

hugo new site quickstart

```powershell
hugo new site 站点名
```

在你指定的目录创建新站点

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%204.png)

## 第四步安装主题

主题官网

[Complete List](http://themes.gohugo.io)

这里采用下载压缩包形式

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%205.png)

然后将hugo-theme-stack-master文件名修改为hugo-theme-stack

我用的主题地址

[GitHub - CaiJimmy/hugo-theme-stack: Card-style Hugo theme designed for bloggers](https://github.com/CaiJimmy/hugo-theme-stack)

 hugo-theme-stack里的exampleSite下的config.yaml和content复制到项目目录下

并把config.toml修改为下面这样

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%206.png)

## 第五步写入文章等数据

新建文章(新建一篇文章放到post目录，方便以后生成聚合页面)

```powershell
hugo new post/myfirst.md
```

## 第六步启用**启动 Hugo 服务器**

```powershell
hugo server -D
```

报错

```powershell
Start building sites …
hugo v0.100.1-0afb4866e345d31cbbcbab4349e43f1d36122806+extended windows/amd64 BuildDate=2022-06-01T10:11:48Z VendorInfo=gohugoio
Error: Error building site: "C:\CodeLearningLibrary\newhugo\studehugo\content\post\rich-content\index.md:38:4": failed to extract shortcode: template for shortcode "bilibili" not found
Built in 6 ms
```

删除所有模板 用{{}}扩起来的东西 包括括号

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%207.png)

```powershell
Start building sites …
hugo v0.100.1-0afb4866e345d31cbbcbab4349e43f1d36122806+extended windows/amd64 BuildDate=2022-06-01T10:11:48Z VendorInfo=gohugoio
WARN 2022/06/05 23:24:28 Search page not found. Create a page with layout: search.
WARN 2022/06/05 23:24:28 Archives page not found. Create a page with layout: archives.
WARN 2022/06/05 23:24:28 Search page not found. Create a page with layout: search.
WARN 2022/06/05 23:24:28 Archives page not found. Create a page with layout: archives.

                   | EN | ZH-CN | AR
-------------------+----+-------+-----
  Pages            | 47 |    17 | 20
  Paginator pages  |  1 |     0 |  0
  Non-page files   |  5 |     4 |  1
  Static files     |  0 |     0 |  0
  Processed images | 48 |    13 |  3
  Aliases          | 23 |     7 |  9
  Sitemaps         |  2 |     1 |  1
  Cleaned          |  0 |     0 |  0

Built in 942 ms
Watching for changes in C:\CodeLearningLibrary\newhugo\studehugo\{archetypes,content,data,layouts,static,themes}
Watching for config changes in C:\CodeLearningLibrary\newhugo\studehugo\config.yaml, C:\CodeLearningLibrary\newhugo\studehugo\themes\hugo-theme-stack\config.yaml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

![Untitled](%E9%9D%99%E6%80%81%E7%BD%91%E9%A1%B5%20HUGO%2037127814d5854d0a93512476419e810f/Untitled%208.png)

到这里 因为教程难以阅读 

所以我们使用另一个主题

主题地址

[LoveIt](https://themes.gohugo.io/themes/loveit/)

## 第七步 部署到网站上

第一步在GitHub上创建一个仓库

命名  xxx.github.io

第二步 迁移到仓库地址

```powershell
hugo --theme=LoveIt --baseUrl="[https://1415-lgtm.github.io/](http://1415-lgtm.github.io/)" -D
```

然后 进入创建好的public文件夹

```powershell
cd public
```

使用git  push到仓库

git init

git add .

git commit -m "first push”

git remote add origin [https://github.com/1415-lgtm/1415-lgtm.github.io.git](https://github.com/1415-lgtm/1415-lgtm.github.io.git)

git push -u origin master

后续更新

```powershell
hugo --theme=LoveIt --baseUrl="[https://1415-lgtm.github.io/](http://1415-lgtm.github.io/)" -D
```

git add .

git commit -m "first push update”

git push
