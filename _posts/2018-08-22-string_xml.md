---
layout:     post
title:      Android string.xml 输入
subtitle:   
date:       2018-08-22
author:     SLX 
header-img: img/post-bg-android.png
catalog: true
tags:
    - Android
    - Develop
---
Android string.xml输入

###特殊符号输入

string.xml文件里面如何输入特殊字符呢？

如果直接输入的话，xml文件会直接报错，这个时候，你可以使用HTML特殊符号表去查询对应十进制编码，替换成对应的编码，就可以使用了。

例如：

```
空格 &#160; @符号 &#064; :符号 &#058
```

###变量输入

string.xml文件里面可以写变量，然后由代码动态传入修改string的值。这样一方面xml修改的时候不需要修改传入的变量，修改变量的值也不需要修改xml文件，同时对多语言有着比较好的支持。

例如：
```
<string name="welcome_messages">Hello, %1$s! You have %2$d new messages.</string>
```
其中

%1$s 表示第一个占位符，s表示string

%2$d 表示第二个占位符，d表示数字

这时候只需要在代码里面传入对应到的值即可：
```
Resources res = getResources();
String text = String.format(res.getString(R.string.welcome_messages), username, mailCount);
```
###HTML输入
xml文件里面可以直接使用html标签，不论是\<b>的加粗还是\<i>的斜体还是\<u>的下划线
不过获取文字后设置的注意是通过html获取文字：
```
CharSequence styledText = Html.fromHtml(text);
```





