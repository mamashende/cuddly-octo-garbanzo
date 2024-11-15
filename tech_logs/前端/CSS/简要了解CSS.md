https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured

将CSS应用于HTML的三种方法：使用外部样式表、使用内部样式表和使用内联样式

外部样式表将 CSS 包含在一个单独的文件中，该文件具有 `.css`扩展名。这是将 CSS 引入文档的最常见和最有用的方法。您可以将单个 CSS 文件链接到多个网页，并使用相同的 CSS 样式表设置所有网页的样式。


从 HTML `<link>` 元素引用外部 CSS 样式表：
```html
<!doctype html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8" />
    <title>My CSS experiment</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>

```
[`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) 元素的 `href` 属性需要引用文件系统上的文件。在上面的示例中，CSS 文件与 HTML 文档位于同一文件夹中，但您可以将其放置在其他位置并调整路径。下面有三个示例：

```html
<!-- Inside a subdirectory called styles inside the current directory -->
<link rel="stylesheet" href="styles/style.css" />

<!-- Inside a subdirectory called general, which is in a subdirectory called styles, inside the current directory -->
<link rel="stylesheet" href="styles/general/style.css" />

<!-- Go up one directory level, then inside a subdirectory called styles -->
<link rel="stylesheet" href="../styles/style.css" />

```

内部样式表位于 HTML 文档中。要创建内部样式表，请将 CSS 放在 HTML [`<head>` 中包含的](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) 元素中。在某些情况下，内部样式表可能很有用。例如，您可能正在使用一个内容管理系统，在该系统中，您被阻止修改外部 CSS 文件。但是对于具有多个页面的网站，内部样式表成为一种效率较低的工作方式。要使用内部样式表将统一的 CSS 样式应用于多个页面，您必须在每个将使用该样式的网页中都有一个内部样式表。效率损失也适用于现场维护。在内部样式表中使用 CSS，即使只是一个简单的样式更改也可能需要对多个网页进行编辑。

内联样式是影响包含在`样式`属性中的单个 HTML 元素的 CSS 声明。HTML 文档中内联样式的实现可能如下所示：



```html
<!doctype html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8" />
    <title>My CSS experiment</title>
  </head>
  <body>
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">
      Hello World!
    </h1>
    <p style="color:red;">This is my first CSS example</p>
  </body>
</html>
```

**尽可能避免以这种方式使用 CSS。**这与最佳实践相反。首先，它是CSS维护效率最低的实现。一次样式更改可能需要在单个网页中进行多次编辑。其次，内联 CSS 还将 （CSS） 表示代码与 HTML 和内容混合在一起，使所有内容更加难以阅读和理解。将代码和内容分开可以使所有在网站上工作的人更容易进行维护。