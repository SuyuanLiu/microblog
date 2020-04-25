# Chapter 2: Templates

目的：分离 html 与 python 代码。更便于修改。

在代码文件夹下建立 templates 文件夹，代码会自动到这个文件夹下去找对应到 html 文件。

在 html 代码中，用 `{{}}` 标记出来的占位符 placeholder，表示变量，只有当代码运行时，才会知道里面对应的值具体是什么。

**渲染**：rendering，就是把 template 变为一个完整的 html 网页的操作。要完成渲染操作，需要 `from flask import render_template`。 render_template() 输入是模板文件名以及模板里面所需要的所有变量，返回的模板中占位符都被赋值。

render_template() 调用 Jinja2 模板引擎。Jinja2 用 render_template 给出的变量值来替代那些 `{{}}` 。

Jinja2 还支持 control statements，用 `{% ... %}` 模块。比如`if else`, `for` 等。

```python
{% if title %}
...
{% else %}
...
{% endif %}

{% for post in posts %}
<div><p>{{ post.author.username }} says: <b>{{ post.body }}</b></p></div>
{% endfor %}
```

**模板继承**：网页一般会有导航栏来链接常用的页面，如果每个页面的 html 代码里面都写上这些东西，就会造成重复冗余。可以把这个公共部分抽离出来，使用模板继承。这个例子中 base.html 是那部分公共代码，index.html 去继承 base，使用 `extends` 申明继承关系。同时在 base 中，用 `block` 来申明派生模板 index 可以嵌入自己代码的地方；`block` 后面的是可自定义的变量名。index 中也使用 `block + 变量名`模块，这样 jinja2 就可以将两个模板联系起来。
