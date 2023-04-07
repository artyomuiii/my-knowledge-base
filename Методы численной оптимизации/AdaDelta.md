## AdaDelta
**AdaDelta (Adaptive Learning Rate)** - [[RMSProp]] + идея использования значения градиента для шага: да, мы могли уже долго двигаться вдоль некоторой координаты, но вдруг у нас случай очень большого несоответствия масштабов, поэтому необходимо использовать информацию  не об абсолютном накоплении, а об относительном.

$$
\begin{aligned}
G &:=G+(1-\alpha) \mathscr{L}_{i}^{\prime}(w) \odot \mathscr{L}_{i}^{\prime}(w) \\
\delta &:=\mathscr{L}_{i}^{\prime}(w) \odot \frac{\sqrt{\Delta}+\varepsilon}{\sqrt{G}+\varepsilon} \\
\Delta &:=\alpha \Delta+(1-\alpha) \delta \odot \delta \\
w &:=w-\eta \delta
\end{aligned}
$$

**Преимущества:**
* Параметр $\eta$ можно брать равным $1$.