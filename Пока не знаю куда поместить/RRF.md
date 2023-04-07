## Random Fourier Features
**Random Fourier Features (Random Kitchen Sinks, RRF)**  - метод аппроксимации ядер (любых).

Будем аппроксимировать гауссово ядро вида:
$$
K(\mathbf{x}, \mathbf{y})=e^{-\|\mathbf{x}-\mathbf{y}\|^{2} / 2 \sigma^{2}}
$$
Матрица линейного преобразования RRF может быть записана в виде:
$$
\mathbf{W}_{\mathrm{RFF}}=\frac{1}{\sigma} \mathbf{G}
$$
Где $\mathbf{G} \in \mathbb{R}^{d \times d}$ - случайная гауссова матрица, каждая строка которой независимо сэмплируется из стандартного нормального распределения. Нормы строк матрицы из $\chi$-распределения.

**Улучшения:** 
* [[ORF]], [[SORF]];
* [[PCA]].