## RMSProp
**RMSProp (Running Mean Square)** -  ускоряет обучение по весам, которые пока мало изменялись. В определении "пока" используется [[Экспоненицальное сглаживание|экспоненциальное сглаживание]].

$$
\begin{aligned}
G &:=\alpha G+(1-\alpha) \mathscr{L}_{i}^{\prime}(w) \odot \mathscr{L}_{i}^{\prime}(w) \\
w &:=w-\eta \mathscr{L}_{i}^{\prime}(w) \oslash(\sqrt{G}+\varepsilon)
\end{aligned}
$$
где $\odot$ и $\oslash-$ покоординатное умножение и деление векторов.

**Улучшения:**
* [[AdaDelta]]
* [[Adam]]