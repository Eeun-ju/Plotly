# Plotly(플로틀리)

## Plotly란?
파이썬 오픈소스 그래프 라이브러리로 다양한 시각화 기능을 제공한다. Plotly의 시각화 기능을 하나씩 확인하고 실습해보자.

### Plotly 패키지 설치

```{.python}
  pip install plotly
  pip install plotly --upgrade
```
### Cufflinks 패키지 설치
Cufflinks는 Plotly를 pandas에서 보다 유연하게 시각화 할 수 있는 라이브러리이다.
```{.python}
  pip install cufflinks
```
## [Line Charts, Bar Charts](BarChart&LineChart.ipynb)

```{.python}
  pandas_data.iplot(kind='bar')
  pandas_data.iplot(kind='line')
```
## [Scatter plot](Scatter.ipynb)

```{.python}
  fig = ex.scatter(df,x='x축',y= 'y축',color='색상',
                 size='크기변화 변수', 
                 hover_data=참고데이터,
                 title = '그래프 이름')
  fig.show()

```

## 지도 시각화
참고 링크 : https://blog.daum.net/geoscience/1420


