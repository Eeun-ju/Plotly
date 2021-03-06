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
## [Pie Chart](PieChart.ipynb)
data : https://www.kaggle.com/sootersaalu/amazon-top-50-bestselling-books-2009-2019
```{.python}
  fig = px.pie(data,names = 'Genre',hover_data = ['User Rating'],title='Genre Pie Chart')

  fig = px.sunburst(data,path=['Genre','Year', ],values='Reviews') #path로 다중 속성 입력, 원 그래프 크기 values 속성으로 저장, reviews가 얼마나 되는지 확인하기
```
## [지도 시각화](공간정보지도화.ipynb)
data : https://blog.daum.net/geoscience/1420 AML_HOSP.xlsx
```{.python}
  fig = px.scatter_mapbox(data=데이터, lat=위도, lon=경도)
  fig.update_layout(mapbox_style='open-street-map")
  fig.show()
```
참고 링크 : https://github.com/osgeokr/dump/blob/master/1420_Pandas%EC%99%80_Plotly%EB%A5%BC_%EC%9D%B4%EC%9A%A9%ED%95%9C_%EA%B3%B5%EA%B0%84%EC%A0%95%EB%B3%B4_%EC%A7%80%EB%8F%84%ED%99%94.ipynb

## [Gantt Chart](GanttChart.ipynb)
간트차트(Gantt Chart)는 프로젝트 일정관리를 위한 bar 형태의 도구로 전체 일정을 한눈에 볼 수 있다.
```{.python}
  fig = px.timeline(data,x_start=시작날짜,x_end=끝날짜,y=일정,color='Task')
  fig.show()
  #figure_factory 사용
  fig = ff.create_gantt(data, colors=컬러설정컬럼, index_col=보여주고싶은값, show_colorbar=True) # index_col : 바로 보이는 값으로 설정
fig.show()
```

# DASH(대시)

## Dash란?
Dash는 웹 분석 애플리케이션을 구축하기 위한 python framework으로 Python에서 데이터로 작업하는 사람들이 많이 사용한다. <br> Plotly와 Dash를 사용해보고 대시 보드를 구축해보자.

## Jypyter-Dash란?
Jupyter 환경내에서 대화식으로 Plotly Dash 앱을 쉽게 개발할 수 있는 라이브러리. Colab에서도 지원하기 때문에 쉽게 실습할 수 있다.

### Dash 패키지 설치

```{.python}
  pip install dash
  #pip install --user dash
```
### Jupyter-Dash 패키지 설치

```{.python}
  pip install jupyter-dash
```
### Jupyter-Dash 디스플레이 모드 
+ 외부 디스플레이 모드 <br><br> URL 클릭으로 새로운 브라우저 탭에서 애플리케이션을 여는 방법으로 애플리케이션이 정확히 어떻게 보이는지 보고 싶을 때 사용한다.
```{.python}
  app.run_server(mode='external')
```
+ 내부 디스플레이 모드 <br><br> 노트북에 애플리케이션을 인라인으로 표시한다. 소규모 애플리케이션에서 빠르게 작용한다.
```{.python}
  app.run_server(mode='inline')
```
+ JupyterLab 디스플레이 모드 <br><br> JupyterLab의 별도 탭에서 애플리케이션이 표시된다. 코드와 나란히 볼 수 있으므로 애플리케이션을 빠르게 반복하는 데 적합하다.
```{.python}
  app.run_server(mode='jupyterlab')
```
### [Jupyter dash inline example](DASH_tutorial.ipynb)
<br>
<center><img src="https://user-images.githubusercontent.com/76032774/127945812-c487440d-08a6-47a2-b7f6-93d040ab587d.png" width="900" height="500"></center>


