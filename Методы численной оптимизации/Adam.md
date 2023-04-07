## Adam
**Adam (Adaptive Momentum)** = [[SGD with Momentum]] + [[RMSProp]]

$$
\begin{array}{ll}
v:=\gamma v+(1-\gamma) \mathscr{L}_{i}^{\prime}(w) & \hat{v}:=v\left(1-\gamma^{k}\right)^{-1} \\
G:=\alpha G+(1-\alpha) \mathscr{L}_{i}^{\prime}(w) \odot \mathscr{L}_{i}^{\prime}(w) & \hat{G}:=G\left(1-\alpha^{k}\right)^{-1} \\
w:=w-\eta \hat{v} \oslash(\sqrt{\hat{G}}+\varepsilon) &
\end{array}
$$
где $\odot$ и $\oslash-$ покоординатное умножение и деление векторов.

Калибровка $\hat{v}, \hat{G}$ увеличивает $v, G$ на первых итерациях, где $k$ - номер итерации; $\gamma=0.9, \quad \alpha=0.999, \quad \varepsilon=10^{-8}$.

**Улучшения:**
* [[Nadam]]
* [[AdaGrad]] *TODO*