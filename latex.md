> Cmd Markdown 编辑阅读器支持 ![\LaTeX](https://math.jianshu.com/math?formula=%5CLaTeX) 编辑显示支持，例如：![\sum_{i=1}^n a_i=0](https://math.jianshu.com/math?formula=%5Csum_%7Bi%3D1%7D%5En%20a_i%3D0)，访问 [MathJax](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference) 以参考更多使用方法。

> 右键点击每一个公式，选择 **[Show Math As] → [TeX Commands]** 以查看该公式的命令详情。

[TOC]

------

# 一、公式使用参考

## 1．如何插入公式

![\LaTeX](https://math.jianshu.com/math?formula=%5CLaTeX) 的数学公式有两种：行中公式和独立公式。行中公式放在文中与其它文字混编，独立公式单独成行。

行中公式可以用如下方法表示：



```ruby
    $ 数学公式 $
```

独立公式可以用如下方法表示：



```ruby
   $$ 数学公式 $$
```

自动编号的公式可以用如下方法表示：
 :    若需要手动编号，参见 [大括号和行标的使用](#14大括号和行标的使用) 。



```ruby
      \begin{equation}
数学公式
\label{eq:当前公式名}
\end{equation}
```

**自动编号后的公式可在全文任意处使用 `\eqref{eq:公式名}` 语句引用。**

- 例子：



```latex
$ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text {，行内公式示例} $
```

- 显示：![J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text {，行内公式示例}](https://math.jianshu.com/math?formula=J_%5Calpha(x)%20%3D%20%5Csum_%7Bm%3D0%7D%5E%5Cinfty%20%5Cfrac%7B(-1)%5Em%7D%7Bm!%20%5CGamma%20(m%20%2B%20%5Calpha%20%2B%201)%7D%20%7B%5Cleft(%7B%20%5Cfrac%7Bx%7D%7B2%7D%20%7D%5Cright)%7D%5E%7B2m%20%2B%20%5Calpha%7D%20%5Ctext%20%7B%EF%BC%8C%E8%A1%8C%E5%86%85%E5%85%AC%E5%BC%8F%E7%A4%BA%E4%BE%8B%7D)
- 例子：



```ruby
$$ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text {，独立公式示例} $$
```

- 显示：

  $$
  J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text{独立公式}
  $$
  

- 例子：



```ruby
在公式 \eqref{eq:sample} 中，我们看到了这个被自动编号的公式。

\begin{equation}
E=mc^2 \text{，自动编号公式示例}
\label{eq:Sample}
\end{equation}
```

- 显示：

在公式 \eqref{eq:sample} 中，我们看到了这个被自动编号的公式。
$$
\begin{equation} E=mc^2 \text{，自动编号公式示例} \label{eq:sample} \end{equation}
$$


## 2．如何输入上下标

`^` 表示上标, `_` 表示下标。如果上下标的内容多于一个字符，需要用 `{}` 将这些内容括成一个整体。上下标可以嵌套，也可以同时使用。

- 例子：



```ruby
$$ x^{y^z}=(1+{\rm e}^x)^{-2xy^w} $$
```

- 显示：![x^{y^z}=(1+{\rm e}^x)^{-2xy^w}](https://math.jianshu.com/math?formula=x%5E%7By%5Ez%7D%3D(1%2B%7B%5Crm%20e%7D%5Ex)%5E%7B-2xy%5Ew%7D)

另外，如果要在左右两边都有上下标，可以用 `\sideset` 命令。

- 例子：



```ruby
$$ \sideset{^1_2}{^3_4}\bigotimes $$
```

- 显示：![\sideset{^1_2}{^3_4}\bigotimes](https://math.jianshu.com/math?formula=%5Csideset%7B%5E1_2%7D%7B%5E3_4%7D%5Cbigotimes)

## 3．如何输入括号和分隔符

`()`、`[]` 和 `|` 表示符号本身，使用 `\{\}` 来表示 `{}` 。当要显示大号的括号或分隔符时，要用 `\left` 和 `\right` 命令。

一些特殊的括号：

|  输入   |                            显示                             |  输入   |                            显示                             |
| :-----: | :---------------------------------------------------------: | :-----: | :---------------------------------------------------------: |
| \langle | ![\langle](https://math.jianshu.com/math?formula=%5Clangle) | \rangle | ![\rangle](https://math.jianshu.com/math?formula=%5Crangle) |
| \lceil  |  ![\lceil](https://math.jianshu.com/math?formula=%5Clceil)  | \rceil  |  ![\rceil](https://math.jianshu.com/math?formula=%5Crceil)  |
| \lfloor | ![\lfloor](https://math.jianshu.com/math?formula=%5Clfloor) | \rfloor | ![\rfloor](https://math.jianshu.com/math?formula=%5Crfloor) |
| \lbrace | ![\lbrace](https://math.jianshu.com/math?formula=%5Clbrace) | \rbrace | ![\rbrace](https://math.jianshu.com/math?formula=%5Crbrace) |

- 例子：



```ruby
$$ f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right) $$
```

- 显示：![f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right)](https://math.jianshu.com/math?formula=f(x%2Cy%2Cz)%20%3D%203y%5E2z%20%5Cleft(%203%2B%5Cfrac%7B7x%2B5%7D%7B1%2By%5E2%7D%20%5Cright))

有时候要用 `\left.` 或 `\right.` 进行匹配而不显示本身。

- 例子：



```swift
$$ \left. \frac{{\rm d}u}{{\rm d}x} \right| _{x=0} $$
```

- 显示：![\left. \frac{{\rm d}u}{{\rm d}x} \right| _{x=0}](https://math.jianshu.com/math?formula=%5Cleft.%20%5Cfrac%7B%7B%5Crm%20d%7Du%7D%7B%7B%5Crm%20d%7Dx%7D%20%5Cright%7C%20_%7Bx%3D0%7D)

## 4．如何输入分数

通常使用 `\frac {分子} {分母}` 命令产生一个分数，分数可嵌套。
 便捷情况可直接输入 `\frac ab` 来快速生成一个 ![\frac ab](https://math.jianshu.com/math?formula=%5Cfrac%20ab) 。
 如果分式很复杂，亦可使用 `分子 \over 分母` 命令，此时分数仅有一层。

- 例子：



```ruby
$$\frac{a-1}{b-1} \quad and \quad {a+1\over b+1}$$
```

- 显示：![\frac{a-1}{b-1} \quad and \quad {a+1\over b+1}](https://math.jianshu.com/math?formula=%5Cfrac%7Ba-1%7D%7Bb-1%7D%20%5Cquad%20and%20%5Cquad%20%7Ba%2B1%5Cover%20b%2B1%7D)

## 5．如何输入开方

使用 `\sqrt [根指数，省略时为2] {被开方数}` 命令输入开方。

- 例子：



```cpp
$$\sqrt{2} \quad and \quad \sqrt[n]{3}$$
```

- 显示：![\sqrt{2} \quad and \quad \sqrt[n]{3}](https://math.jianshu.com/math?formula=%5Csqrt%7B2%7D%20%5Cquad%20and%20%5Cquad%20%5Csqrt%5Bn%5D%7B3%7D)

## 6．如何输入省略号

数学公式中常见的省略号有两种，`\ldots` 表示与文本底线对齐的省略号，`\cdots` 表示与文本中线对齐的省略号。

- 例子：



```ruby
$$f(x_1,x_2,\underbrace{\ldots}_{\rm ldots} ,x_n) = x_1^2 + x_2^2 + \underbrace{\cdots}_{\rm cdots} + x_n^2$$
```

- 显示：![f(x_1,x_2,\underbrace{\ldots}_{\rm ldots} ,x_n) = x_1^2 + x_2^2 + \underbrace{\cdots}_{\rm cdots} + x_n^2](https://math.jianshu.com/math?formula=f(x_1%2Cx_2%2C%5Cunderbrace%7B%5Cldots%7D_%7B%5Crm%20ldots%7D%20%2Cx_n)%20%3D%20x_1%5E2%20%2B%20x_2%5E2%20%2B%20%5Cunderbrace%7B%5Ccdots%7D_%7B%5Crm%20cdots%7D%20%2B%20x_n%5E2)

## 7．如何输入矢量

使用 `\vec{矢量}` 来自动产生一个矢量。也可以使用 `\overrightarrow` 等命令自定义字母上方的符号。

- 例子：



```ruby
$$\vec{a} \cdot \vec{b}=0$$
```

- 显示：![\vec{a} \cdot \vec{b}=0](https://math.jianshu.com/math?formula=%5Cvec%7Ba%7D%20%5Ccdot%20%5Cvec%7Bb%7D%3D0)
- 例子：



```ruby
$$\overleftarrow{xy} \quad and \quad \overleftrightarrow{xy} \quad and \quad \overrightarrow{xy}$$
```

- 显示：![\overleftarrow{xy} \quad and \quad \overleftrightarrow{xy} \quad and \quad \overrightarrow{xy}](https://math.jianshu.com/math?formula=%5Coverleftarrow%7Bxy%7D%20%5Cquad%20and%20%5Cquad%20%5Coverleftrightarrow%7Bxy%7D%20%5Cquad%20and%20%5Cquad%20%5Coverrightarrow%7Bxy%7D)

## 8．如何输入积分

使用 `\int_积分下限^积分上限 {被积表达式}` 来输入一个积分。

例子：



```ruby
$$\int_0^1 {x^2} \,{\rm d}x$$
```

显示：![\int_0^1 {x^2} \,{\rm d}x](https://math.jianshu.com/math?formula=%5Cint_0%5E1%20%7Bx%5E2%7D%20%5C%2C%7B%5Crm%20d%7Dx)

本例中 `\,` 和 `{\rm d}` 部分可省略，但建议加入，能使式子更美观。

## 9．如何输入极限运算

使用 `\lim_{变量 \to 表达式} 表达式` 来输入一个极限。如有需求，可以更改 `\to` 符号至任意符号。

例子：



```ruby
$$ \lim_{n \to +\infty} \frac{1}{n(n+1)} \quad and \quad \lim_{x\leftarrow{示例}} \frac{1}{n(n+1)} $$
```

显示：![\lim_{n \to +\infty} \frac{1}{n(n+1)} \quad and \quad \lim_{x\leftarrow{示例}} \frac{1}{n(n+1)}](https://math.jianshu.com/math?formula=%5Clim_%7Bn%20%5Cto%20%2B%5Cinfty%7D%20%5Cfrac%7B1%7D%7Bn(n%2B1)%7D%20%5Cquad%20and%20%5Cquad%20%5Clim_%7Bx%5Cleftarrow%7B%E7%A4%BA%E4%BE%8B%7D%7D%20%5Cfrac%7B1%7D%7Bn(n%2B1)%7D)

## 10．如何输入累加、累乘运算

使用 `\sum_{下标表达式}^{上标表达式} {累加表达式}` 来输入一个累加。
 与之类似，使用 `\prod` `\bigcup` `\bigcap` 来分别输入累乘、并集和交集。
 此类符号在行内显示时上下标表达式将会移至右上角和右下角。

- 例子：



```ruby
$$\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R$$
```

- 显示：![\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R](https://math.jianshu.com/math?formula=%5Csum_%7Bi%3D1%7D%5En%20%5Cfrac%7B1%7D%7Bi%5E2%7D%20%5Cquad%20and%20%5Cquad%20%5Cprod_%7Bi%3D1%7D%5En%20%5Cfrac%7B1%7D%7Bi%5E2%7D%20%5Cquad%20and%20%5Cquad%20%5Cbigcup_%7Bi%3D1%7D%5E%7B2%7D%20R)

## 11．如何输入希腊字母

输入 `\小写希腊字母英文全称` 和 `\首字母大写希腊字母英文全称` 来分别输入小写和大写希腊字母。
 **对于大写希腊字母与现有字母相同的，直接输入大写字母即可。**

|   输入   |                             显示                             |  输入   |                            显示                             |   输入   |                             显示                             |   输入   |                             显示                             |
| :------: | :----------------------------------------------------------: | :-----: | :---------------------------------------------------------: | :------: | :----------------------------------------------------------: | :------: | :----------------------------------------------------------: |
|  \alpha  |  ![\alpha](https://math.jianshu.com/math?formula=%5Calpha)   |    A    |        ![A](https://math.jianshu.com/math?formula=A)        |  \beta   |   ![\beta](https://math.jianshu.com/math?formula=%5Cbeta)    |    B     |        ![B](https://math.jianshu.com/math?formula=B)         |
|  \gamma  |  ![\gamma](https://math.jianshu.com/math?formula=%5Cgamma)   | \Gamma  |  ![\Gamma](https://math.jianshu.com/math?formula=%5CGamma)  |  \delta  |  ![\delta](https://math.jianshu.com/math?formula=%5Cdelta)   |  \Delta  |  ![\Delta](https://math.jianshu.com/math?formula=%5CDelta)   |
| \epsilon | ![\epsilon](https://math.jianshu.com/math?formula=%5Cepsilon) |    E    |        ![E](https://math.jianshu.com/math?formula=E)        |  \zeta   |   ![\zeta](https://math.jianshu.com/math?formula=%5Czeta)    |    Z     |        ![Z](https://math.jianshu.com/math?formula=Z)         |
|   \eta   |    ![\eta](https://math.jianshu.com/math?formula=%5Ceta)     |    H    |        ![H](https://math.jianshu.com/math?formula=H)        |  \theta  |  ![\theta](https://math.jianshu.com/math?formula=%5Ctheta)   |  \Theta  |  ![\Theta](https://math.jianshu.com/math?formula=%5CTheta)   |
|  \iota   |   ![\iota](https://math.jianshu.com/math?formula=%5Ciota)    |    I    |        ![I](https://math.jianshu.com/math?formula=I)        |  \kappa  |  ![\kappa](https://math.jianshu.com/math?formula=%5Ckappa)   |    K     |        ![K](https://math.jianshu.com/math?formula=K)         |
| \lambda  | ![\lambda](https://math.jianshu.com/math?formula=%5Clambda)  | \Lambda | ![\Lambda](https://math.jianshu.com/math?formula=%5CLambda) |   \mu    |     ![\mu](https://math.jianshu.com/math?formula=%5Cmu)      |    M     |        ![M](https://math.jianshu.com/math?formula=M)         |
|   \nu    |     ![\nu](https://math.jianshu.com/math?formula=%5Cnu)      |    N    |        ![N](https://math.jianshu.com/math?formula=N)        |   \xi    |     ![\xi](https://math.jianshu.com/math?formula=%5Cxi)      |   \Xi    |     ![\Xi](https://math.jianshu.com/math?formula=%5CXi)      |
|    o     |        ![o](https://math.jianshu.com/math?formula=o)         |    O    |        ![O](https://math.jianshu.com/math?formula=O)        |   \pi    |     ![\pi](https://math.jianshu.com/math?formula=%5Cpi)      |   \Pi    |     ![\Pi](https://math.jianshu.com/math?formula=%5CPi)      |
|   \rho   |    ![\rho](https://math.jianshu.com/math?formula=%5Crho)     |    P    |        ![P](https://math.jianshu.com/math?formula=P)        |  \sigma  |  ![\sigma](https://math.jianshu.com/math?formula=%5Csigma)   |  \Sigma  |  ![\Sigma](https://math.jianshu.com/math?formula=%5CSigma)   |
|   \tau   |    ![\tau](https://math.jianshu.com/math?formula=%5Ctau)     |    T    |        ![T](https://math.jianshu.com/math?formula=T)        | \upsilon | ![\upsilon](https://math.jianshu.com/math?formula=%5Cupsilon) | \Upsilon | ![\Upsilon](https://math.jianshu.com/math?formula=%5CUpsilon) |
|   \phi   |    ![\phi](https://math.jianshu.com/math?formula=%5Cphi)     |  \Phi   |    ![\Phi](https://math.jianshu.com/math?formula=%5CPhi)    |   \chi   |    ![\chi](https://math.jianshu.com/math?formula=%5Cchi)     |    X     |        ![X](https://math.jianshu.com/math?formula=X)         |
|   \psi   |    ![\psi](https://math.jianshu.com/math?formula=%5Cpsi)     |  \Psi   |    ![\Psi](https://math.jianshu.com/math?formula=%5CPsi)    |  \omega  |  ![\omega](https://math.jianshu.com/math?formula=%5Comega)   |  \Omega  |  ![\Omega](https://math.jianshu.com/math?formula=%5COmega)   |

**部分字母有变量专用形式，以 `\var-` 开头。**

| 小写形式 | 大写形式 |  变量形式   |                             显示                             |
| :------: | :------: | :---------: | :----------------------------------------------------------: |
| \epsilon |    E     | \varepsilon | ![\epsilon \mid E \mid \varepsilon](https://math.jianshu.com/math?formula=%5Cepsilon%20%5Cmid%20E%20%5Cmid%20%5Cvarepsilon) |
|  \theta  |  \Theta  |  \vartheta  | ![\theta \mid \Theta \mid \vartheta](https://math.jianshu.com/math?formula=%5Ctheta%20%5Cmid%20%5CTheta%20%5Cmid%20%5Cvartheta) |
|   \rho   |    P     |   \varrho   | ![\rho \mid P \mid \varrho](https://math.jianshu.com/math?formula=%5Crho%20%5Cmid%20P%20%5Cmid%20%5Cvarrho) |
|  \sigma  |  \Sigma  |  \varsigma  | ![\sigma \mid \Sigma \mid \varsigma](https://math.jianshu.com/math?formula=%5Csigma%20%5Cmid%20%5CSigma%20%5Cmid%20%5Cvarsigma) |
|   \phi   |   \Phi   |   \varphi   | ![\phi \mid \Phi \mid \varphi](https://math.jianshu.com/math?formula=%5Cphi%20%5Cmid%20%5CPhi%20%5Cmid%20%5Cvarphi) |

## 12．如何输入其它特殊字符

> **若需要显示更大或更小的字符，在符号前插入 `\large` 或 `\small` 命令。**

> 若找不到需要的符号，使用 [![\rm{Detexify^2}](https://math.jianshu.com/math?formula=%5Crm%7BDetexify%5E2%7D)](http://detexify.kirelabs.org/classify.html) 来画出想要的符号。

> ![img](https:////upload-images.jianshu.io/upload_images/7600498-9fe3d705d571d408.png?imageMogr2/auto-orient/strip|imageView2/2/w/825/format/webp)
>
> Detexify^2

### (1)．关系运算符

|   输入   |                             显示                             |    输入    |                             显示                             |   输入    |                             显示                             |    输入    |                             显示                             |
| :------: | :----------------------------------------------------------: | :--------: | :----------------------------------------------------------: | :-------: | :----------------------------------------------------------: | :--------: | :----------------------------------------------------------: |
|   \pm    |     ![\pm](https://math.jianshu.com/math?formula=%5Cpm)      |   \times   |  ![\times](https://math.jianshu.com/math?formula=%5Ctimes)   |   \div    |    ![\div](https://math.jianshu.com/math?formula=%5Cdiv)     |    \mid    |    ![\mid](https://math.jianshu.com/math?formula=%5Cmid)     |
|  \nmid   |   ![\nmid](https://math.jianshu.com/math?formula=%5Cnmid)    |   \cdot    |   ![\cdot](https://math.jianshu.com/math?formula=%5Ccdot)    |   \circ   |   ![\circ](https://math.jianshu.com/math?formula=%5Ccirc)    |    \ast    |    ![\ast](https://math.jianshu.com/math?formula=%5Cast)     |
| \bigodot | ![\bigodot](https://math.jianshu.com/math?formula=%5Cbigodot) | \bigotimes | ![\bigotimes](https://math.jianshu.com/math?formula=%5Cbigotimes) | \bigoplus | ![\bigoplus](https://math.jianshu.com/math?formula=%5Cbigoplus) |    \leq    |    ![\leq](https://math.jianshu.com/math?formula=%5Cleq)     |
|   \geq   |    ![\geq](https://math.jianshu.com/math?formula=%5Cgeq)     |    \neq    |    ![\neq](https://math.jianshu.com/math?formula=%5Cneq)     |  \approx  | ![\approx](https://math.jianshu.com/math?formula=%5Capprox)  |   \equiv   |  ![\equiv](https://math.jianshu.com/math?formula=%5Cequiv)   |
|   \sum   |    ![\sum](https://math.jianshu.com/math?formula=%5Csum)     |   \prod    |   ![\prod](https://math.jianshu.com/math?formula=%5Cprod)    |  \coprod  | ![\coprod](https://math.jianshu.com/math?formula=%5Ccoprod)  | \backslash | ![\backslash](https://math.jianshu.com/math?formula=%5Cbackslash) |

### (2)．集合运算符

|   输入    |                             显示                             |   输入    |                             显示                             |   输入    |                             显示                             |
| :-------: | :----------------------------------------------------------: | :-------: | :----------------------------------------------------------: | :-------: | :----------------------------------------------------------: |
| \emptyset | ![\emptyset](https://math.jianshu.com/math?formula=%5Cemptyset) |    \in    |     ![\in](https://math.jianshu.com/math?formula=%5Cin)      |  \notin   |  ![\notin](https://math.jianshu.com/math?formula=%5Cnotin)   |
|  \subset  | ![\subset](https://math.jianshu.com/math?formula=%5Csubset)  |  \supset  | ![\supset](https://math.jianshu.com/math?formula=%5Csupset)  | \subseteq | ![\subseteq](https://math.jianshu.com/math?formula=%5Csubseteq) |
| \supseteq | ![\supseteq](https://math.jianshu.com/math?formula=%5Csupseteq) |  \bigcap  | ![\bigcap](https://math.jianshu.com/math?formula=%5Cbigcap)  |  \bigcup  | ![\bigcup](https://math.jianshu.com/math?formula=%5Cbigcup)  |
|  \bigvee  | ![\bigvee](https://math.jianshu.com/math?formula=%5Cbigvee)  | \bigwedge | ![\bigwedge](https://math.jianshu.com/math?formula=%5Cbigwedge) | \biguplus | ![\biguplus](https://math.jianshu.com/math?formula=%5Cbiguplus) |

### (3)．对数运算符

| 输入 |                         显示                          | 输入 |                        显示                         | 输入 |                        显示                         |
| :--: | :---------------------------------------------------: | :--: | :-------------------------------------------------: | :--: | :-------------------------------------------------: |
| \log | ![\log](https://math.jianshu.com/math?formula=%5Clog) | \lg  | ![\lg](https://math.jianshu.com/math?formula=%5Clg) | \ln  | ![\ln](https://math.jianshu.com/math?formula=%5Cln) |

### (4)．三角运算符

|   输入   |                             显示                             | 输入 |                         显示                          |   输入   |                             显示                             |
| :------: | :----------------------------------------------------------: | :--: | :---------------------------------------------------: | :------: | :----------------------------------------------------------: |
| 30^\circ | ![30^\circ](https://math.jianshu.com/math?formula=30%5E%5Ccirc) | \bot | ![\bot](https://math.jianshu.com/math?formula=%5Cbot) | \angle A | ![\angle A](https://math.jianshu.com/math?formula=%5Cangle%20A) |
|   \sin   |    ![\sin](https://math.jianshu.com/math?formula=%5Csin)     | \cos | ![\cos](https://math.jianshu.com/math?formula=%5Ccos) |   \tan   |    ![\tan](https://math.jianshu.com/math?formula=%5Ctan)     |
|   \csc   |    ![\csc](https://math.jianshu.com/math?formula=%5Ccsc)     | \sec | ![\sec](https://math.jianshu.com/math?formula=%5Csec) |   \cot   |    ![\cot](https://math.jianshu.com/math?formula=%5Ccot)     |

### (5)．微积分运算符

|  输入   |                            显示                             |  输入  |                           显示                            |  输入  |                           显示                            |
| :-----: | :---------------------------------------------------------: | :----: | :-------------------------------------------------------: | :----: | :-------------------------------------------------------: |
|  \int   |    ![\int](https://math.jianshu.com/math?formula=%5Cint)    | \iint  |  ![\iint](https://math.jianshu.com/math?formula=%5Ciint)  | \iiint | ![\iiint](https://math.jianshu.com/math?formula=%5Ciiint) |
| \iiiint | ![\iiiint](https://math.jianshu.com/math?formula=%5Ciiiint) | \oint  |  ![\oint](https://math.jianshu.com/math?formula=%5Coint)  | \prime | ![\prime](https://math.jianshu.com/math?formula=%5Cprime) |
|  \lim   |    ![\lim](https://math.jianshu.com/math?formula=%5Clim)    | \infty | ![\infty](https://math.jianshu.com/math?formula=%5Cinfty) | \nabla | ![\nabla](https://math.jianshu.com/math?formula=%5Cnabla) |

### (6)．逻辑运算符

|   输入   |                             显示                             |    输入    |                             显示                             |    输入     |                             显示                             |
| :------: | :----------------------------------------------------------: | :--------: | :----------------------------------------------------------: | :---------: | :----------------------------------------------------------: |
| \because | ![\because](https://math.jianshu.com/math?formula=%5Cbecause) | \therefore | ![\therefore](https://math.jianshu.com/math?formula=%5Ctherefore) |    \sim     |    ![\sim](https://math.jianshu.com/math?formula=%5Csim)     |
| \forall  | ![\forall](https://math.jianshu.com/math?formula=%5Cforall)  |  \exists   | ![\exists](https://math.jianshu.com/math?formula=%5Cexists)  | \not\subset | ![\not\subset](https://math.jianshu.com/math?formula=%5Cnot%5Csubset) |
|  \not<   |  ![\not<](https://math.jianshu.com/math?formula=%5Cnot%3C)   |   \not>    |  ![\not>](https://math.jianshu.com/math?formula=%5Cnot%3E)   |    \not=    |  ![\not=](https://math.jianshu.com/math?formula=%5Cnot%3D)   |

### (7)．戴帽符号

|    输入    |                             显示                             |      输入       |                             显示                             |
| :--------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: |
|  \hat{xy}  | ![\hat{xy}](https://math.jianshu.com/math?formula=%5Chat%7Bxy%7D) |  \widehat{xyz}  | ![\widehat{xyz}](https://math.jianshu.com/math?formula=%5Cwidehat%7Bxyz%7D) |
| \tilde{xy} | ![\tilde{xy}](https://math.jianshu.com/math?formula=%5Ctilde%7Bxy%7D) | \widetilde{xyz} | ![\widetilde{xyz}](https://math.jianshu.com/math?formula=%5Cwidetilde%7Bxyz%7D) |
| \check{x}  | ![\check{x}](https://math.jianshu.com/math?formula=%5Ccheck%7Bx%7D) |    \breve{y}    | ![\breve{y}](https://math.jianshu.com/math?formula=%5Cbreve%7By%7D) |
| \grave{x}  | ![\grave{x}](https://math.jianshu.com/math?formula=%5Cgrave%7Bx%7D) |    \acute{y}    | ![\acute{y}](https://math.jianshu.com/math?formula=%5Cacute%7By%7D) |

### (8)．连线符号

|                      输入                      |                             显示                             |
| :--------------------------------------------: | :----------------------------------------------------------: |
|                 \fbox{a+b+c+d}                 | ![\fbox{a+b+c+d}](https://math.jianshu.com/math?formula=%5Cfbox%7Ba%2Bb%2Bc%2Bd%7D) |
|            \overleftarrow{a+b+c+d}             | ![\overleftarrow{a+b+c+d}](https://math.jianshu.com/math?formula=%5Coverleftarrow%7Ba%2Bb%2Bc%2Bd%7D) |
|            \overrightarrow{a+b+c+d}            | ![\overrightarrow{a+b+c+d}](https://math.jianshu.com/math?formula=%5Coverrightarrow%7Ba%2Bb%2Bc%2Bd%7D) |
|          \overleftrightarrow{a+b+c+d}          | ![\overleftrightarrow{a+b+c+d}](https://math.jianshu.com/math?formula=%5Coverleftrightarrow%7Ba%2Bb%2Bc%2Bd%7D) |
|            \underleftarrow{a+b+c+d}            | ![\underleftarrow{a+b+c+d}](https://math.jianshu.com/math?formula=%5Cunderleftarrow%7Ba%2Bb%2Bc%2Bd%7D) |
|           \underrightarrow{a+b+c+d}            | ![\underrightarrow{a+b+c+d}](https://math.jianshu.com/math?formula=%5Cunderrightarrow%7Ba%2Bb%2Bc%2Bd%7D) |
|         \underleftrightarrow{a+b+c+d}          | ![\underleftrightarrow{a+b+c+d}](https://math.jianshu.com/math?formula=%5Cunderleftrightarrow%7Ba%2Bb%2Bc%2Bd%7D) |
|               \overline{a+b+c+d}               | ![\overline{a+b+c+d}](https://math.jianshu.com/math?formula=%5Coverline%7Ba%2Bb%2Bc%2Bd%7D) |
|              \underline{a+b+c+d}               | ![\underline{a+b+c+d}](https://math.jianshu.com/math?formula=%5Cunderline%7Ba%2Bb%2Bc%2Bd%7D) |
|          \overbrace{a+b+c+d}^{Sample}          | ![\overbrace{a+b+c+d}^{Sample}](https://math.jianshu.com/math?formula=%5Coverbrace%7Ba%2Bb%2Bc%2Bd%7D%5E%7BSample%7D) |
|         \underbrace{a+b+c+d}_{Sample}          | ![\underbrace{a+b+c+d}_{Sample}](https://math.jianshu.com/math?formula=%5Cunderbrace%7Ba%2Bb%2Bc%2Bd%7D_%7BSample%7D) |
|  \overbrace{a+\underbrace{b+c}_{1.0}+d}^{2.0}  | ![\overbrace{a+\underbrace{b+c}_{1.0}+d}^{2.0}](https://math.jianshu.com/math?formula=%5Coverbrace%7Ba%2B%5Cunderbrace%7Bb%2Bc%7D_%7B1.0%7D%2Bd%7D%5E%7B2.0%7D) |
| \underbrace{a\cdot a\cdots a}_{b\text{ times}} | ![\underbrace{a\cdot a\cdots a}_{b\text{ times}}](https://math.jianshu.com/math?formula=%5Cunderbrace%7Ba%5Ccdot%20a%5Ccdots%20a%7D_%7Bb%5Ctext%7B%20times%7D%7D) |

### (9)．箭头符号

- 推荐使用符号：

|   输入   |                             显示                             |  输入   |                            显示                             |    输入    |                             显示                             |
| :------: | :----------------------------------------------------------: | :-----: | :---------------------------------------------------------: | :--------: | :----------------------------------------------------------: |
|   \to    |     ![\to](https://math.jianshu.com/math?formula=%5Cto)      | \mapsto | ![\mapsto](https://math.jianshu.com/math?formula=%5Cmapsto) |            |                                                              |
| \implies | ![\implies](https://math.jianshu.com/math?formula=%5Cimplies) |  \iff   |    ![\iff](https://math.jianshu.com/math?formula=%5Ciff)    | \impliedby | ![\impliedby](https://math.jianshu.com/math?formula=%5Cimpliedby) |

- 其它可用符号：

|        输入         |                             显示                             |        输入         |                             显示                             |
| :-----------------: | :----------------------------------------------------------: | :-----------------: | :----------------------------------------------------------: |
|      \uparrow       | ![\uparrow](https://math.jianshu.com/math?formula=%5Cuparrow) |      \Uparrow       | ![\Uparrow](https://math.jianshu.com/math?formula=%5CUparrow) |
|     \downarrow      | ![\downarrow](https://math.jianshu.com/math?formula=%5Cdownarrow) |     \Downarrow      | ![\Downarrow](https://math.jianshu.com/math?formula=%5CDownarrow) |
|     \leftarrow      | ![\leftarrow](https://math.jianshu.com/math?formula=%5Cleftarrow) |     \Leftarrow      | ![\Leftarrow](https://math.jianshu.com/math?formula=%5CLeftarrow) |
|     \rightarrow     | ![\rightarrow](https://math.jianshu.com/math?formula=%5Crightarrow) |     \Rightarrow     | ![\Rightarrow](https://math.jianshu.com/math?formula=%5CRightarrow) |
|   \leftrightarrow   | ![\leftrightarrow](https://math.jianshu.com/math?formula=%5Cleftrightarrow) |   \Leftrightarrow   | ![\Leftrightarrow](https://math.jianshu.com/math?formula=%5CLeftrightarrow) |
|   \longleftarrow    | ![\longleftarrow](https://math.jianshu.com/math?formula=%5Clongleftarrow) |   \Longleftarrow    | ![\Longleftarrow](https://math.jianshu.com/math?formula=%5CLongleftarrow) |
|   \longrightarrow   | ![\longrightarrow](https://math.jianshu.com/math?formula=%5Clongrightarrow) |   \Longrightarrow   | ![\Longrightarrow](https://math.jianshu.com/math?formula=%5CLongrightarrow) |
| \longleftrightarrow | ![\longleftrightarrow](https://math.jianshu.com/math?formula=%5Clongleftrightarrow) | \Longleftrightarrow | ![\Longleftrightarrow](https://math.jianshu.com/math?formula=%5CLongleftrightarrow) |

## 13．如何进行字体转换

若要对公式的某一部分字符进行字体转换，可以用 `{\字体 {需转换的部分字符}}` 命令，其中 `\字体` 部分可以参照下表选择合适的字体。一般情况下，公式默认为意大利体 ![italic](https://math.jianshu.com/math?formula=italic) 。

示例中 **全部大写** 的字体仅大写可用。

| 输入  |    说明    |                             显示                             | 输入 |   说明   |                             显示                             |
| :---: | :--------: | :----------------------------------------------------------: | :--: | :------: | :----------------------------------------------------------: |
|  \rm  |   罗马体   | ![\rm{Sample}](https://math.jianshu.com/math?formula=%5Crm%7BSample%7D) | \cal |   花体   | ![\cal{SAMPLE}](https://math.jianshu.com/math?formula=%5Ccal%7BSAMPLE%7D) |
|  \it  |  意大利体  | ![\it{Sample}](https://math.jianshu.com/math?formula=%5Cit%7BSample%7D) | \Bbb | 黑板粗体 | ![\Bbb{SAMPLE}](https://math.jianshu.com/math?formula=%5CBbb%7BSAMPLE%7D) |
|  \bf  |    粗体    | ![\bf{Sample}](https://math.jianshu.com/math?formula=%5Cbf%7BSample%7D) | \mit | 数学斜体 | ![\mit{SAMPLE}](https://math.jianshu.com/math?formula=%5Cmit%7BSAMPLE%7D) |
|  \sf  |   等线体   | ![\sf{Sample}](https://math.jianshu.com/math?formula=%5Csf%7BSample%7D) | \scr |  手写体  | ![\scr{SAMPLE}](https://math.jianshu.com/math?formula=%5Cscr%7BSAMPLE%7D) |
|  \tt  |  打字机体  | ![\tt{Sample}](https://math.jianshu.com/math?formula=%5Ctt%7BSample%7D) |      |          |                                                              |
| \frak | 旧德式字体 | ![\frak{Sample}](https://math.jianshu.com/math?formula=%5Cfrak%7BSample%7D) |      |          |                                                              |

转换字体十分常用，例如在积分中：

- 例子：



```cpp
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
\int_0^1 x^2 dx & \int_0^1 x^2 \,{\rm d}x
\end{array}
```

- 显示：

![\begin{array}{cc} \mathrm{Bad} & \mathrm{Better} \\ \hline \\ \int_0^1 x^2 dx & \int_0^1 x^2 \,{\rm d}x \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7Bcc%7D%20%5Cmathrm%7BBad%7D%20%26%20%5Cmathrm%7BBetter%7D%20%5C%5C%20%5Chline%20%5C%5C%20%5Cint_0%5E1%20x%5E2%20dx%20%26%20%5Cint_0%5E1%20x%5E2%20%5C%2C%7B%5Crm%20d%7Dx%20%5Cend%7Barray%7D)

注意比较两个式子间 ![dx](https://math.jianshu.com/math?formula=dx) 与 ![{\rm d} x](https://math.jianshu.com/math?formula=%7B%5Crm%20d%7D%20x) 的不同。
 使用 `\operatorname` 命令也可以达到相同的效果，详见 [定义新的符号 \operatorname](#1定义新的符号-operatorname) 。

## 14．大括号和行标的使用

使用 `\left` 和 `\right` 来创建自动匹配高度的 (圆括号)，[方括号] 和 {花括号} 。
 在每个公式末尾前使用 `\tag{行标}` 来实现行标。

- 例子：



```swift
$$
f\left(
   \left[ 
     \frac{
       1+\left\{x,y\right\}
     }{
       \left(
          \frac{x}{y}+\frac{y}{x}
       \right)
       \left(u+1\right)
     }+a
   \right]^{3/2}
\right)
\tag{行标}
$$
```

- 显示：
   ![f\left( \left[ \frac{ 1+\left\{x,y\right\} }{ \left( \frac{x}{y}+\frac{y}{x} \right) \left(u+1\right) }+a \right]^{3/2} \right) \tag{行标}](https://math.jianshu.com/math?formula=f%5Cleft(%20%5Cleft%5B%20%5Cfrac%7B%201%2B%5Cleft%5C%7Bx%2Cy%5Cright%5C%7D%20%7D%7B%20%5Cleft(%20%5Cfrac%7Bx%7D%7By%7D%2B%5Cfrac%7By%7D%7Bx%7D%20%5Cright)%20%5Cleft(u%2B1%5Cright)%20%7D%2Ba%20%5Cright%5D%5E%7B3%2F2%7D%20%5Cright)%20%5Ctag%7B%E8%A1%8C%E6%A0%87%7D)

如果你需要在不同的行显示对应括号，可以在每一行对应处使用 `\left.` 或 `\right.` 来放一个"影子"括号：

- 例子：



```ruby
$$
\begin{aligned}
a=&\left(1+2+3+  \cdots \right. \\
& \cdots+ \left. \infty-2+\infty-1+\infty\right)
\end{aligned}
$$
```

- 显示：

![\begin{aligned} a=&\left(1+2+3+ \cdots \right. \\ & \cdots+ \left. \infty-2+\infty-1+\infty\right) \end{aligned}](https://math.jianshu.com/math?formula=%5Cbegin%7Baligned%7D%20a%3D%26%5Cleft(1%2B2%2B3%2B%20%5Ccdots%20%5Cright.%20%5C%5C%20%26%20%5Ccdots%2B%20%5Cleft.%20%5Cinfty-2%2B%5Cinfty-1%2B%5Cinfty%5Cright)%20%5Cend%7Baligned%7D)

如果你需要将行内显示的分隔符也变大，可以使用 `\middle` 命令：

- 例子：



```ruby
$$
\left\langle  
  q
\middle\|
  \frac{\frac{x}{y}}{\frac{u}{v}}
\middle| 
   p 
\right\rangle
$$
```

- 显示：
   ![\left\langle q \middle\| \frac{\frac{x}{y}}{\frac{u}{v}} \middle| p \right\rangle](https://math.jianshu.com/math?formula=%5Cleft%5Clangle%20q%20%5Cmiddle%5C%7C%20%5Cfrac%7B%5Cfrac%7Bx%7D%7By%7D%7D%7B%5Cfrac%7Bu%7D%7Bv%7D%7D%20%5Cmiddle%7C%20p%20%5Cright%5Crangle)

## 15．其它命令

### (1)．定义新的符号 \operatorname

查询 [关于此命令的定义](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference/15077#15077) 和 [关于此命令的讨论](http://meta.math.stackexchange.com/search?q=operatorname) 来进一步了解此命令。

- 例子：



```ruby
$$ \operatorname{Symbol} A $$
```

- 显示： ![\operatorname{Symbol} A](https://math.jianshu.com/math?formula=%5Coperatorname%7BSymbol%7D%20A)

### (2)．添加注释文字 \text

在 `\text {文字}` 中仍可以使用 `$公式$` 插入其它公式。

- 例子：



```ruby
$$ f(n)= \begin{cases} n/2, & \text {if $n$ is even} \\ 3n+1, & \text{if $n$ is odd} \end{cases} $$
```

- 显示：
   ![f(n)= \begin{cases} n/2, & \text {if $n$ is even} \\ 3n+1, & \text{if $n$ is odd} \end{cases}](https://math.jianshu.com/math?formula=f(n)%3D%20%5Cbegin%7Bcases%7D%20n%2F2%2C%20%26%20%5Ctext%20%7Bif%20%24n%24%20is%20even%7D%20%5C%5C%203n%2B1%2C%20%26%20%5Ctext%7Bif%20%24n%24%20is%20odd%7D%20%5Cend%7Bcases%7D)

### (3)．在字符间加入空格

有四种宽度的空格可以使用： `\,`、`\;`、`\quad` 和 `\qquad` 。

- 例子：



```ruby
$$ a \, b \mid a \; b \mid a \quad b \mid a \qquad b $$
```

- 显示：![a \, b \mid a \; b \mid a \quad b \mid a \qquad b](https://math.jianshu.com/math?formula=a%20%5C%2C%20b%20%5Cmid%20a%20%5C%3B%20b%20%5Cmid%20a%20%5Cquad%20b%20%5Cmid%20a%20%5Cqquad%20b)

当然，使用 `\text {n个空格}` 也可以达到同样效果。

### (4)．更改文字颜色

使用 `\color{颜色}{文字}` 来更改特定的文字颜色。
 更改文字颜色 **需要浏览器支持** ，如果浏览器不知道你所需的颜色，那么文字将被渲染为黑色。

对于较旧的浏览器（HTML4与CSS2），以下颜色是被支持的：

|  输入  |                             显示                             |  输入   |                             显示                             |
| :----: | :----------------------------------------------------------: | :-----: | :----------------------------------------------------------: |
| black  | ![\color{black}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bblack%7D%7Btext%7D) |  grey   | ![\color{grey}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bgrey%7D%7Btext%7D) |
| silver | ![\color{silver}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bsilver%7D%7Btext%7D) |  white  | ![\color{white}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bwhite%7D%7Btext%7D) |
| maroon | ![\color{maroon}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bmaroon%7D%7Btext%7D) |   red   | ![\color{red}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bred%7D%7Btext%7D) |
| yellow | ![\color{yellow}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Byellow%7D%7Btext%7D) |  lime   | ![\color{lime}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Blime%7D%7Btext%7D) |
| olive  | ![\color{olive}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bolive%7D%7Btext%7D) |  green  | ![\color{green}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bgreen%7D%7Btext%7D) |
|  teal  | ![\color{teal}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bteal%7D%7Btext%7D) |  auqa   | ![\color{auqa}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bauqa%7D%7Btext%7D) |
|  blue  | ![\color{blue}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bblue%7D%7Btext%7D) |  navy   | ![\color{navy}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bnavy%7D%7Btext%7D) |
| purple | ![\color{purple}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bpurple%7D%7Btext%7D) | fuchsia | ![\color{fuchsia}{text}](https://math.jianshu.com/math?formula=%5Ccolor%7Bfuchsia%7D%7Btext%7D) |

对于较新的浏览器（HTML5与CSS3），额外的124种颜色将被支持：

输入 `\color {#rgb} {text}` 来自定义更多的颜色，其中 `#rgb` 的 `r` `g` `b` 可输入 `0-9` 和 `a-f` 来表示红色、绿色和蓝色的纯度（饱和度）。

- 例子：



```ruby
\begin{array}{|rrrrrrrr|}\hline
\verb+#000+ & \color{#000}{text} & & &
\verb+#00F+ & \color{#00F}{text} & & \\
& & \verb+#0F0+ & \color{#0F0}{text} &
& & \verb+#0FF+ & \color{#0FF}{text}\\
\verb+#F00+ & \color{#F00}{text} & & &
\verb+#F0F+ & \color{#F0F}{text} & & \\
& & \verb+#FF0+ & \color{#FF0}{text} &
& & \verb+#FFF+ & \color{#FFF}{text}\\
\hline
\end{array}
```

- 显示：
   ![\begin{array}{|rrrrrrrr|}\hline \verb+#000+ & \color{#000}{text} & & & \verb+#00F+ & \color{#00F}{text} & & \\ & & \verb+#0F0+ & \color{#0F0}{text} & & & \verb+#0FF+ & \color{#0FF}{text}\\ \verb+#F00+ & \color{#F00}{text} & & & \verb+#F0F+ & \color{#F0F}{text} & & \\ & & \verb+#FF0+ & \color{#FF0}{text} & & & \verb+#FFF+ & \color{#FFF}{text}\\ \hline \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7B%7Crrrrrrrr%7C%7D%5Chline%20%5Cverb%2B%23000%2B%20%26%20%5Ccolor%7B%23000%7D%7Btext%7D%20%26%20%26%20%26%20%5Cverb%2B%2300F%2B%20%26%20%5Ccolor%7B%2300F%7D%7Btext%7D%20%26%20%26%20%5C%5C%20%26%20%26%20%5Cverb%2B%230F0%2B%20%26%20%5Ccolor%7B%230F0%7D%7Btext%7D%20%26%20%26%20%26%20%5Cverb%2B%230FF%2B%20%26%20%5Ccolor%7B%230FF%7D%7Btext%7D%5C%5C%20%5Cverb%2B%23F00%2B%20%26%20%5Ccolor%7B%23F00%7D%7Btext%7D%20%26%20%26%20%26%20%5Cverb%2B%23F0F%2B%20%26%20%5Ccolor%7B%23F0F%7D%7Btext%7D%20%26%20%26%20%5C%5C%20%26%20%26%20%5Cverb%2B%23FF0%2B%20%26%20%5Ccolor%7B%23FF0%7D%7Btext%7D%20%26%20%26%20%26%20%5Cverb%2B%23FFF%2B%20%26%20%5Ccolor%7B%23FFF%7D%7Btext%7D%5C%5C%20%5Chline%20%5Cend%7Barray%7D)
- 例子：



```ruby
\begin{array}{|rrrrrrrr|}
\hline
\verb+#000+ & \color{#000}{text} & \verb+#005+ & \color{#005}{text} & \verb+#00A+ & \color{#00A}{text} & \verb+#00F+ & \color{#00F}{text}  \\
\verb+#500+ & \color{#500}{text} & \verb+#505+ & \color{#505}{text} & \verb+#50A+ & \color{#50A}{text} & \verb+#50F+ & \color{#50F}{text}  \\
\verb+#A00+ & \color{#A00}{text} & \verb+#A05+ & \color{#A05}{text} & \verb+#A0A+ & \color{#A0A}{text} & \verb+#A0F+ & \color{#A0F}{text}  \\
\verb+#F00+ & \color{#F00}{text} & \verb+#F05+ & \color{#F05}{text} & \verb+#F0A+ & \color{#F0A}{text} & \verb+#F0F+ & \color{#F0F}{text}  \\
\hline
\verb+#080+ & \color{#080}{text} & \verb+#085+ & \color{#085}{text} & \verb+#08A+ & \color{#08A}{text} & \verb+#08F+ & \color{#08F}{text}  \\
\verb+#580+ & \color{#580}{text} & \verb+#585+ & \color{#585}{text} & \verb+#58A+ & \color{#58A}{text} & \verb+#58F+ & \color{#58F}{text}  \\
\verb+#A80+ & \color{#A80}{text} & \verb+#A85+ & \color{#A85}{text} & \verb+#A8A+ & \color{#A8A}{text} & \verb+#A8F+ & \color{#A8F}{text}  \\
\verb+#F80+ & \color{#F80}{text} & \verb+#F85+ & \color{#F85}{text} & \verb+#F8A+ & \color{#F8A}{text} & \verb+#F8F+ & \color{#F8F}{text}  \\
\hline
\verb+#0F0+ & \color{#0F0}{text} & \verb+#0F5+ & \color{#0F5}{text} & \verb+#0FA+ & \color{#0FA}{text} & \verb+#0FF+ & \color{#0FF}{text}  \\
\verb+#5F0+ & \color{#5F0}{text} & \verb+#5F5+ & \color{#5F5}{text} & \verb+#5FA+ & \color{#5FA}{text} & \verb+#5FF+ & \color{#5FF}{text}  \\
\verb+#AF0+ & \color{#AF0}{text} & \verb+#AF5+ & \color{#AF5}{text} & \verb+#AFA+ & \color{#AFA}{text} & \verb+#AFF+ & \color{#AFF}{text}  \\
\verb+#FF0+ & \color{#FF0}{text} & \verb+#FF5+ & \color{#FF5}{text} & \verb+#FFA+ & \color{#FFA}{text} & \verb+#FFF+ & \color{#FFF}{text}  \\
\hline
\end{array}
```

- 显示：

![\begin{array}{|rrrrrrrr|} \hline \verb+#000+ & \color{#000}{text} & \verb+#005+ & \color{#005}{text} & \verb+#00A+ & \color{#00A}{text} & \verb+#00F+ & \color{#00F}{text} \\ \verb+#500+ & \color{#500}{text} & \verb+#505+ & \color{#505}{text} & \verb+#50A+ & \color{#50A}{text} & \verb+#50F+ & \color{#50F}{text} \\ \verb+#A00+ & \color{#A00}{text} & \verb+#A05+ & \color{#A05}{text} & \verb+#A0A+ & \color{#A0A}{text} & \verb+#A0F+ & \color{#A0F}{text} \\ \verb+#F00+ & \color{#F00}{text} & \verb+#F05+ & \color{#F05}{text} & \verb+#F0A+ & \color{#F0A}{text} & \verb+#F0F+ & \color{#F0F}{text} \\ \hline \verb+#080+ & \color{#080}{text} & \verb+#085+ & \color{#085}{text} & \verb+#08A+ & \color{#08A}{text} & \verb+#08F+ & \color{#08F}{text} \\ \verb+#580+ & \color{#580}{text} & \verb+#585+ & \color{#585}{text} & \verb+#58A+ & \color{#58A}{text} & \verb+#58F+ & \color{#58F}{text} \\ \verb+#A80+ & \color{#A80}{text} & \verb+#A85+ & \color{#A85}{text} & \verb+#A8A+ & \color{#A8A}{text} & \verb+#A8F+ & \color{#A8F}{text} \\ \verb+#F80+ & \color{#F80}{text} & \verb+#F85+ & \color{#F85}{text} & \verb+#F8A+ & \color{#F8A}{text} & \verb+#F8F+ & \color{#F8F}{text} \\ \hline \verb+#0F0+ & \color{#0F0}{text} & \verb+#0F5+ & \color{#0F5}{text} & \verb+#0FA+ & \color{#0FA}{text} & \verb+#0FF+ & \color{#0FF}{text} \\ \verb+#5F0+ & \color{#5F0}{text} & \verb+#5F5+ & \color{#5F5}{text} & \verb+#5FA+ & \color{#5FA}{text} & \verb+#5FF+ & \color{#5FF}{text} \\ \verb+#AF0+ & \color{#AF0}{text} & \verb+#AF5+ & \color{#AF5}{text} & \verb+#AFA+ & \color{#AFA}{text} & \verb+#AFF+ & \color{#AFF}{text} \\ \verb+#FF0+ & \color{#FF0}{text} & \verb+#FF5+ & \color{#FF5}{text} & \verb+#FFA+ & \color{#FFA}{text} & \verb+#FFF+ & \color{#FFF}{text} \\ \hline \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7B%7Crrrrrrrr%7C%7D%20%5Chline%20%5Cverb%2B%23000%2B%20%26%20%5Ccolor%7B%23000%7D%7Btext%7D%20%26%20%5Cverb%2B%23005%2B%20%26%20%5Ccolor%7B%23005%7D%7Btext%7D%20%26%20%5Cverb%2B%2300A%2B%20%26%20%5Ccolor%7B%2300A%7D%7Btext%7D%20%26%20%5Cverb%2B%2300F%2B%20%26%20%5Ccolor%7B%2300F%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23500%2B%20%26%20%5Ccolor%7B%23500%7D%7Btext%7D%20%26%20%5Cverb%2B%23505%2B%20%26%20%5Ccolor%7B%23505%7D%7Btext%7D%20%26%20%5Cverb%2B%2350A%2B%20%26%20%5Ccolor%7B%2350A%7D%7Btext%7D%20%26%20%5Cverb%2B%2350F%2B%20%26%20%5Ccolor%7B%2350F%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23A00%2B%20%26%20%5Ccolor%7B%23A00%7D%7Btext%7D%20%26%20%5Cverb%2B%23A05%2B%20%26%20%5Ccolor%7B%23A05%7D%7Btext%7D%20%26%20%5Cverb%2B%23A0A%2B%20%26%20%5Ccolor%7B%23A0A%7D%7Btext%7D%20%26%20%5Cverb%2B%23A0F%2B%20%26%20%5Ccolor%7B%23A0F%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23F00%2B%20%26%20%5Ccolor%7B%23F00%7D%7Btext%7D%20%26%20%5Cverb%2B%23F05%2B%20%26%20%5Ccolor%7B%23F05%7D%7Btext%7D%20%26%20%5Cverb%2B%23F0A%2B%20%26%20%5Ccolor%7B%23F0A%7D%7Btext%7D%20%26%20%5Cverb%2B%23F0F%2B%20%26%20%5Ccolor%7B%23F0F%7D%7Btext%7D%20%5C%5C%20%5Chline%20%5Cverb%2B%23080%2B%20%26%20%5Ccolor%7B%23080%7D%7Btext%7D%20%26%20%5Cverb%2B%23085%2B%20%26%20%5Ccolor%7B%23085%7D%7Btext%7D%20%26%20%5Cverb%2B%2308A%2B%20%26%20%5Ccolor%7B%2308A%7D%7Btext%7D%20%26%20%5Cverb%2B%2308F%2B%20%26%20%5Ccolor%7B%2308F%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23580%2B%20%26%20%5Ccolor%7B%23580%7D%7Btext%7D%20%26%20%5Cverb%2B%23585%2B%20%26%20%5Ccolor%7B%23585%7D%7Btext%7D%20%26%20%5Cverb%2B%2358A%2B%20%26%20%5Ccolor%7B%2358A%7D%7Btext%7D%20%26%20%5Cverb%2B%2358F%2B%20%26%20%5Ccolor%7B%2358F%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23A80%2B%20%26%20%5Ccolor%7B%23A80%7D%7Btext%7D%20%26%20%5Cverb%2B%23A85%2B%20%26%20%5Ccolor%7B%23A85%7D%7Btext%7D%20%26%20%5Cverb%2B%23A8A%2B%20%26%20%5Ccolor%7B%23A8A%7D%7Btext%7D%20%26%20%5Cverb%2B%23A8F%2B%20%26%20%5Ccolor%7B%23A8F%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23F80%2B%20%26%20%5Ccolor%7B%23F80%7D%7Btext%7D%20%26%20%5Cverb%2B%23F85%2B%20%26%20%5Ccolor%7B%23F85%7D%7Btext%7D%20%26%20%5Cverb%2B%23F8A%2B%20%26%20%5Ccolor%7B%23F8A%7D%7Btext%7D%20%26%20%5Cverb%2B%23F8F%2B%20%26%20%5Ccolor%7B%23F8F%7D%7Btext%7D%20%5C%5C%20%5Chline%20%5Cverb%2B%230F0%2B%20%26%20%5Ccolor%7B%230F0%7D%7Btext%7D%20%26%20%5Cverb%2B%230F5%2B%20%26%20%5Ccolor%7B%230F5%7D%7Btext%7D%20%26%20%5Cverb%2B%230FA%2B%20%26%20%5Ccolor%7B%230FA%7D%7Btext%7D%20%26%20%5Cverb%2B%230FF%2B%20%26%20%5Ccolor%7B%230FF%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%235F0%2B%20%26%20%5Ccolor%7B%235F0%7D%7Btext%7D%20%26%20%5Cverb%2B%235F5%2B%20%26%20%5Ccolor%7B%235F5%7D%7Btext%7D%20%26%20%5Cverb%2B%235FA%2B%20%26%20%5Ccolor%7B%235FA%7D%7Btext%7D%20%26%20%5Cverb%2B%235FF%2B%20%26%20%5Ccolor%7B%235FF%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23AF0%2B%20%26%20%5Ccolor%7B%23AF0%7D%7Btext%7D%20%26%20%5Cverb%2B%23AF5%2B%20%26%20%5Ccolor%7B%23AF5%7D%7Btext%7D%20%26%20%5Cverb%2B%23AFA%2B%20%26%20%5Ccolor%7B%23AFA%7D%7Btext%7D%20%26%20%5Cverb%2B%23AFF%2B%20%26%20%5Ccolor%7B%23AFF%7D%7Btext%7D%20%5C%5C%20%5Cverb%2B%23FF0%2B%20%26%20%5Ccolor%7B%23FF0%7D%7Btext%7D%20%26%20%5Cverb%2B%23FF5%2B%20%26%20%5Ccolor%7B%23FF5%7D%7Btext%7D%20%26%20%5Cverb%2B%23FFA%2B%20%26%20%5Ccolor%7B%23FFA%7D%7Btext%7D%20%26%20%5Cverb%2B%23FFF%2B%20%26%20%5Ccolor%7B%23FFF%7D%7Btext%7D%20%5C%5C%20%5Chline%20%5Cend%7Barray%7D)

### (5)．添加删除线

使用删除线功能必须声明 `$$` 符号。

在公式内使用 `\require{cancel}` 来允许 **片段删除线** 的显示。
 声明片段删除线后，使用 `\cancel{字符}`、`\bcancel{字符}`、`\xcancel{字符}` 和 `\cancelto{字符}` 来实现各种片段删除线效果。

- 例子：



```ruby
$$
\require{cancel}\begin{array}{rl}
\verb|y+\cancel{x}| & y+\cancel{x}\\
\verb|\cancel{y+x}| & \cancel{y+x}\\
\verb|y+\bcancel{x}| & y+\bcancel{x}\\
\verb|y+\xcancel{x}| & y+\xcancel{x}\\
\verb|y+\cancelto{0}{x}| & y+\cancelto{0}{x}\\
\verb+\frac{1\cancel9}{\cancel95} = \frac15+& \frac{1\cancel9}{\cancel95} = \frac15 \\
\end{array}
$$
```

- 显示：
   ![\require{cancel} \begin{array}{rl} \verb|y+\cancel{x}| & y+\cancel{x}\\ \verb|\cancel{y+x}| & \cancel{y+x}\\ \verb|y+\bcancel{x}| & y+\bcancel{x}\\ \verb|y+\xcancel{x}| & y+\xcancel{x}\\ \verb|y+\cancelto{0}{x}| & y+\cancelto{0}{x}\\ \verb+\frac{1\cancel9}{\cancel95} = \frac15+& \frac{1\cancel9}{\cancel95} = \frac15 \\ \end{array}](https://math.jianshu.com/math?formula=%5Crequire%7Bcancel%7D%20%5Cbegin%7Barray%7D%7Brl%7D%20%5Cverb%7Cy%2B%5Ccancel%7Bx%7D%7C%20%26%20y%2B%5Ccancel%7Bx%7D%5C%5C%20%5Cverb%7C%5Ccancel%7By%2Bx%7D%7C%20%26%20%5Ccancel%7By%2Bx%7D%5C%5C%20%5Cverb%7Cy%2B%5Cbcancel%7Bx%7D%7C%20%26%20y%2B%5Cbcancel%7Bx%7D%5C%5C%20%5Cverb%7Cy%2B%5Cxcancel%7Bx%7D%7C%20%26%20y%2B%5Cxcancel%7Bx%7D%5C%5C%20%5Cverb%7Cy%2B%5Ccancelto%7B0%7D%7Bx%7D%7C%20%26%20y%2B%5Ccancelto%7B0%7D%7Bx%7D%5C%5C%20%5Cverb%2B%5Cfrac%7B1%5Ccancel9%7D%7B%5Ccancel95%7D%20%3D%20%5Cfrac15%2B%26%20%5Cfrac%7B1%5Ccancel9%7D%7B%5Ccancel95%7D%20%3D%20%5Cfrac15%20%5C%5C%20%5Cend%7Barray%7D)

使用 `\require{enclose}` 来允许 **整段删除线** 的显示。
 声明整段删除线后，使用 `\enclose{删除线效果}{字符}` 来实现各种整段删除线效果。
 其中，删除线效果有 `horizontalstrike`、`verticalstrike`、`updiagonalstrike` 和 `downdiagonalstrike`，可叠加使用。

- 例子：



```ruby
$$
\require{enclose}\begin{array}{rl}
\verb|\enclose{horizontalstrike}{x+y}| & \enclose{horizontalstrike}{x+y}\\
\verb|\enclose{verticalstrike}{\frac xy}| & \enclose{verticalstrike}{\frac xy}\\
\verb|\enclose{updiagonalstrike}{x+y}| & \enclose{updiagonalstrike}{x+y}\\
\verb|\enclose{downdiagonalstrike}{x+y}| & \enclose{downdiagonalstrike}{x+y}\\
\verb|\enclose{horizontalstrike,updiagonalstrike}{x+y}| & \enclose{horizontalstrike,updiagonalstrike}{x+y}\\
\end{array}
$$
```

- 显示：
   ![\require{enclose}\begin{array}{rl} \verb|\enclose{horizontalstrike}{x+y}| & \enclose{horizontalstrike}{x+y}\\ \verb|\enclose{verticalstrike}{\frac xy}| & \enclose{verticalstrike}{\frac xy}\\ \verb|\enclose{updiagonalstrike}{x+y}| & \enclose{updiagonalstrike}{x+y}\\ \verb|\enclose{downdiagonalstrike}{x+y}| & \enclose{downdiagonalstrike}{x+y}\\ \verb|\enclose{horizontalstrike,updiagonalstrike}{x+y}| & \enclose{horizontalstrike,updiagonalstrike}{x+y}\\ \end{array}](https://math.jianshu.com/math?formula=%5Crequire%7Benclose%7D%5Cbegin%7Barray%7D%7Brl%7D%20%5Cverb%7C%5Cenclose%7Bhorizontalstrike%7D%7Bx%2By%7D%7C%20%26%20%5Cenclose%7Bhorizontalstrike%7D%7Bx%2By%7D%5C%5C%20%5Cverb%7C%5Cenclose%7Bverticalstrike%7D%7B%5Cfrac%20xy%7D%7C%20%26%20%5Cenclose%7Bverticalstrike%7D%7B%5Cfrac%20xy%7D%5C%5C%20%5Cverb%7C%5Cenclose%7Bupdiagonalstrike%7D%7Bx%2By%7D%7C%20%26%20%5Cenclose%7Bupdiagonalstrike%7D%7Bx%2By%7D%5C%5C%20%5Cverb%7C%5Cenclose%7Bdowndiagonalstrike%7D%7Bx%2By%7D%7C%20%26%20%5Cenclose%7Bdowndiagonalstrike%7D%7Bx%2By%7D%5C%5C%20%5Cverb%7C%5Cenclose%7Bhorizontalstrike%2Cupdiagonalstrike%7D%7Bx%2By%7D%7C%20%26%20%5Cenclose%7Bhorizontalstrike%2Cupdiagonalstrike%7D%7Bx%2By%7D%5C%5C%20%5Cend%7Barray%7D)

此外， `\enclose` 命令还可以产生包围的边框和圆等，参见 [MathML Menclose Documentation](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/menclose) 以查看更多效果。

# 二、矩阵使用参考

## 1．如何输入无框矩阵

在开头使用 `begin{matrix}`，在结尾使用 `end{matrix}`，在中间插入矩阵元素，每个元素之间插入 `&` ，并在每行结尾处使用 `\\` 。
 使用矩阵时必须声明 `$` 或 `$$` 符号。

- 例子：



```ruby
$$
        \begin{matrix}
        1 & x & x^2 \\
        1 & y & y^2 \\
        1 & z & z^2 \\
        \end{matrix}
$$
```

- 显示：
   ![\begin{matrix} 1 & x & x^2 \\ 1 & y & y^2 \\ 1 & z & z^2 \\ \end{matrix}](https://math.jianshu.com/math?formula=%5Cbegin%7Bmatrix%7D%201%20%26%20x%20%26%20x%5E2%20%5C%5C%201%20%26%20y%20%26%20y%5E2%20%5C%5C%201%20%26%20z%20%26%20z%5E2%20%5C%5C%20%5Cend%7Bmatrix%7D)

## 2．如何输入边框矩阵

在开头将 `matrix` 替换为 `pmatrix` `bmatrix` `Bmatrix` `vmatrix` `Vmatrix` 。

- 例子：



```ruby
$ \begin{matrix} 1 & 2 \\ 3 & 4 \\ \end{matrix} $
$ \begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix} $
$ \begin{bmatrix} 1 & 2 \\ 3 & 4 \\ \end{bmatrix} $
$ \begin{Bmatrix} 1 & 2 \\ 3 & 4 \\ \end{Bmatrix} $
$ \begin{vmatrix} 1 & 2 \\ 3 & 4 \\ \end{vmatrix} $
$ \begin{Vmatrix} 1 & 2 \\ 3 & 4 \\ \end{Vmatrix} $
```

- 显示：

|                            matrix                            |                           pmatrix                            |                           bmatrix                            |                           Bmatrix                            |                           vmatrix                            |                           Vmatrix                            |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| ![\begin{matrix} 1 & 2 \\ 3 & 4 \\ \end{matrix}](https://math.jianshu.com/math?formula=%5Cbegin%7Bmatrix%7D%201%20%26%202%20%5C%5C%203%20%26%204%20%5C%5C%20%5Cend%7Bmatrix%7D) | ![\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix}](https://math.jianshu.com/math?formula=%5Cbegin%7Bpmatrix%7D%201%20%26%202%20%5C%5C%203%20%26%204%20%5C%5C%20%5Cend%7Bpmatrix%7D) | ![\begin{bmatrix} 1 & 2 \\ 3 & 4 \\ \end{bmatrix}](https://math.jianshu.com/math?formula=%5Cbegin%7Bbmatrix%7D%201%20%26%202%20%5C%5C%203%20%26%204%20%5C%5C%20%5Cend%7Bbmatrix%7D) | ![\begin{Bmatrix} 1 & 2 \\ 3 & 4 \\ \end{Bmatrix}](https://math.jianshu.com/math?formula=%5Cbegin%7BBmatrix%7D%201%20%26%202%20%5C%5C%203%20%26%204%20%5C%5C%20%5Cend%7BBmatrix%7D) | ![\begin{vmatrix} 1 & 2 \\ 3 & 4 \\ \end{vmatrix}](https://math.jianshu.com/math?formula=%5Cbegin%7Bvmatrix%7D%201%20%26%202%20%5C%5C%203%20%26%204%20%5C%5C%20%5Cend%7Bvmatrix%7D) | ![\begin{Vmatrix} 1 & 2 \\ 3 & 4 \\ \end{Vmatrix}](https://math.jianshu.com/math?formula=%5Cbegin%7BVmatrix%7D%201%20%26%202%20%5C%5C%203%20%26%204%20%5C%5C%20%5Cend%7BVmatrix%7D) |

## 3．如何输入带省略符号的矩阵

使用 `\cdots` ![\cdots](https://math.jianshu.com/math?formula=%5Ccdots) , `\ddots` ![\ddots](https://math.jianshu.com/math?formula=%5Cddots) , `\vdots` ![\vdots](https://math.jianshu.com/math?formula=%5Cvdots) 来输入省略符号。

- 例子：



```ruby
$$
        \begin{pmatrix}
        1 & a_1 & a_1^2 & \cdots & a_1^n \\
        1 & a_2 & a_2^2 & \cdots & a_2^n \\
        \vdots & \vdots & \vdots & \ddots & \vdots \\
        1 & a_m & a_m^2 & \cdots & a_m^n \\
        \end{pmatrix}
$$
```

- 显示：
   ![\begin{pmatrix} 1 & a_1 & a_1^2 & \cdots & a_1^n \\ 1 & a_2 & a_2^2 & \cdots & a_2^n \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 1 & a_m & a_m^2 & \cdots & a_m^n \\ \end{pmatrix}](https://math.jianshu.com/math?formula=%5Cbegin%7Bpmatrix%7D%201%20%26%20a_1%20%26%20a_1%5E2%20%26%20%5Ccdots%20%26%20a_1%5En%20%5C%5C%201%20%26%20a_2%20%26%20a_2%5E2%20%26%20%5Ccdots%20%26%20a_2%5En%20%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cddots%20%26%20%5Cvdots%20%5C%5C%201%20%26%20a_m%20%26%20a_m%5E2%20%26%20%5Ccdots%20%26%20a_m%5En%20%5C%5C%20%5Cend%7Bpmatrix%7D)

## 4．如何输入带分割符号的矩阵

详见"[数组使用参考](#五数组与表格使用参考)"。

- 例子：



```ruby
$$
\left[
    \begin{array}{cc|c}
      1&2&3\\
      4&5&6
    \end{array}
\right]
$$
```

- 显示：
   ![\left[ \begin{array}{cc|c} 1&2&3\\ 4&5&6 \end{array} \right]](https://math.jianshu.com/math?formula=%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bcc%7Cc%7D%201%262%263%5C%5C%204%265%266%20%5Cend%7Barray%7D%20%5Cright%5D)

其中 `cc|c` 代表在一个三列矩阵中的第二和第三列之间插入分割线。

## 5．如何输入行中矩阵

若想在一行内显示矩阵，
 使用`\bigl(\begin{smallmatrix} ... \end{smallmatrix}\bigr)`。

- 例子：



```ruby
这是一个行中矩阵的示例 $\bigl( \begin{smallmatrix} a & b \\ c & d \end{smallmatrix} \bigr)$ 。
```

- 显示：这是一个行中矩阵的示例 ![\bigl( \begin{smallmatrix} a & b \\ c & d \end{smallmatrix} \bigr)](https://math.jianshu.com/math?formula=%5Cbigl(%20%5Cbegin%7Bsmallmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5Cend%7Bsmallmatrix%7D%20%5Cbigr)) 。

# 三、方程式序列使用参考

## 1．如何输入一个方程式序列

人们经常想要一列整齐且居中的方程式序列。使用 `\begin{align}…\end{align}` 来创造一列方程式，其中在每行结尾处使用 `\\` 。
 使用方程式序列无需声明公式符号 `$` 或 `$$` 。

请注意 `{align}` 语句是 **自动编号** 的。

- 例子：



```cpp
\begin{align}
\sqrt{37} & = \sqrt{\frac{73^2-1}{12^2}} \\
 & = \sqrt{\frac{73^2}{12^2}\cdot\frac{73^2-1}{73^2}} \\ 
 & = \sqrt{\frac{73^2}{12^2}}\sqrt{\frac{73^2-1}{73^2}} \\
 & = \frac{73}{12}\sqrt{1 - \frac{1}{73^2}} \\ 
 & \approx \frac{73}{12}\left(1 - \frac{1}{2\cdot73^2}\right)
\end{align}
```

- 显示：
   ![\begin{align} \sqrt{37} & = \sqrt{\frac{73^2-1}{12^2}} \\ & = \sqrt{\frac{73^2}{12^2}\cdot\frac{73^2-1}{73^2}} \\ & = \sqrt{\frac{73^2}{12^2}}\sqrt{\frac{73^2-1}{73^2}} \\ & = \frac{73}{12}\sqrt{1 - \frac{1}{73^2}} \\ & \approx \frac{73}{12}\left(1 - \frac{1}{2\cdot73^2}\right) \end{align}](https://math.jianshu.com/math?formula=%5Cbegin%7Balign%7D%20%5Csqrt%7B37%7D%20%26%20%3D%20%5Csqrt%7B%5Cfrac%7B73%5E2-1%7D%7B12%5E2%7D%7D%20%5C%5C%20%26%20%3D%20%5Csqrt%7B%5Cfrac%7B73%5E2%7D%7B12%5E2%7D%5Ccdot%5Cfrac%7B73%5E2-1%7D%7B73%5E2%7D%7D%20%5C%5C%20%26%20%3D%20%5Csqrt%7B%5Cfrac%7B73%5E2%7D%7B12%5E2%7D%7D%5Csqrt%7B%5Cfrac%7B73%5E2-1%7D%7B73%5E2%7D%7D%20%5C%5C%20%26%20%3D%20%5Cfrac%7B73%7D%7B12%7D%5Csqrt%7B1%20-%20%5Cfrac%7B1%7D%7B73%5E2%7D%7D%20%5C%5C%20%26%20%5Capprox%20%5Cfrac%7B73%7D%7B12%7D%5Cleft(1%20-%20%5Cfrac%7B1%7D%7B2%5Ccdot73%5E2%7D%5Cright)%20%5Cend%7Balign%7D)
   本例中每行公式的编号续自 [如何插入公式](#1如何插入公式) 中的自动编号公式 \eqref{eq:sample} 。

## 2．在一个方程式序列的每一行中注明原因

在 `{align}` 中灵活组合 `\text` 和 `\tag` 语句。`\tag` 语句编号优先级高于自动编号。

- 例子：



```ruby
\begin{align}
   v + w & = 0  &\text{Given} \tag 1\\
   -w & = -w + 0 & \text{additive identity} \tag 2\\
   -w + 0 & = -w + (v + w) & \text{equations $(1)$ and $(2)$}
\end{align}
```

- 显示：
   ![\begin{align} v + w & = 0 &\text{Given} \tag 1\\ -w & = -w + 0 & \text{additive identity} \tag 2\\ -w + 0 & = -w + (v + w) & \text{equations $(1)$ and $(2)$} \end{align}](https://math.jianshu.com/math?formula=%5Cbegin%7Balign%7D%20v%20%2B%20w%20%26%20%3D%200%20%26%5Ctext%7BGiven%7D%20%5Ctag%201%5C%5C%20-w%20%26%20%3D%20-w%20%2B%200%20%26%20%5Ctext%7Badditive%20identity%7D%20%5Ctag%202%5C%5C%20-w%20%2B%200%20%26%20%3D%20-w%20%2B%20(v%20%2B%20w)%20%26%20%5Ctext%7Bequations%20%24(1)%24%20and%20%24(2)%24%7D%20%5Cend%7Balign%7D)
   本例中第一、第二行的自动编号被 `\tag` 语句覆盖，第三行的编号为自动编号。

# 四、条件表达式使用参考

## 1．如何输入一个条件表达式

使用 `begin{cases}` 来创造一组条件表达式，在每一行条件中插入 `&` 来指定需要对齐的内容，并在每一行结尾处使用 `\\`，以 `end{cases}` 结束。
 条件表达式无需声明 `$` 或 `$$` 符号。

- 例子：



```ruby
$$
        f(n) =
        \begin{cases}
        n/2,  & \text{if $n$ is even} \\
        3n+1, & \text{if $n$ is odd}
        \end{cases}
$$
```

- 显示：
   ![f(n) = \begin{cases} n/2, & \text{if $n$ is even} \\ 3n+1, & \text{if $n$ is odd} \end{cases}](https://math.jianshu.com/math?formula=f(n)%20%3D%20%5Cbegin%7Bcases%7D%20n%2F2%2C%20%26%20%5Ctext%7Bif%20%24n%24%20is%20even%7D%20%5C%5C%203n%2B1%2C%20%26%20%5Ctext%7Bif%20%24n%24%20is%20odd%7D%20%5Cend%7Bcases%7D)

## 2．如何输入一个左侧对齐的条件表达式

若想让文字在 **左侧对齐显示** ，则有如下方式：

- 例子：



```ruby
$$
        \left.
        \begin{array}{l}
        \text{if $n$ is even:}&n/2\\
        \text{if $n$ is odd:}&3n+1
        \end{array}
        \right\}
        =f(n)
$$
```

- 显示：
   ![\left. \begin{array}{l} \text{if $n$ is even:}&n/2\\ \text{if $n$ is odd:}&3n+1 \end{array} \right\} =f(n)](https://math.jianshu.com/math?formula=%5Cleft.%20%5Cbegin%7Barray%7D%7Bl%7D%20%5Ctext%7Bif%20%24n%24%20is%20even%3A%7D%26n%2F2%5C%5C%20%5Ctext%7Bif%20%24n%24%20is%20odd%3A%7D%263n%2B1%20%5Cend%7Barray%7D%20%5Cright%5C%7D%20%3Df(n))

## 3．如何使条件表达式适配行高

在一些情况下，条件表达式中某些行的行高为非标准高度，此时使用 `\\[2ex]` 语句代替该行末尾的 `\\` 来让编辑器适配。

- 例子：

| 不适配[2ex] |
| :---------: |
|             |



```ruby
$$
f(n) = 
\begin{cases}
\frac{n}{2},  & \text{if $n$ is even} \\
3n+1, & \text{if $n$ is odd}
\end{cases}
$$
```

| 适配[2ex] |
| :-------: |
|           |



```ruby
$$
f(n) = 
\begin{cases}
\frac{n}{2},  & \text{if $n$ is even} \\[2ex]
3n+1, & \text{if $n$ is odd}
\end{cases}
$$
```

- 显示：

| 不适配[2ex] |
| :---------: |
|             |

![f(n) = \begin{cases} \frac{n}{2}, & \text{if $n$ is even} \\ 3n+1, & \text{if $n$ is odd} \end{cases}](https://math.jianshu.com/math?formula=f(n)%20%3D%20%5Cbegin%7Bcases%7D%20%5Cfrac%7Bn%7D%7B2%7D%2C%20%26%20%5Ctext%7Bif%20%24n%24%20is%20even%7D%20%5C%5C%203n%2B1%2C%20%26%20%5Ctext%7Bif%20%24n%24%20is%20odd%7D%20%5Cend%7Bcases%7D)|

| 适配[2ex] |
| :-------: |
|           |

![f(n) = \begin{cases} \frac{n}{2}, & \text{if $n$ is even} \\[2ex] 3n+1, & \text{if $n$ is odd} \end{cases}](https://math.jianshu.com/math?formula=f(n)%20%3D%20%5Cbegin%7Bcases%7D%20%5Cfrac%7Bn%7D%7B2%7D%2C%20%26%20%5Ctext%7Bif%20%24n%24%20is%20even%7D%20%5C%5C%5B2ex%5D%203n%2B1%2C%20%26%20%5Ctext%7Bif%20%24n%24%20is%20odd%7D%20%5Cend%7Bcases%7D)|

**一个 `[ex]` 指一个 "X-Height"，即x字母高度。可以根据情况指定多个 `[ex]`，如 `[3ex]`、`[4ex]` 等。**
 其实可以在任何地方使用 `\\[2ex]` 语句，只要你觉得合适。

# 五、数组与表格使用参考

## 1．如何输入一个数组或表格

通常，一个格式化后的表格比单纯的文字或排版后的文字更具有可读性。数组和表格均以 `begin{array}` 开头，并在其后定义列数及每一列的文本对齐属性，`c` `l` `r` 分别代表居中、左对齐及右对齐。若需要插入垂直分割线，在定义式中插入 `|` ，若要插入水平分割线，在下一行输入前插入 `\hline` 。与矩阵相似，每行元素间均须要插入 `&` ，每行元素以 `\\` 结尾，最后以 `end{array}` 结束数组。
 使用单个数组或表格时无需声明 `$` 或 `$$` 符号。

- 例子：



```cpp
\begin{array}{c|lcr}
n & \text{左对齐} & \text{居中对齐} & \text{右对齐} \\
\hline
1 & 0.24 & 1 & 125 \\
2 & -1 & 189 & -8 \\
3 & -20 & 2000 & 1+10i
\end{array}
```

- 显示：
   ![\begin{array}{c|lcr} n & \text{左对齐} & \text{居中对齐} & \text{右对齐} \\ \hline 1 & 0.24 & 1 & 125 \\ 2 & -1 & 189 & -8 \\ 3 & -20 & 2000 & 1+10i \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7Bc%7Clcr%7D%20n%20%26%20%5Ctext%7B%E5%B7%A6%E5%AF%B9%E9%BD%90%7D%20%26%20%5Ctext%7B%E5%B1%85%E4%B8%AD%E5%AF%B9%E9%BD%90%7D%20%26%20%5Ctext%7B%E5%8F%B3%E5%AF%B9%E9%BD%90%7D%20%5C%5C%20%5Chline%201%20%26%200.24%20%26%201%20%26%20125%20%5C%5C%202%20%26%20-1%20%26%20189%20%26%20-8%20%5C%5C%203%20%26%20-20%20%26%202000%20%26%201%2B10i%20%5Cend%7Barray%7D)

## 2．如何输入一个嵌套的数组或表格

多个数组/表格可 **互相嵌套** 并组成一组数组/一组表格。
 使用嵌套前必须声明 `$$` 符号。

- 例子：



```cpp
$$
% outer vertical array of arrays 外层垂直表格
\begin{array}{c}
    % inner horizontal array of arrays 内层水平表格
    \begin{array}{cc}
        % inner array of minimum values 内层"最小值"数组
        \begin{array}{c|cccc}
        \text{min} & 0 & 1 & 2 & 3\\
        \hline
        0 & 0 & 0 & 0 & 0\\
        1 & 0 & 1 & 1 & 1\\
        2 & 0 & 1 & 2 & 2\\
        3 & 0 & 1 & 2 & 3
        \end{array}
    &
        % inner array of maximum values 内层"最大值"数组
        \begin{array}{c|cccc}
        \text{max}&0&1&2&3\\
        \hline
        0 & 0 & 1 & 2 & 3\\
        1 & 1 & 1 & 2 & 3\\
        2 & 2 & 2 & 2 & 3\\
        3 & 3 & 3 & 3 & 3
        \end{array}
    \end{array}
    % 内层第一行表格组结束
    \\
    % inner array of delta values 内层第二行Delta值数组
        \begin{array}{c|cccc}
        \Delta&0&1&2&3\\
        \hline
        0 & 0 & 1 & 2 & 3\\
        1 & 1 & 0 & 1 & 2\\
        2 & 2 & 1 & 0 & 1\\
        3 & 3 & 2 & 1 & 0
        \end{array}
        % 内层第二行表格组结束
\end{array}
$$
```

- 显示：

![% outer vertical array of arrays 外层垂直表格 \begin{array}{c} % inner horizontal array of arrays 内层水平表格 \begin{array}{cc} % inner array of minimum values 内层"最小值"数组 \begin{array}{c|cccc} \text{min} & 0 & 1 & 2 & 3\\ \hline 0 & 0 & 0 & 0 & 0\\ 1 & 0 & 1 & 1 & 1\\ 2 & 0 & 1 & 2 & 2\\ 3 & 0 & 1 & 2 & 3 \end{array} & % inner array of maximum values 内层"最大值"数组 \begin{array}{c|cccc} \text{max}&0&1&2&3\\ \hline 0 & 0 & 1 & 2 & 3\\ 1 & 1 & 1 & 2 & 3\\ 2 & 2 & 2 & 2 & 3\\ 3 & 3 & 3 & 3 & 3 \end{array} \end{array} % 内层第一行表格组结束 \\ % inner array of delta values 内层第二行Delta值数组 \begin{array}{c|cccc} \Delta&0&1&2&3\\ \hline 0 & 0 & 1 & 2 & 3\\ 1 & 1 & 0 & 1 & 2\\ 2 & 2 & 1 & 0 & 1\\ 3 & 3 & 2 & 1 & 0 \end{array} % 内层第二行表格组结束 \end{array}](https://math.jianshu.com/math?formula=%25%20outer%20vertical%20array%20of%20arrays%20%E5%A4%96%E5%B1%82%E5%9E%82%E7%9B%B4%E8%A1%A8%E6%A0%BC%20%5Cbegin%7Barray%7D%7Bc%7D%20%25%20inner%20horizontal%20array%20of%20arrays%20%E5%86%85%E5%B1%82%E6%B0%B4%E5%B9%B3%E8%A1%A8%E6%A0%BC%20%5Cbegin%7Barray%7D%7Bcc%7D%20%25%20inner%20array%20of%20minimum%20values%20%E5%86%85%E5%B1%82%22%E6%9C%80%E5%B0%8F%E5%80%BC%22%E6%95%B0%E7%BB%84%20%5Cbegin%7Barray%7D%7Bc%7Ccccc%7D%20%5Ctext%7Bmin%7D%20%26%200%20%26%201%20%26%202%20%26%203%5C%5C%20%5Chline%200%20%26%200%20%26%200%20%26%200%20%26%200%5C%5C%201%20%26%200%20%26%201%20%26%201%20%26%201%5C%5C%202%20%26%200%20%26%201%20%26%202%20%26%202%5C%5C%203%20%26%200%20%26%201%20%26%202%20%26%203%20%5Cend%7Barray%7D%20%26%20%25%20inner%20array%20of%20maximum%20values%20%E5%86%85%E5%B1%82%22%E6%9C%80%E5%A4%A7%E5%80%BC%22%E6%95%B0%E7%BB%84%20%5Cbegin%7Barray%7D%7Bc%7Ccccc%7D%20%5Ctext%7Bmax%7D%260%261%262%263%5C%5C%20%5Chline%200%20%26%200%20%26%201%20%26%202%20%26%203%5C%5C%201%20%26%201%20%26%201%20%26%202%20%26%203%5C%5C%202%20%26%202%20%26%202%20%26%202%20%26%203%5C%5C%203%20%26%203%20%26%203%20%26%203%20%26%203%20%5Cend%7Barray%7D%20%5Cend%7Barray%7D%20%25%20%E5%86%85%E5%B1%82%E7%AC%AC%E4%B8%80%E8%A1%8C%E8%A1%A8%E6%A0%BC%E7%BB%84%E7%BB%93%E6%9D%9F%20%5C%5C%20%25%20inner%20array%20of%20delta%20values%20%E5%86%85%E5%B1%82%E7%AC%AC%E4%BA%8C%E8%A1%8CDelta%E5%80%BC%E6%95%B0%E7%BB%84%20%5Cbegin%7Barray%7D%7Bc%7Ccccc%7D%20%5CDelta%260%261%262%263%5C%5C%20%5Chline%200%20%26%200%20%26%201%20%26%202%20%26%203%5C%5C%201%20%26%201%20%26%200%20%26%201%20%26%202%5C%5C%202%20%26%202%20%26%201%20%26%200%20%26%201%5C%5C%203%20%26%203%20%26%202%20%26%201%20%26%200%20%5Cend%7Barray%7D%20%25%20%E5%86%85%E5%B1%82%E7%AC%AC%E4%BA%8C%E8%A1%8C%E8%A1%A8%E6%A0%BC%E7%BB%84%E7%BB%93%E6%9D%9F%20%5Cend%7Barray%7D)

## 3．如何输入一个方程组

使用 `\begin{array}…\end{array}` 和 `\left\{…\right.` 来创建一个方程组。

- 例子：



```ruby
$$
\left\{ 
\begin{array}{c}
a_1x+b_1y+c_1z=d_1 \\ 
a_2x+b_2y+c_2z=d_2 \\ 
a_3x+b_3y+c_3z=d_3
\end{array}
\right. 
$$
```

- 显示：
   ![\left\{ \begin{array}{c} a_1x+b_1y+c_1z=d_1 \\ a_2x+b_2y+c_2z=d_2 \\ a_3x+b_3y+c_3z=d_3 \end{array} \right.](https://math.jianshu.com/math?formula=%5Cleft%5C%7B%20%5Cbegin%7Barray%7D%7Bc%7D%20a_1x%2Bb_1y%2Bc_1z%3Dd_1%20%5C%5C%20a_2x%2Bb_2y%2Bc_2z%3Dd_2%20%5C%5C%20a_3x%2Bb_3y%2Bc_3z%3Dd_3%20%5Cend%7Barray%7D%20%5Cright.)

或者使用条件表达式组 `\begin{cases}…\end{cases}` 来实现相同效果：

- 例子：



```ruby
\begin{cases}
a_1x+b_1y+c_1z=d_1 \\ 
a_2x+b_2y+c_2z=d_2 \\ 
a_3x+b_3y+c_3z=d_3
\end{cases}
```

- 显示：
   ![\begin{cases} a_1x+b_1y+c_1z=d_1 \\ a_2x+b_2y+c_2z=d_2 \\ a_3x+b_3y+c_3z=d_3 \end{cases}](https://math.jianshu.com/math?formula=%5Cbegin%7Bcases%7D%20a_1x%2Bb_1y%2Bc_1z%3Dd_1%20%5C%5C%20a_2x%2Bb_2y%2Bc_2z%3Dd_2%20%5C%5C%20a_3x%2Bb_3y%2Bc_3z%3Dd_3%20%5Cend%7Bcases%7D)

# 六、连分数使用参考

## 1．如何输入一个连分式

就像输入分式时使用 `\frac` 一样，使用 `\cfrac` 来创建一个连分数。

- 例子：



```ruby
$$
x = a_0 + \cfrac{1^2}{a_1
          + \cfrac{2^2}{a_2
          + \cfrac{3^2}{a_3 + \cfrac{4^4}{a_4 + \cdots}}}}
$$
```

- 显示：
   ![x = a_0 + \cfrac{1^2}{a_1 + \cfrac{2^2}{a_2 + \cfrac{3^2}{a_3 + \cfrac{4^4}{a_4 + \cdots}}}}](https://math.jianshu.com/math?formula=x%20%3D%20a_0%20%2B%20%5Ccfrac%7B1%5E2%7D%7Ba_1%20%2B%20%5Ccfrac%7B2%5E2%7D%7Ba_2%20%2B%20%5Ccfrac%7B3%5E2%7D%7Ba_3%20%2B%20%5Ccfrac%7B4%5E4%7D%7Ba_4%20%2B%20%5Ccdots%7D%7D%7D%7D)

不要使用普通的 `\frac` 或 `\over` 来创建，否则会看起来 **很恶心** 。

- 反例：



```ruby
$$
x = a_0 + \frac{1^2}{a_1
          + \frac{2^2}{a_2
          + \frac{3^2}{a_3 + \frac{4^4}{a_4 + \cdots}}}}
$$
```

- 显示：
   ![x = a_0 + \frac{1^2}{a_1 + \frac{2^2}{a_2 + \frac{3^2}{a_3 + \frac{4^4}{a_4 + \cdots}}}}](https://math.jianshu.com/math?formula=x%20%3D%20a_0%20%2B%20%5Cfrac%7B1%5E2%7D%7Ba_1%20%2B%20%5Cfrac%7B2%5E2%7D%7Ba_2%20%2B%20%5Cfrac%7B3%5E2%7D%7Ba_3%20%2B%20%5Cfrac%7B4%5E4%7D%7Ba_4%20%2B%20%5Ccdots%7D%7D%7D%7D)

当然，你可以使用 `\frac` 来表达连分数的 **紧缩记法** 。

- 例子：



```ruby
$$
x = a_0 + \frac{1^2}{a_1+}
          \frac{2^2}{a_2+}
          \frac{3^2}{a_3 +} \frac{4^4}{a_4 +} \cdots
$$
```

- 显示：
   ![x = a_0 + \frac{1^2}{a_1+} \frac{2^2}{a_2+} \frac{3^2}{a_3 +} \frac{4^4}{a_4 +} \cdots](https://math.jianshu.com/math?formula=x%20%3D%20a_0%20%2B%20%5Cfrac%7B1%5E2%7D%7Ba_1%2B%7D%20%5Cfrac%7B2%5E2%7D%7Ba_2%2B%7D%20%5Cfrac%7B3%5E2%7D%7Ba_3%20%2B%7D%20%5Cfrac%7B4%5E4%7D%7Ba_4%20%2B%7D%20%5Ccdots)

连分数通常都太大以至于不易排版，所以建议在连分数前后声明 `$$` 符号，或使用像 `[a0;a1,a2,a3,…]` 一样的紧缩记法。

# 七、交换图表使用参考

## 1．如何输入一个交换图表

使用一行 `$ \require{AMScd} $` 语句来允许交换图表的显示。
 声明交换图表后，语法与矩阵相似，在开头使用 `begin{CD}`，在结尾使用 `end{CD}`，在中间插入图表元素，每个元素之间插入 `&` ，并在每行结尾处使用 `\\` 。

- 例子：



```ruby
$\require{AMScd}$
\begin{CD}
    A @>a>> B\\
    @V b V V\# @VV c V\\
    C @>>d> D
\end{CD}
```

- 显示：

![\require{AMScd}$ \begin{CD} A @>a>> B\\ @V b V V\# @VV c V\\ C @>>d> D \end{CD}](https://math.jianshu.com/math?formula=%5Crequire%7BAMScd%7D%24%20%5Cbegin%7BCD%7D%20A%20%40%3Ea%3E%3E%20B%5C%5C%20%40V%20b%20V%20V%5C%23%20%40VV%20c%20V%5C%5C%20C%20%40%3E%3Ed%3E%20D%20%5Cend%7BCD%7D)

其中，`@>>>` 代表右箭头、`@<<<` 代表左箭头、`@VVV` 代表下箭头、`@AAA` 代表上箭头、`@=` 代表水平双实线、`@|` 代表竖直双实线、`@.`代表没有箭头。
 在 `@>>>` 的 `>>>` 之间任意插入文字即代表该箭头的注释文字。

- 例子：



```ruby
\begin{CD}
    A @>>> B @>{\text{very long label}}>> C \\
    @. @AAA @| \\
    D @= E @<<< F
\end{CD}
```

- 显示：
   ![\begin{CD} A @>>> B @>{\text{very long label}}>> C \\ @. @AAA @| \\ D @= E @<<< F \end{CD}](https://math.jianshu.com/math?formula=%5Cbegin%7BCD%7D%20A%20%40%3E%3E%3E%20B%20%40%3E%7B%5Ctext%7Bvery%20long%20label%7D%7D%3E%3E%20C%20%5C%5C%20%40.%20%40AAA%20%40%7C%20%5C%5C%20D%20%40%3D%20E%20%40%3C%3C%3C%20F%20%5Cend%7BCD%7D)
   在本例中， "very long label"自动延长了它所在箭头以及对应箭头的长度。

# 八、一些特殊的注意事项

**!! 本段内容为个人翻译，可能有不准确之处 !!**

These are issues that won't affect the correctness of formulas, but might make them look significantly better or worse. Beginners should feel free to ignore this advice; someone else will correct it for them, or more likely nobody will care.

现在指出的小问题并不会影响方程式及公式等的正确显示，但能让它们看起来明显更好看。初学者可无视这些建议，自然会有强迫症患者替你们改掉它的，或者更可能地，根本没人发现这些问题。

Don't use `\frac` in exponents or limits of integrals; it looks bad and can be confusing, which is why it is rarely done in professional mathematical typesetting. Write the fraction horizontally, with a slash:

在以e为底的指数函数、极限和积分中尽量不要使用 `\frac` 符号：它会使整段函数看起来很怪，而且可能产生歧义。也正是因此它在专业数学排版中几乎从不出现。
 横着写这些分式，中间使用斜线间隔 `/` （用斜线代替分数线）。

- 例子：



```cpp
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
e^{i\frac{\pi}2} \quad e^{\frac{i\pi}2}& e^{i\pi/2} \\
\int_{-\frac\pi2}^\frac\pi2 \sin x\,dx & \int_{-\pi/2}^{\pi/2}\sin x\,dx \\
\end{array}
```

- 显示：
   ![\begin{array}{cc} \mathrm{Bad} & \mathrm{Better} \\ \hline \\ e^{i\frac{\pi}2} \quad e^{\frac{i\pi}2}& e^{i\pi/2} \\ \int_{-\frac\pi2}^\frac\pi2 \sin x\,dx & \int_{-\pi/2}^{\pi/2}\sin x\,dx \\ \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7Bcc%7D%20%5Cmathrm%7BBad%7D%20%26%20%5Cmathrm%7BBetter%7D%20%5C%5C%20%5Chline%20%5C%5C%20e%5E%7Bi%5Cfrac%7B%5Cpi%7D2%7D%20%5Cquad%20e%5E%7B%5Cfrac%7Bi%5Cpi%7D2%7D%26%20e%5E%7Bi%5Cpi%2F2%7D%20%5C%5C%20%5Cint_%7B-%5Cfrac%5Cpi2%7D%5E%5Cfrac%5Cpi2%20%5Csin%20x%5C%2Cdx%20%26%20%5Cint_%7B-%5Cpi%2F2%7D%5E%7B%5Cpi%2F2%7D%5Csin%20x%5C%2Cdx%20%5C%5C%20%5Cend%7Barray%7D)
   The `|` symbol has the wrong spacing when it is used as a divider, for example in set comprehensions. Use `\mid` instead:

`|` 符号在被当作分隔符时会产生错误的间隔，因此在需要分隔时最好使用 `\mid` 来代替它。

- 例子:



```cpp
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
\{x|x^2\in\Bbb Z\} & \{x\mid x^2\in\Bbb Z\} \\
\end{array}
```

- 显示：
   ![\begin{array}{cc} \mathrm{Bad} & \mathrm{Better} \\ \hline \\ \{x|x^2\in\Bbb Z\} & \{x\mid x^2\in\Bbb Z\} \\ \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7Bcc%7D%20%5Cmathrm%7BBad%7D%20%26%20%5Cmathrm%7BBetter%7D%20%5C%5C%20%5Chline%20%5C%5C%20%5C%7Bx%7Cx%5E2%5Cin%5CBbb%20Z%5C%7D%20%26%20%5C%7Bx%5Cmid%20x%5E2%5Cin%5CBbb%20Z%5C%7D%20%5C%5C%20%5Cend%7Barray%7D)
   For double and triple integrals, don't use `\int\int` or `\int\int\int`. Instead use the special forms `\iint` and `\iiint`:

使用多重积分符号时，不要多次使用 `\int` 来声明，直接使用 `\iint` 来表示 **二重积分** ，使用 `\iiint` 来表示 **三重积分** 等。对于无限次积分，可以用 `\int \cdots \int` 表示。

- 例子：



```csharp
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
\int\int_S f(x)\,dy\,dx & \iint_S f(x)\,dy\,dx \\
\int\int\int_V f(x)\,dz\,dy\,dx & \iiint_V f(x)\,dz\,dy\,dx
\end{array}
```

- 显示：
   ![\begin{array}{cc} \mathrm{Bad} & \mathrm{Better} \\ \hline \\ \int\int_S f(x)\,dy\,dx & \iint_S f(x)\,dy\,dx \\ \int\int\int_V f(x)\,dz\,dy\,dx & \iiint_V f(x)\,dz\,dy\,dx \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7Bcc%7D%20%5Cmathrm%7BBad%7D%20%26%20%5Cmathrm%7BBetter%7D%20%5C%5C%20%5Chline%20%5C%5C%20%5Cint%5Cint_S%20f(x)%5C%2Cdy%5C%2Cdx%20%26%20%5Ciint_S%20f(x)%5C%2Cdy%5C%2Cdx%20%5C%5C%20%5Cint%5Cint%5Cint_V%20f(x)%5C%2Cdz%5C%2Cdy%5C%2Cdx%20%26%20%5Ciiint_V%20f(x)%5C%2Cdz%5C%2Cdy%5C%2Cdx%20%5Cend%7Barray%7D)
   ![无限次积分：\int \cdots \int](https://math.jianshu.com/math?formula=%E6%97%A0%E9%99%90%E6%AC%A1%E7%A7%AF%E5%88%86%EF%BC%9A%5Cint%20%5Ccdots%20%5Cint)

Use `\,`, to insert a thin space before differentials; without this ![\TeX](https://math.jianshu.com/math?formula=%5CTeX) will mash them together:

在微分符号前加入 `\,` 来插入一个小的间隔空隙；没有 `\,` 符号的话，![\TeX](https://math.jianshu.com/math?formula=%5CTeX) 将会把不同的微分符号堆在一起。

- 例子：



```csharp
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
\iiint_V f(x){\rm d}z {\rm d}y {\rm d}x & \iiint_V f(x)\,{\rm d}z\,{\rm d}y\,{\rm d}x
\end{array}
```

- 显示：
   ![\begin{array}{cc} \mathrm{Bad} & \mathrm{Better} \\ \hline \\ \iiint_V f(x){\rm d}z {\rm d}y {\rm d}x & \iiint_V f(x)\,{\rm d}z\,{\rm d}y\,{\rm d}x \end{array}](https://math.jianshu.com/math?formula=%5Cbegin%7Barray%7D%7Bcc%7D%20%5Cmathrm%7BBad%7D%20%26%20%5Cmathrm%7BBetter%7D%20%5C%5C%20%5Chline%20%5C%5C%20%5Ciiint_V%20f(x)%7B%5Crm%20d%7Dz%20%7B%5Crm%20d%7Dy%20%7B%5Crm%20d%7Dx%20%26%20%5Ciiint_V%20f(x)%5C%2C%7B%5Crm%20d%7Dz%5C%2C%7B%5Crm%20d%7Dy%5C%2C%7B%5Crm%20d%7Dx%20%5Cend%7Barray%7D)

