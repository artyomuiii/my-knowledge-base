# Полезные приёмы

Можно немного залезть во внутренности **Jupyter**, чтобы отобразить сразу несколько таблиц:
```
from IPython.display import display
display(data3.sample(3)), display(data3.sample(3))
```
---
Если хочется отобразить все строки таблицы, то можно сделать так:
```
pd.options.display.max_rows = 999
```
---
Переводят в числовой тип обычно так:
```
data3['Рейтинг'] = data3['Рейтинг'].apply(lambda x: float(str(x).replace(',', '.')))
```
---
Для создания перцентилей можно поступить так:
```
data3['percentile'] = data3['Рейтинг'].rank(pct=True)
```
---
Вот почему `.count()` в `groupby()` может выдавать разные значения для разных столбцов:

![[Pasted image 20230708194454.png]]

---
