---
title: latex使用记录
date: 2024-10-31 12:51:58
tags:
---
1. 参考文献
在tex同级目录添加.bib文件，其中填写引用格式的bibtex
1.1 在导言部分加
\usepackage{cite}  //引用要加的包
\usepackage[hidelinks]{hyperref} //去掉引用效果绿框和链接跳转
\usepackage[numbers,sort\&compress]{natbib}//多个文献引用

多文献引用格式:[1,2].   \cite{label1,label2}

多文献引用格式:[1,2][1-3]只有是三片文献以上才是连字符.  \usepackage[numbers,sort&compress]{natbib}我所知道的是这是一种压缩的格式.

1.2 在参考文献出现的位置
\bibliographystyle{unsrt} //按出现顺序编号参考文献
\bibliography{ref}//导入刚才的bib文件

2. 图片跨栏居中
方法：使用 figure* 环境
在双栏文档中，将 figure 环境替换为 figure*，并将浮动参数设为 [t] 或 [b]，以控制图片出现在页面顶部或底部。

\begin{figure*}[t] % 使用 figure* 环境，并设置 [t] 或 [b] 控制位置
    \centering
    \includegraphics[width=\textwidth]{your-image.png} % 设置图片宽度为整页宽度
    \caption{Your Caption}
    \label{fig:your-label}
\end{figure*}

3. 图片索引居中
\usepackage[caption=true,font=normalsize,labelfont=sf,textfont=sf]{subfig}
模板默认是false
caption=true改成true就行了

Tip:有时会出现编译不成功的问题，只要在空白的地方随便打打即可重新编译成功；照片的位置好像不能指定；照片可以在label重新命名。