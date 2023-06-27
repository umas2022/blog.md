# 分类


- 参考：
  - https://zoharandroid.github.io/2019-08-02-Jekyll%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2%E6%B7%BB%E5%8A%A0%E5%88%86%E7%B1%BBCategory%E5%8A%9F%E8%83%BD/



- 首先md文件添加yaml前置格式

```yml
---
layout: post
title: awesome title
categories: Personal
---
```
- 多个类别直接用空格隔开就可以


- config.yaml
```yaml
# 默认是通过日期做子目录的方式
# permalink   : date
# 改为使用category做子目录
permalink: /:categories/:title/
```

- 未套用主题的默认项目在右上角about处添加新的按钮只需要在根目录下创建md或html文件即可，categories可以放在这里，yaml前置格式：
```yml
---
layout: page
title: Help
permalink: /help/
---
```

- 创建categories.html，内容如下
```html
---
layout: page
permalink: /categories/
title: categories
---

<div id="archives">
    <ul>
        {% for category in site.categories %}
          <li>
            <a href="{{ site.baseurl }}/{{ category | first | slugify }}">{{ category | first }}</a>
          </li>
        {% endfor %}
      </ul>
</div>
```


