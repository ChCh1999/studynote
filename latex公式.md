# Latex公式

### 希腊字母

> | 命令     | 显示 | 命令   | 显示 |
> | -------- | ---- | ------ | ---- |
> | \alpha   | αα   | \beta  | ββ   |
> | \gamma   | γγ   | \delta | δδ   |
> | \epsilon | ϵϵ   | \zeta  | ζζ   |
> | \eta     | ηη   | \theta | θθ   |
> | \iota    | ιι   | \kappa | κκ   |
> | \lambda  | λλ   | \mu    | μμ   |
> | \xi      | ξξ   | \nu    | νν   |
> | \pi      | ππ   | \rho   | ρρ   |
> | \sigma   | σσ   | \tau   | ττ   |
> | \upsilon | υυ   | \phi   | ϕϕ   |
> | \chi     | χχ   | \psi   | ψψ   |
> | \omega   | ωω   |        |      |

如果使用大写的希腊字母，把命令的首字母变成大写即可，例如 `\Gamma` 输出的是 ΓΓ。

如果使用斜体大写希腊字母，再在大写希腊字母的*LaTeX*命令前加上var，例如`\varGamma` 生成 ΓΓ。

例如：

```latex
$$
 \varGamma(x) = \frac{\int_{\alpha}^{\beta} g(t)(x-t)^2\text{ d}t }{\phi(x)\sum_{i=0}^{N-1} \omega_i} \tag{2}
$$
```


$$
\varGamma(x) = \frac{\int_{\alpha}^{\beta} g(t)(x-t)^2\text{ d}t }{\phi(x)\sum_{i=0}^{N-1} \omega_i} \tag{2}
$$


### **和号和积分号**

下面列出常用的和号与积分号：

> | 命令              | 显示       |      | 命令              | 显示               |
> | ----------------- | ---------- | ---- | ----------------- | ------------------ |
> | \sum              | ∑∑         |      | \int              | ∫∫                 |
> | \sum_{i=1}^{N}    | ∑Ni=1∑i=1N |      | \int_{a}^{b}      | ∫ba∫ab             |
> | \prod             | ∏∏         |      | \iint             | ∬∬                 |
> | \prod_{i=1}^{N}   | ∏Ni=1∏i=1N |      | \iint_{a}^{b}     | ∬ba∬ab             |
> | \bigcup           | ⋃⋃         |      | \bigcap           | ⋂⋂                 |
> | \bigcup_{i=1}^{N} | ⋃Ni=1⋃i=1N |      | \bigcap_{i=1}^{N} | $\bigcap_{i=1}^{N} |

### **其它常用命令**

> | 命令           | 显示         |      | 命令        | 显示 |
> | -------------- | ------------ | ---- | ----------- | ---- |
> | \sqrt[3]{2}    | 2–√323       |      | \sqrt{2}    | 2–√2 |
> | x^{3}          | x3x3         |      | x_{3}       | x3x3 |
> | \lim_{x \to 0} | limx→0limx→0 |      | \frac{1}{2} | 12   |