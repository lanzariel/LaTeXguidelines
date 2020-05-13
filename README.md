# LaTeX Guidelines

Remember that whenever you see something like 

![Overleaf Error](/OverError.png)


It means that you made a mistake. You have to fix it before the submission. Click on it to have additional information!
For example, clicking on this specific error we get 

![Overleaf Error 1](/WrongNewline.png)


It is very useful to know that:
 * The problem was a misplaced newline.
 * The problem is at line 127

Sometimes you could see a pdf even if there are errors. This does not mean that everything is fine!!!

## Equations

### Basic knowledge

There are several **not equivalent** ways to write an equation in LaTeX:

 * *inline equations*. Is when you place a single dollar signs at both ends, i.e., `$ equation_code $`. It should be used only when you need a few maths symbols inside a text. You should not use it to write long equations.
 * *numbered equations at a new line*. Is by far the best way to write an equation
 ```
\begin{equation}
equation_code
\end{equation}
```
 * *not numbered equations (at new line)* (which I discourage). Can be obtained in one of the following:
    *  Double dollar sign, i.e.,  `$$ equation_code $$`
    *  Square breakets sign, i.e.,  `\[ equation_code \]`

**Please, don't force a newline, write an inline equation and then force a newline again, i.e.**
```
\\
$ equation_code $ \\
```
**Is REALLY BAD.**

Use instead:
```
\begin{equation}
equation_code
\end{equation}
```

### Numbering

I think that every equation or group of equations should be numbered (very handy whenever you or anyone who is correcting your work should point out something at a specific point). This translates to

**Use**
```
\begin{equation}
equation_code
\end{equation}
```
**whenever possible.**

If you need an equation that lasts more than one line I personally prefer the sub-enviroment `aligned` to the evironment `align` in order to keep only one number.

**Use**
```
\begin{equation}
\begin{aligned}
equation_code_left_aligned1 & equation_code_right_aligned1 \\
equation_code_left_aligned2 & equation_code_right_aligned2
\end{aligned}
\end{equation}
```
**Instead of**
```
\begin{align}
equation_code_left_aligned1 & equation_code_right_aligned1 \\
equation_code_left_aligned2 & equation_code_right_aligned2
\end{align}
```
**And NEVER do**
```
\begin{equation}
equation_code_left_aligned1 equation_code_right_aligned1
\end{equation}
\begin{equation}
equation_code_left_aligned2 equation_code_right_aligned2
\end{equation}
```

Remember that the numbering is done automatically. If you need a reference to an equation, **don't** read the equation number in the pdf and reference it as plain text, as in
```
\begin{equation}
equation_code
\end{equation}
from Equation (7) we conclude ...
```
This is a problem: whenever you or some of your coworkers will add a numbered equation before the one you are referencing, the numbering will be shifted.

Instead, label the equation with `\label{}` and call the label whenever you need a reference to the equation with `\eqref{}`. For example:
```
\begin{equation}\label{1:finalpoint}
equation_code
\end{equation}
from Equation \eqref{1:finalpoint} we conclude ...
```
As a best practice, begin all your labels with your problem number, in this way the same label for different problems won't conflict.


## Newlines

LaTeX sometimes might prevent you from going to a new line for many different reasons, and often that will raise an error.
It is often the case that you might want to skip two lines instead of just one or to go to a newline after the beginning of a theorem or an exercise. You can use workarounds such as


**good:**
```
\begin{exo} $ $\\
my exercise
\end{exo}
```

**wrong:**
```
\begin{exo}\\
my exercise
\end{exo}
```

Remember that Google and tex.stackexchange are your friends.
For example see [Theorem environment - line break after label [duplicate]](https://tex.stackexchange.com/questions/37797/theorem-environment-line-break-after-label/37805)

## Other style tips

Remember that there is a difference between the product of the tree variables `m`, `a` and `x` and the symbol used for the maximum, i.e. `\max`. In the same way, it is a best practice to write `\min`, `\argmax`, `\log` or `\cos` instead of `min`, `argmax`, `log` or `cos`.

If the symbol you are trying to use is not a LaTeX command (for example Var, to indicate variance), you can use the command mathrm, i.e. `\mathrm{Var}`

It might happen that you put between parenthesis some text that is displayed bigger than the parenthesis themselves (for example you might use `\sum` or `\int` or some fractions with `\frac{numerator}{denominator}`. To have the parenthesis automatically adjust, remember to use `\left` and `\right`. For example
```
(bigtext)
```
would become 
```
\left (
bigtext
\right )
```

### Example
Can you see the difference between
```
\begin{equation}
V(k,K,s,z)=max_{c,k'}
[
log(c) + 
\beta \sum_{s'} \sum_{z'}
\pi_{z z' s s'} V(k',K', s', z')
]
\end{equation}
```
<p align="center">
<img src="/BadDisplay.png">
</p>
and
```
\begin{equation}
V(k,K,s,z)=\max_{c,k'}
\left [
log(c) + 
\beta \sum_{s'} \sum_{z'}
\pi_{z z' s s'} V(k',K', s', z')
\right ]
\end{equation}
```
<p align="center">
<img src="/GoodDisplay.png">
</p>
?
