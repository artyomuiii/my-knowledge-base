## Nadam
**Nadam (Nesterov-accelerated Adaptive Momentum)** = [[Adam]] + [[NAG]]

$$
w:=w-\eta\left(\gamma \hat{v}+\frac{1-\gamma}{1-\gamma^{k}} \mathscr{L}_{i}^{\prime}(w)\right) \oslash(\sqrt{\hat{G}}+\varepsilon)
$$