Demo: <csh.farbox.com>

### About the theme
一个用了[bootswatch](http://bootswatch.com/)里面的样式的`farbox`主题。[bootswatch](http://bootswatch.com/)是一个基于[bootstrap](http://getbootstrap.com/)的开源主题站。

依据[Ubuntu for Farbox](http://lanbing.org/post/Ubuntu4Farbox.html)修改，直接用了[Spacelab](http://bootswatch.com/spacelab/)的`css`样式。神马`bootstrap`完全不懂，完全是套样式，代码在[这里](https://github.com/river2008000/farbox_template_Spacelab_Bootswatch)。可以很明显的看出`bootstrap`的痕迹，[这里](http://wrapbootstrap.com)有更好看的主题。

### Some Features
 - `CSS`文件里面有一些对`html`文本标签的支持，可以直接插入`html`代码段来使用。如`Emphasis classes`:
    -  <p class="text-muted">Fusce dapibus, tellus ac cursus commodo, tortor mauris nibh.</p>
    - <p class="text-primary">Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
    - <p class="text-warning">Etiam porta sem malesuada magna mollis euismod.</p>
    - <p class="text-danger">Donec ullamcorper nulla non metus auctor fringilla.</p>
    - <p class="text-success">Duis mollis, est non commodo luctus, nisi erat porttitor ligula.</p>
    - <p class="text-info">Maecenas sed diam eget risus varius blandit sit amet non magna.</p>

   所用代码为：

```html
<p class="text-muted">Fusce dapibus, tellus ac cursus commodo, tortor mauris nibh.</p>
<p class="text-primary">Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
<p class="text-warning">Etiam porta sem malesuada magna mollis euismod.</p>
<p class="text-danger">Donec ullamcorper nulla non metus auctor fringilla.</p>
<p class="text-success">Duis mollis, est non commodo luctus, nisi erat porttitor ligula.</p>
<p class="text-info">Maecenas sed diam eget risus varius blandit sit amet non magna.</p>
```

 - 还有右对齐的`Blockquotes`:

<blockquote class="pull-right">
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <small>Someone famous in <cite title="Source Title">Source Title</cite></small>
</blockquote>
代码为

```html
<blockquote class="pull-right">
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <small>Someone famous in <cite title="Source Title">Source Title</cite></small>
</blockquote>
```
 - 完整示例见[spacelab](http://bootswatch.com/spacelab/)

### 更改样式：
 - [bootswatch](http://bootswatch.com/)里面还有很多其他的颜色样式，需要更改把对应的`css`文件`bootstrap.css`和`bootstrap.min.css`用相应主题的css文件替换掉即可。
 - 导航栏用的都是`inverse`样式(如<http://bootswatch.com/cyborg/>中靠下的导航栏)。如果要改成`default`样式，把`base.html`中20,24,31行的`inverse`替换为`default`。
 - 导航栏是固定在顶部的，取消固定把`base.html`第20行中的`navbar-fixed-top`去掉。同时去掉`css`文件夹下`adjust.css`中的`padding-top: 70px;`

### PS
加载的`mathjax`脚本会导致页面加载变得很慢，不写数学公式的就删了。

## Update in 2014-03-14
 - 增加了[Bootswatch](http://bootswatch.com/)里的所有样式。通过`site.md`里的`theme`和`themeset`配置，类似
```
theme: Readable
themeset: default
```
 - 添加了[DOC](http://doc.farbox.com/)部分，访问`http://yoururl/read`的时候会有一个类似<http://doc.farbox.com/>的页面，这个页面的文档要置于**docs**文件夹下面，而且**一定在`metadata`要添加`status: doc`**，否则会出现在post列表。
 - 主页的`page`会读取标记了`status: inline`的post, 然后作为静态页面插入到`index.html`中，这类`post`要增加`status: inline`标签，和`url: balabala`，并且用`position`制定次序。PS: `page`是内嵌到`index.html`中的。
 - `Links`部分在`site.md`下设置，否者默认会指向本站。

## Update in 2014-03-22
 - 去掉导航栏的`docs`链接，但是通过`http://yourdomain/read`还是可以访问到。
 - 增加顶部导航栏是否固定的选项: `themefixed: yes`即为固定，其他或者没有都是不固定。

## Site.md配置
**由于Links的设置，一定要使用YAML格式**，示例如下:
```yaml
---
rpost: 6 # 这里是sidebar最近文章的数目
post_per_page: 6 # 这里是分页的每页post数量
duoshuo: xxxxx # 多说账号，评论系统只有多说的
subtitle: People die # subtitle 用不上
keywords: 你的网站keyword
description: 你的网站description
links: 
 - title: 百度 # 链接名称
   url: http://www.baidu.com/ # 链接地址
   description: 百度搜索 # descreption是可选项
 - title: Google
   url: http://www.google.com
theme: Readable # Bootswatch上的主题，注意大小写
themeset: default # 导航栏的样式，有default和inverse
themefixed: yes # yes为固定顶部导航栏
---
```
