## NAG
**NAG (Nesterov's accelerated gradient)** - [[SGD with Momentum]] с "умным" вычислением градиента в особой точке.
*[Ю. Е. Нестеров, 1983]*

$$
\begin{aligned}
v &:=\gamma v+(1-\gamma) \mathscr{L}_{i}^{\prime}(w-h \gamma v) \\
w &:=w-h v
\end{aligned}
$$

**Улучшения:**
* [[Nadam]]