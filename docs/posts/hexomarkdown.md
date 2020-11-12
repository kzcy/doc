## 创建文章

在站点文件夹中打开 git bash，输入如下命令创建文章，其中 `title` 为文章的标题
```bash
hexo new “title”*
```
当输入命令后，就会在 `source/_post` 文件夹下创建一个文件，命名为：`title.md`
这个文件就是将要发布到网站上的原始文件，用于记录文章内容。

<!--more-->

## 编写文章

### Markdown 简介
*Markdown 是一种可以使用普通文本编辑器编写的 **标记语言**，通过简单的 **标记语法**，它可以使普通文本内容具有一定的格式*

### Markdown语法

#### Typora 快捷键：

Ctrl+1：一级标题
Ctrl+2：二级标题
Ctrl+3：三级标题
Ctrl+4：四级标题
Ctrl+5：五级标题
Ctrl+6：六级标题
Ctrl+0：段落

#### Markdown 语法：
```markdown
*斜体*
**粗体**
***加粗斜体***
~~删除线~~
```

**Typora 快捷键：**
Ctrl+I：斜体
Ctrl+B：粗体
Ctrl+U：下划线
Alt+Shift+5：删除线

### 引用块

#### 文字引用

> **Markdown 语法：**
>
> 在Typora中输入””” + 回车，并在后面选择一个语言名称即可语法高亮。
>
> > 语法高亮:
> >
> > ```python
> > > > > def helloWorld():
> > > > > 	print 'hello, world'
> > > > > 
> > > >
> > ```

#### 表

> 输入`| 表头1 | 表头2 |`并回车。即可将创建一个包含两列的表，然后就像操作Word文档一样设置表格即可，没必要知道Markdown的复杂语法，因为这些语法会由Typora自动生成。效果如下：
>
> | First Header | Second Header |
> | :----------- | :------------ |
> |              |               |

#### 分割线

> 输入`***`或`---` 再按回车即可绘制一条水平线，如下：
>
> ------
>
> 链接
>
> 内部链接
>
> > 这是一个带有标题属性的[链接](http://naka.club/).
> > 这是一个没有标题属性的[链接](https://www.dazhuanlan.com/2019/12/14/5df3b9db55a34/naka.club/)
>
> 效果如下：
>
> 这是一个带有标题属性的[链接](http://example.com/).
> 这是一个没有标题属性的[链接](http://example.net/)
>
> Typora 快捷键：**
>
> 行内代码：Ctrl+Shift+`
>
> 多行代码：Ctrl+Shift+K

#### 代码标记

> 标记代码使用反引号，即在英文输入法下，ESC键下面和1键左边的符号——`
>
> 使用该`printf()`功能。
> 效果如下：
> 使用该`printf()`功能。

#### 删除线(中间没有空格)

> ~ ~删除线~ ~

> 效果如下：
>
> ~~删除线~~

#### 下划线

> 下划线
>
> 效果如下：
>
> 下划线

### 内置样式

#### 分割线和空行

> 这是文字
>
> ```python
> > <hr />
> >
> ```

> 上面是分隔线
>
> ```python
> > <br />
> >
> ```

> 上面是空行



### 文本居中的引用

此标签将生成一个带上下分割线的引用，同时引用内文本将自动居中。 文本居中时，多行文本若长度不等，视觉上会显得不对称，因此建议在引用单行文本的场景下使用。 例如作为文章开篇引用 或者 结束语之前的总结引用。

#### 使用方式

- HTML方式：使用这种方式时，给 `img` 添加属性 `class="blockquote-center"` 即可。
- 标签方式：使用 `centerquote` 或者 简写 `cq`。

此标签要求 NexT 的版本在 **0.4.5** 或以上。 若你正在使用的版本比较低，可以选择使用 `HTML` 方式。

**标签调用方法**

```php+HTML
<!-- HTML方式: 直接在 Markdown 文件中编写 HTML 来调用 -->
<!-- 其中 class="blockquote-center" 是必须的 -->
<blockquote class="blockquote-center">blah blah blah</blockquote>

<!-- 标签 方式，要求版本在0.4.5或以上 -->
{% centerquote %}blah blah blah{% endcenterquote %}

<!-- 标签别名 -->
{% cq %} blah blah blah {% endcq %}
```

#### 效果示例

![Center Blockquote Tag](http://theme-next.iissnan.com/uploads/tags/blockquote-center.png)

### 突破容器宽度限制的图片

当使用此标签引用图片时，图片将自动扩大 26%，并突破文章容器的宽度。 此标签使用于需要突出显示的图片, 图片的扩大与容器的偏差从视觉上提升图片的吸引力。 此标签有两种调用方式（详细参看底下示例）：

#### 使用方式

- HTML方式：使用这种方式时，为 `img` 添加属性 `class="full-image"`即可。
- 标签方式：使用 `fullimage` 或者 简写 `fi`， 并传递图片地址、 `alt` 和 `title` 属性即可。 属性之间以逗号分隔。

此标签要求 NexT 的版本在 **0.4.5** 或以上。 若你正在使用的版本比较低，可以选择使用 `HTML` 方式。
如果要在图片下显示图片的标题，请使用 标签方式 并给定 `title` 属性。

 **标签调用方法**

```php+HTML
<!-- HTML方式: 直接在 Markdown 文件中编写 HTML 来调用 -->
<!-- 其中 class="full-image" 是必须的 -->
<img src="/image-url" class="full-image" />

<!-- 标签 方式，要求版本在0.4.5或以上 -->
{% fullimage /image-url, alt, title %}

<!-- 别名 -->
{% fi /image-url, alt, title %}
```

#### 效果示例

![img](http://theme-next.iissnan.com/uploads/tags/full-image.jpg)

### Bootstrap Callout 

由 [ivan-nginx](https://github.com/iissnan/hexo-theme-next/pull/1160) 贡献
这些样式出现在 [Bootstrap 的官方文档](http://getbootstrap.com/)中。

#### 使用方式

```php+HTML
{% note class_name %} Content (md partial supported) {% endnote %}
```

其中，`class_name` 可以是以下列表中的一个值：

- `default`
- `primary`
- `success`
- `info`
- `warning`
- `danger`

#### 效果示例

![img](https://gitee.com/kzcy/pic/raw/master/img/bootstrap-callout.png)


#### 参考资料
  1.  https://www.dazhuanlan.com/2019/12/14/5df3b9db55a34/
  2.  http://theme-next.iissnan.com/tag-plugins.html
