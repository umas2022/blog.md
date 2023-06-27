# 用jekyll搭建的个人博客


## hello_world

- 项目：./1_example/jekyll/hello_umas


- 参考：
  - 官方：https://www.jekyll.com.cn/docs/
  - https://blog.csdn.net/qq_34967770/article/details/110098826


1. 安装Ruby
  - https://rubyinstaller.org/downloads/
  - 使用ruby -v 查看安装


2. 安装 Jekyll 和 bundler gems（要很久）
  ```
  gem install jekyll bundler
  ```

3. 创建并启动项目
  ```
  jekyll new hello_umas
  cd hello_umas
  bundle exec jekyll serve
  ```

4. 在浏览器中打开 http://localhost:4000 网址


5. 添加markdown文件
   - 在 Jekyll 项目的 _posts 目录下创建一个 Markdown 文件，文件名必须遵循 YYYY-MM-DD-title.md 的格式，其中 YYYY-MM-DD 表示文章的发布日期，title 表示文章的标题，文件名中的单词必须用短横线 - 分隔
   - 可以在md文件的头部添加解释文本
      ```
      ---
      layout: post
      title: awesome title
      categories: Personal
      ---
      ```
  - 多个类别可以categories: [Personal,python]

6. 创建模板
   - 在 Jekyll 项目的 _layouts 目录下创建一个文章模板，模板文件名可以任意取，通常命名为 post.html 或 article.html，并在文件中使用 {{ content }} 占位符表示文章内容
    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <title>{{ page.title }}</title>
      </head>
      <body>
        <h1>{{ page.title }}</h1>
        <p>{{ page.date | date_to_string }}</p>
        {{ content }}
      </body>
    </html>
    ```

7. build
    ```
    jekyll build --source source_dir --destination destination_dir
    ```
    - 这条命令将网页构建到_site文件夹中，之后可以托管在服务器上




## 其他功能

- 分类
  - 博客头部添加category或categories
  - 在_posts文件夹下添加多级文件夹


- 草稿
  - 创建_drafts文件夹


- 数据文件
  - _data文件夹，内容可以通过site.data.members访问
  - 可以使用.yml、.yaml、.json、csv


- 全局配置：_config.yaml
```yaml
#网站根目录
baseurl: /docs

# 生成的文件路径
destination: ../../dist/docs

# 分页
permalink: /:year/:month/:day/:title.html
paginate: 1
paginate_path: "article/:num"

# 转换
markdown: kramdown
highlighter: rouge
excerpt_separator: <!--excerpt-->

gems: ['jekyll-paginate']

exclude: ['open.bat','Gemfile','Gemfile.lock','Guardfile', 'gulpfile.js']

# Collections
collections:
 common:
  output: true
  permalink: /:collection/:title
 ui:
  output: true
  permalink: /:collection/:title
```


## 可能的问题


1. 启动服务器时报错一个语法错误

244 │     padding: ($spacing-unit / 3) ($spacing-unit / 2);
    │               ^^^^^^^^^^^^^^^^^

不影响服务器的启动，没找到解决办法


## 附录

- 以下是gpt推荐的支持markdown的博客框架：

Jekyll：Jekyll 是一个简单、易用、支持 Markdown 的静态网站生成器，它能够将 Markdown 文件转换成静态的 HTML 网页。Jekyll 的优点在于它易于安装和使用，并且支持 GitHub Pages，可以免费托管网站。

Hexo：Hexo 是一个快速、简洁且高效的博客框架，它基于 Node.js 平台，支持 Markdown 语法，可以生成静态的 HTML 文件。Hexo 的优点在于它的速度非常快，而且支持插件扩展，可以实现更多的功能。

Hugo：Hugo 是一个快速、灵活、易用的静态网站生成器，它支持 Markdown 语法，并且可以生成静态的 HTML 文件。Hugo 的优点在于它的速度非常快，而且支持多种主题和插件，可以满足不同的需求。

Gatsby：Gatsby 是一个基于 React 的静态网站生成器，它支持 Markdown 语法，并且可以生成静态的 HTML 文件。Gatsby 的优点在于它支持多种数据源，可以从多种数据源中获取数据，而且支持多种插件和主题，可以实现更多的功能。