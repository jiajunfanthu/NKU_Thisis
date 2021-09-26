# NKU_Thisis
南开人工智能学院毕业设计模板（优秀毕业设计）


# 初衷

我在大四做毕业设计的时候，老师只给了我们word的模板。不过我们一些工科类学院的毕业论文常常需要打许多的公式，
所以latex可能更适合我们。所以为了帮助南开人工智能学院的同学能够更方便的写出优秀的论文，
这里我提供一套latex的模板，希望能够对大家有所帮助，也希望我们学院能够越来越好。


有啥问题可以这里提issue，发邮件或者微信找我，我的联系方式可见[Jiajun Fan](https://www.jiajunfan.com)

这里为了便于共享我把附录删除了。原文可见[My Thisis](https://www.overleaf.com/6951136389yrzcxnqfympn)
# 使用方法
## 文件说明


```main.tex``` 包含封面信息和所需要的头文件（封面格式我调了好久）。


```abstract.tex``` 主要写中英文摘要和关键词。

```manual.tex``` 是论文的正文和附录，大部分内容都在这里写。


```acknowledgements.tex``` 主要写致谢相关的信息。

```references.tex``` 这个文件不用管

```resume.tex``` 主要写自己的个人简历

```nkthesis.bib``` 主要以bib的格式放置参考文献（推荐这样管理参考文献）

温馨提示：如果觉得这个封面确实比较丑，可以用word单独写一个封面然后用smallpdf把这个封面删了，然后和word导出的pdf封面拼一下。
## 本文件使用方法
2021年9月26日以下流程测试没问题。

1. github下载为zip格式压缩包
2. 打开overleaf新建一个Project，并且选择upload Project
3. 等待编译，然后开始happy！

当然你也可以直接copy这个[My Thisis](https://www.overleaf.com/6951136389yrzcxnqfympn)

## Latex基本语法

插入图片
```latex
\begin{figure}[!t]
	\centering
	\subfigure{
		\centering
		\includegraphics[scale=0.5]{图片路径：photo/chapter2/MDP.pdf}
% 		\caption{fig2}
	}%
	\caption{图片名字：马尔科夫在决策时间处理过程中的各种智能机器人之间的交互流程示意图}
	\label{图片标记（用于文章引用）：Fig:MDP}
\end{figure}
```

插入表格（语法和图片类似）

```latex
\begin{table}[!tp]
    \caption{强化学习基础方法的特点}
    
	\centering
	\begin{tabular}{c||c ||c }
    \hline
    方法类别&优点 & 缺点\\
    \hline
    无模型方法&\parbox{.4\linewidth}{\begin{enumerate}
      \item 可以适应环境动态转移\textbf{\eqref{Equ:environment_transistion}}未知的情况。
      \item 可以处理更大的状态空间的环境。
    \end{enumerate}} & \parbox{.3\linewidth}{\begin{enumerate}
      \item 需要较强的探索。
    \end{enumerate}}\\
    
    \hline

    同策略方法&\parbox{.4\linewidth}{\begin{enumerate}
      \item 使用函数逼近器时更加稳定。
      \item 适合解决连续状态空间的问题。
    \end{enumerate}} & \parbox{.3\linewidth}{\begin{enumerate}
      \item 必须采用随机策略。
     
    \end{enumerate}}\\
    
    \hline
    
    异策略方法&\parbox{.4\linewidth}{\begin{enumerate}
      \item 算法实现和设计简单。
      \item 可以解决不同种类的问题。
      \item 可以使用确定性策略。
    \end{enumerate}} & \parbox{.3\linewidth}{\begin{enumerate}
      \item 使用函数逼近器时效果不稳定。
    \end{enumerate}}\\
    
    \hline
    自举方法&\parbox{.4\linewidth}{\begin{enumerate}
      \item 在很多任务中学习更快。
    \end{enumerate}} & \parbox{.3\linewidth}{\begin{enumerate}
      \item 无法解决环境未知的任务。
    \end{enumerate}}\\

    \hline
    \end{tabular}
    \label{Table: adv and disadv on RL method}
    
\end{table}

```


插入代码

```latex
\begin{algorithm}[h]
	\caption{Q-learning强化学习方法}
	\label{alg:Q-learning}
	\begin{algorithmic}[1]
		\STATE{初始化Q函数，策略$\pi$}
		\FOR{ 每一条轨迹$\tau$}
		\STATE{初始化环境状态$s_t$}
		\WHILE{$s_t$不是终止状态}
		\STATE{根据当前的策略$\pi$和行为函数$Q$状态$S_t$处选择动作$a_t$}
		\STATE{执行动作$a_t$}
		\STATE{获取回报$r_{t+1}$和状态$s_{t+1}$}
		\STATE{根据\textbf{式\eqref{Equ: q-learning update}}更新Q函数}
		\STATE{$s_t=s_{t+1}$}
		\ENDWHILE
		\ENDFOR
	\end{algorithmic}
	\hspace*{0.02in} {\bf 输出:} $\pi^{*},Q^{*}$
\end{algorithm}
```
