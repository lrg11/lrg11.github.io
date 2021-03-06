---
title: 'Literature management'
date: 2022-04-05
permalink: /posts/2022/04/literature/
tags:
  - 文献管理
  - 交叉引用
  - Jabref
  - BibTeX
---


# 参考文献管理

## Word篇

### Method1 交叉引用

1. 将参考文献放在文末适当位置，自动编号，一般选用“[]”方括号。

2. 将光标定位到引用位置，点击“引用”—“交叉引用”。（可多次引用同一参考文献）
3. 引用类型和引用内容分别选择编号项、段落编号。
4. 更新。若在文献中间插入新文献，如在[2]，[3]之间插入，[3]会变为[4]，引用位置不会自动变，需选中所受影响文字，按F9，或右键更新域。
5. LBNL，引用位置的编号需上标，选择查找和替换，若编号个位数，在内容区域填 `\[[0-9]\]`，两位数填`\[[0-9]{1,2}\]`，选项中点击使用通配符，替换为填`^&`，在格式—字体中选择上标。
6. 或者，快捷键“Ctrl+H”打开查找与替换对话框，1-9输入`[^#]`，10以上输入 `[^#^#]`，"替换为"选择格式-字体-设置为上标----------全部替换。

### Word自带引文管理

任何引文管理软件，都是要**建库-导入文献-插入文献-设定style**。建库这一步既然比较难，那我们就交给Jabref去建库。

Jabref是严格按照BibTeX格式来进行建库和管理的。主流的学术搜索引擎都支持BibTeX的文献导出。

打开Jabref，新建一个库用来导入和管理参考文献。新建的这个库保存以后是以.bib为后缀的文件，下次继续打开它就打开了库文件。

![img](https://gitee.com/LonleyRong/markdown-pictures/raw/master/img/202204141146215.webp)

导入文献，和Endnote一样，支持多种导入方法。这里不多做介绍，这里介绍2种。可以通过DOI导入英文文献（中文文献不推荐），还可以就通过百度学术或谷歌学术或某个文章的页面直接导出为BibTeX，然后再通过Jabref导入库中。


特别提醒：BibTeX规范认为期刊的issue，也就是中文年卷期的“期”，在BibTeX为number。所以在每次导入的时候number就是那个issue。但是，bib文件一旦转化成其他库文件并导入其他软件，则会出问题，主要是issue缺失。因为其他软件都认为issue就是issue。所以这里有个大坑，先要设定好一个issue字段。找到Customize entry types。







然后给Article添加这个issue字段，并设定为required






 在每次导入的文献中，将number里的数字要手动填到issue里。（不好意思，似乎很扯淡，但我通过github和jabref官方发布了这个报错，他们不以为然，认为就是这样，你若用BibTeX就得用它的规范。）

把该加的参考文献全部导入bib库后，要导出给word使用，file-export-export all entries
 保存类型选择Office 2007。





这个导出来的xml文件，就是能兼容word的文献库了。目前只发现Jabref可以生成可以兼容word 的库，而你用Endnote等软件无论导出的是什么格式、什么样式，都无法导入到word中。

打开word文件（**必须是docx，doc文件不能使用**），引用-管理源-浏览-找到文件-复制



接着就像其他引文管理一样，可以插入引文了：点击插入引文。插完引文后，在文档末尾点击书目，即可把参考文献列在后面。





选择样式，这个样式 是 GB 7714。现在已开源，具体放的位置，参考码云项目。请改为Chinese test即可。
[文献样式](https://gitee.com/hao203/BibWord)






