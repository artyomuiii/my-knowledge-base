*Svetlana Illarionova, ...*

#### I. INTRODUCTION
Мультиспектральные спутниковые снимки среднего разрешения (Landsat или Sentinel) - в свободном доступе.
(???Есть ещё гиперспектр какой-то)
??? **LIDAR**

"???Спутниковые снимки с очень высоким пространственным разрешением, такие как
спутниковые данные WorldView (2 m)."

???QuickBird images (2.44 m)

Цели:
1. Улучшить многоклассовую сегментацию изображений лесных видов
путем разделения задачи на иерархию задач бинарной сегментации.
2. Использование карт высоты лесов в качестве доп. данных
3. Создание размеченного датасета

Были использованы и сравнены 6 архитектур NN. Для каждой задачи классификации возможно найти лучшую архитектуру. Также протестировано на *Sentinel*.

#### II. DATASET
###### A. Study Area
Ленинградская область
S ~ 20 тыс. га

###### B. Reference Data
Исследуемая территория была разделена на небольшие регионы, описывающиеся:
* Состав леса (по нему определяется доминирующий вид - самый представленный) - были исключены регионы со смешанными лесами, когда два и более видов деревьев наиболее представлены. Всего 4 вида - ели (*spruce*), осины (*aspen*), берёзы (*birch*) и сосны (*pine*). Остальные представлены в меньших объёмах.
* Средняя высота деревьев
* Средний возраст деревьев

Виды деревьев - не с биологической точки зрения, а с точки зрения качетсва древисины. Т.о., не делаются внутриродовые различия внутри одного рода.

![[Pasted image 20231026145558.png]]
![[Pasted image 20231026145900.png]]

###### C. Satellite Data
Все снимки в период высокой вегитации - с мая по август.
???  "WorldView 2 and 3 multispectral imagery with eight spectral
bands was downloaded from GBDX [31]. The spatial resolution
was about 2 m per pixel. Sentinel imagery with 13 spectral
bands and a spatial resolution of about 10 m per pixel was
downloaded from SentinelHub [32]. All images were from the
high vegetation period from May to August. Image acquisition
dates and catalogue IDs are presented in Tables II and III.
Dataset consists of georeferenced satellite images in the for-
mat of 8-b TIFF files and forestry inventory data converted into
raster per pixel masks for each class."

Специальная сетка, сегментирующая лес, обрезает безлесые участки из обучающих и валидационных данных, ибо имеет место несоответствие во времени (какие-то леса уже вырублены физически, а информация о них до сих пор хранится). Тестовый датасет почищен вручную.

#### III. METHODS
###### A. Problem Definition

Решается задача сегментации - присвоить каждому пикселю определённый класс.

*Доп. проблемы:* данные могут быть противоречивыми - в пределах элементарных регионов могут быть видимые вкрапления недоминирующего вида деревьев
###### B. Neural Networks for Image Segmentation

* FCNN (полносвёрточная NN) - **U-Net**
* **FPN (Feature Pyramid Network)** - больше подходит для многоклассовой сегментации *(архитектуры выше работают по принципу кодер-декодер со skip connections => на самом деле можем использовать произвольный кодировщик)*
* **ResNet** (-34)
* **Inception-ResNet-v2** (-34)
* **EfficientNet** (B3)

Реализация архитектур основана на:
"P. Yakubovskiy, “Segmentation models,” 2019. [Online]. Available: https://github.com/qubvel/segmentation_models"
###### C. Image Preprocessing

Sentinel
![[Pasted image 20231026154522.png]]
![[Pasted image 20231026154533.png]]
TODO

###### D. Dataset Augmentation
С вер-тью 50%:
* поворот на 90°
* горизонтальное или вертикальное отражение
* увеличение или уменьшение масштаба в пределах 20%
###### E. Oversampling
###### F. Problem Decomposition
###### G. Height Data
#### IV. EXPERIMENTS
###### A. Training
###### B. Medium Resolution Data
###### C. Evaluation
#### V. RESULTS AND D ISCUSSION
###### A. Hierarchical Decomposition
###### B. Supplementary Height Data
###### C. Architecture Selection
###### D. Augmentation and Oversampling
#### VI. CONCLUSION
#### REFERENCES
