# LaTeX Guidelines

Remember that whenever you see something like 

![Overleaf Error](/OverError.png)


It means that you did a mistake. You have to fix it before the submission. Click on it to have additional information!
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



# Newlines
