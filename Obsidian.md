---
date: 2025-06-27
aliases:
  - How to use Obsidian
tags:
  - Obsidian
---
# heading 1
- bullet point (- )
- ==highlight== (== )
- **bold** (** )
- *Italic* (* )
- ~~strikethrough~~ (~~ )
	- tab
1. list1
2. list2
	1. 2-1
Todo list:
- [ ] (- [ ] )
- [x] task2
- [ ] command+L

## heading 2
- link [[Welcome]] ([[ )
- link word [[Welcome|word]] 
- link paragraph [[Welcome#heading]]
- link sentence [[Welcome#^d7123f]]
- insert link ![[Welcome]]
- link outside [google](https://www.google.com)

### heading 3
Quote: 
>this is something i said
>--by chris
>>this is also something i said
>>--by chris

Callout: 
note/abstract/summary/tldr/info/todo/tip/hint/important/success/check/done/question/help/faq/
warning/caution/attention/failure/fail/missing/danger/error/bug/example/quote/cite
> [!INFO] info
>> [!important]

> [!question]- something
> 1. first
> 2. second
> 3. third

> [!error]

> [!example] e.p.1
> 12345


Footnote:  [^1]
maybe ^[this is another footnote]
[^1]: this is a footnote
	yes
	alright

# Table

| head 1 | head 2 |     |
| ------ | ------ | --- |
|        |        |     |

# Image
some words some sentences some phrases to add images

# Math

| 类别       | 名称      | LaTeX 代码                                  | 显示效果            |
| :------- | :------ | :---------------------------------------- | :-------------- |
| **希腊字母** | Alpha   | `\alpha`                                  | α               |
|          | Beta    | `\beta`                                   | β               |
|          | Gamma   | `\gamma`, `\Gamma`                        | γ, Γ            |
|          | Delta   | `\delta`, `\Delta`                        | δ, Δ            |
|          | Epsilon | `\epsilon`, `\varepsilon`                 | ε, ε            |
|          | Theta   | `\theta`, `\Theta`                        | θ, Θ            |
|          | Lambda  | `\lambda`, `\Lambda`                      | λ, Λ            |
|          | Pi      | `\pi`, `\Pi`                              | π, Π            |
|          | Rho     | `\rho`, `\varrho`                         | ρ, ϱ            |
|          | Sigma   | `\sigma`, `\Sigma`                        | σ, Σ            |
|          | Phi     | `\phi`, `\varphi`, `\Phi`                 | φ, φ, Φ         |
|          | Omega   | `\omega`, `\Omega`                        | ω, Ω            |
| **上下标**  | 上标      | `x^2`, `e^{-x}`, `a^{n+1}`                | x², e⁻ˣ, aⁿ⁺¹   |
|          | 下标      | `x_i`, `x_{n-1}`                          | xᵢ, xₙ₋₁        |
|          | 上下标     | `x_i^2`, `x^2_i`                          | xᵢ², xᵢ²        |
| **分数**   | 分数      | `\frac{a}{b}`                             | a/b             |
|          | 大分数     | `\dfrac{a}{b}`                            | a/b             |
|          | 小分数     | `\tfrac{a}{b}`                            | a/b             |
|          | 斜线分数    | `a/b`                                     | a/b             |
| **积分**   | 不定积分    | `\int f(x) \, dx`                         | ∫f(x) dx        |
|          | 定积分     | `\int_{a}^{b} f(x) \, dx`                 | ∫ₐᵇ f(x) dx     |
|          | 二重积分    | `\iint\limits_{D} f(x,y) \, dxdy`         | ∬_D f(x,y) dxdy |
|          | 三重积分    | `\iiint\limits_{V} f(x,y,z) \, dV`        | ∭_V f(x,y,z) dV |
|          | 环路积分    | `\oint\limits_{C} \vec{F} \cdot d\vec{r}` | ∮_C F·dr        |
| **运算符**  | 加减乘除    | `\pm`, `\mp`, `\times`, `\div`            | ±, ∓, ×, ÷      |
|          | 点乘      | `\cdot`                                   | ⋅               |
|          | 比较      | `\leq`, `\geq`, `\neq`, `\approx`         | ≤, ≥, ≠, ≈      |
|          | 恒等      | `\equiv`                                  | ≡               |
|          | 无穷      | `\infty`                                  | ∞               |
|          | 微分      | `\partial`, `\nabla`                      | ∂, ∇            |
|          | 求和求积    | `\sum`, `\prod`                           | ∑, ∏            |
|          | 根号      | `\sqrt{x}`, `\sqrt[n]{x}`                 | √x, ⁿ√x         |
| **箭头**   | 单箭头     | `\to`, `\rightarrow`, `\leftarrow`        | →, →, ←         |
|          | 双箭头     | `\Rightarrow`, `\Leftarrow`               | ⇒, ⇐            |
|          | 双向箭头    | `\leftrightarrow`, `\Leftrightarrow`      | ↔, ⇔            |
|          | 映射      | `\mapsto`                                 | ↦               |
|          | 长箭头     | `\longrightarrow`                         | ⟶               |
| **其他符号** | 度       | `90^\circ`                                | 90°             |
|          | 角       | `\angle`                                  | ∠               |
|          | 三角形     | `\triangle`                               | △               |
|          | 因为所以    | `\because`, `\therefore`                  | ∵, ∴            |
|          | 空集      | `\emptyset`                               | ∅               |
|          | 属于      | `\in`, `\notin`                           | ∈, ∉            |
|          | 子集      | `\subset`                                 | ⊂               |
|          | 集合运算    | `\cup`, `\cap`                            | ∪, ∩            |
|          | 逻辑符号    | `\forall`, `\exists`, `\neg`              | ∀, ∃, ¬         |
|          | 异或      | `\oplus`                                  | ⊕               |
| **括号**   | 小括号     | `( )`                                     | ( )             |
|          | 中括号     | `[ ]`                                     | [ ]             |
|          | 大括号     | `\{ \}`                                   | { }             |
|          | 尖括号     | `\langle \rangle`                         | ⟨ ⟩             |
|          | 绝对值     | `\| \|`                                   | ‖ ‖             |
|          | 取整      | `\lfloor \rfloor`, `\lceil \rceil`        | ⌊ ⌋, ⌈ ⌉        |
| **格式**   | 粗体      | `\mathbf{x}`                              | **x**           |
|          | 斜体      | `\mathit{x}`                              | *x*             |
|          | 空格      | `\,`, `\:`, `\;`, `\quad`, `\qquad`       | 小,中,大,更大空格      |
|          | 换行      | `\\`                                      | 换行              |
|          | 对齐      | `&`                                       | 对齐点             |
|          | 文本      | `\text{文字}`                               | 文字              |
