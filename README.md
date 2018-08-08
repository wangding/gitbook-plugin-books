# 综合性的一个插件

由于本人经常性的写一些文档，然后现有的很多插件版本各方面存在问题，甚至还有一些作者已经放弃维护了，所以决定自己写一个综合性的插件用来满足个人需求。

本插件只在 Windows 系统下进行测试，Linux 等其他环境不保证问题的存在！！！

>本插件仅支持 html 文档生成

本人环境【Windows 10 64bit，nodejs v8.11.3，gitbook 3】。

## 前置条件

使用 `npm root -g`查看`npm`全局模块安装路径。

新建`NODE_PATH`环境变量。

将路径加入到`NODE_PATH`环境变量中。

全局安装相应模块。

```bash
npm install -g books-cli
```

## 编辑 book.json

```json
{
  "plugins": [
    "-lunr",
    "-search",
    "-highlight",
    "-sharing",
    "books"
  ]
}
```

运行 `gitbook install`.

## 数学公式使用

支持 [KaTeX](https://khan.github.io/KaTeX/docs/supported.html) 已支持的全部符号。

```html
内联数学公式：$$\int_{-\infty}^\infty g(x) dx$$

$$\fcolorbox{red}{aqua}{A}$$

$$\textcolor{#228B22}{F=ma}$$

块级数学公式:

$$
\def\arraystretch{1.5}
\begin{array}{c|c:c}
   a & b & c \\ \hline
   d & e & f \\
   \hdashline
   g & h & i
\end{array}
$$
```

## 流程图使用

支持 [mermaid](https://mermaidjs.github.io/) 以支持的流程图。

    ```mermaid
    graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
    ```

## 代码高亮支持

采用 [prism](https://prismjs.com/) 支持所有官方支持语言。

### 主题样式

支持官方所有主题

`prismjs/themes/prism.css`

`prismjs/themes/prism-coy.css`

`prismjs/themes/prism-dark.css`

`prismjs/themes/prism-funky.css`

`prismjs/themes/prism-okaidia.css`

`prismjs/themes/prism-solarizedlight.css`

`prismjs/themes/prism-tomorrow.css`

`prismjs/themes/prism-twilight.css`

```json
"pluginsConfig": {
  "books": {
    "themes": [
      "prismjs/themes/prism-okaidia.css"
    ]
  }
}
```

## 添加 github url 图标

```json
"pluginsConfig": {
  "books": {
    "url": "https://liushilive.github.io/"
  }
}
