# LaTeX与Markdown（KaTeX）公式对比分析与优化方案

我帮你分析清楚「LaTeX公式和Markdown（KaTeX）公式」的核心差异，并给出**两种可直接复制的方案**，让你的LaTeX公式达到和图2一样的美观效果，甚至更专业。

---

## 🔍 核心差异分析

你觉得Markdown公式更美观，本质是这3点不同：

1. **数学字体**：Markdown的KaTeX默认使用**现代OpenType数学字体（如Latin Modern Math）**，而LaTeX默认的Computer Modern字体风格偏复古，符号圆润度、间距差异很大。

2. **排版紧凑度**：LaTeX默认的公式前后间距、行间距较大，而Markdown的公式和正文、公式内部的间距更协调。

3. **多行公式对齐**：图2的分部积分推导用了**自动对齐的多行公式环境**，而LaTeX如果只用`$$`，多行公式会松散、不对齐。

---

## 🎯 方案1：零成本快速优化（pdfLaTeX，不用换编译器）

无需修改TeXstudio的编译器，直接在导言区添加几行代码，就能让公式风格大幅贴近KaTeX。

### 完整可复制代码

```LaTeX

\documentclass{article}
\usepackage{ctex}       % 中文支持（pdfLaTeX下也能正常用）
\usepackage{lmodern}    % 加载和KaTeX几乎一致的Latin Modern字体
\usepackage{amsmath,mathtools} % mathtools是amsmath的增强版，优化公式排版
\usepackage{amsfonts,amssymb}  % 补充常用数学符号

% 关键：调整公式前后间距，和Markdown的紧凑感一致
\setlength{\abovedisplayskip}{8pt plus 2pt minus 2pt}
\setlength{\belowdisplayskip}{8pt plus 2pt minus 2pt}
\setlength{\abovedisplayshortskip}{6pt plus 2pt minus 2pt}
\setlength{\belowdisplayshortskip}{6pt plus 2pt minus 2pt}

% 调整数学字体大小，让公式和正文比例协调
\DeclareMathSizes{10}{10}{7}{5} % 正文10pt，公式10pt，下标7pt，次下标5pt

% 微调行高，避免公式太挤或太松
\renewcommand{\arraystretch}{1.1}

\begin{document}

和Markdown风格一致的分部积分推导：
\begin{align*}
I &= \int e^{-x}\sin x dx \\
&= -\int e^{-x} d(\cos x) \\
&= -\left( e^{-x}\cos x - \int \cos x d(e^{-x}) \right) \\
&= -e^{-x}\cos x - \int e^{-x} d(\sin x) \\
&= -e^{-x}\cos x - \left( e^{-x}\sin x - \int \sin x d(e^{-x}) \right) \\
&= -e^{-x}(\cos x + \sin x) - I \\
\intertext{两边移项整理：}
2I &= -e^{-x}(\cos x + \sin x) \\
I &= -\frac{1}{2}e^{-x}(\cos x + \sin x) + C
\end{align*}

你的周期积分公式也能完美适配：
\[
I = \int_{0}^{\infty} |\sin x| e^{-sx} dx = \frac{1}{1-e^{-sT}} \int_{0}^{T} |\sin x| e^{-sx} dx
\]

行列式公式也和KaTeX风格一致：
\[
\int e^{ax}\sin(bx)dx = \frac{1}{a^2+b^2} \begin{vmatrix} (e^{ax})' & (\sin bx)' \\ e^{ax} & \sin bx \end{vmatrix} + C
\]

\end{document}
```

---

## 🎯 方案2：完美复刻KaTeX效果（XeLaTeX/LuaLaTeX，推荐）

如果愿意把编译器换成XeLaTeX（TeXlive自带，无需额外安装），可以直接加载和KaTeX完全一致的OpenType数学字体，效果几乎一模一样，还能自定义中文字体，整体文档更协调。

### 完整可复制代码

```LaTeX

\documentclass{article}
\usepackage{ctex}       % 中文支持，XeLaTeX下完美适配
\usepackage{fontspec}
\usepackage{unicode-math} % 加载OpenType数学字体，和KaTeX底层一致

% 关键：设置和KaTeX完全一致的字体
\setCJKmainfont{Source Han Sans SC} % 中文字体用思源黑体，和Markdown编辑器风格匹配
\setmainfont{Latin Modern Roman}    % 英文字体
\setmathfont{Latin Modern Math}     % 数学字体，和KaTeX默认字体1:1复刻

\usepackage{mathtools}  % 优化多行公式排版

% 调整公式前后间距，和Markdown紧凑感一致
\setlength{\abovedisplayskip}{8pt plus 2pt minus 2pt}
\setlength{\belowdisplayskip}{8pt plus 2pt minus 2pt}
\setlength{\abovedisplayshortskip}{6pt plus 2pt minus 2pt}
\setlength{\belowdisplayshortskip}{6pt plus 2pt minus 2pt}

\renewcommand{\arraystretch}{1.1} % 微调公式行高

\begin{document}

完美复刻Markdown（KaTeX）的公式效果：
\begin{align*}
I &= \int e^{-x}\sin x dx \\
&= -\int e^{-x} d(\cos x) \\
&= -\left( e^{-x}\cos x - \int \cos x d(e^{-x}) \right) \\
&= -e^{-x}\cos x - \int e^{-x} d(\sin x) \\
&= -e^{-x}\cos x - \left( e^{-x}\sin x - \int \sin x d(e^{-x}) \right) \\
&= -e^{-x}(\cos x + \sin x) - I \\
\intertext{两边移项得：}
2I &= -e^{-x}(\cos x + \sin x) \\
I &= -\frac{1}{2}e^{-x}(\cos x + \sin x) + C
\end{align*}

\[
I = \int_{0}^{\infty} |\sin x| e^{-sx} dx = \frac{1}{1-e^{-sT}} \int_{0}^{T} |\sin x| e^{-sx} dx
\]

\end{document}
```

### TeXstudio设置说明

1. 打开 `选项 → 配置TeXstudio → 构建`

2. 将默认编译器从 `pdfLaTeX` 改为 `XeLaTeX`

3. 编译即可看到和Markdown几乎一致的效果

---

## ✨ 额外优化技巧（和图2效果完全对齐）

1. **多行推导式用** **`align*`** **环境**：

不要用多个独立的`$$`，而是用`align*`，等号会自动对齐，和图2的分部积分推导效果完全一致。

比如：

```LaTeX

\begin{align*}
u_k &= \int_{k\pi}^{(k+1)\pi} e^{-x} |\sin x| dx \\
&= (-1)^k \int_{k\pi}^{(k+1)\pi} e^{-x} \sin x dx
\end{align*}
```

1. **调整公式前后的段落间距**：

在导言区添加：

```LaTeX

\setlength{\parskip}{5pt} % 段落间距，和Markdown一致
\setlength{\parindent}{0pt} % 取消首行缩进，和Markdown更像（可选）
```

1. **用** **`\displaystyle`** **强制公式样式**：

如果行内公式也想和Markdown一样大，可以用`$\displaystyle \int e^{-x}\sin x dx$`，但不推荐全文档用，会影响排版。

---

## 📊 两种方案对比

|方案|编译器|效果|难度|
|---|---|---|---|
|方案1|pdfLaTeX|接近KaTeX，字体清晰，排版紧凑|零难度，直接复制|
|方案2|XeLaTeX|1:1复刻KaTeX效果，字体、间距完全一致|仅需修改编译器，10秒设置|
---

如果你愿意，我可以帮你把你图1里的所有公式，直接改成适配这两种方案的完整代码，你复制过去就能编译出和图2一样美观的效果。需要我帮你改吗？
> （注：文档部分内容可能由 AI 生成）