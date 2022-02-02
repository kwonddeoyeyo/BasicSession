# BasicSession
기초세션 과제 repo
----
## 시각화 피드백
----
### 박지은님
#### 피드백 : 딕셔너리를 활용한 replace !! 간결하고 깔끔한 코드 아주 좋습니다. 
```python 
train['weekday'] = train['weekday'].replace({0 : 'Monday', 
                                   1 : 'Tuesday',
                                   2 : 'Wednesday',
                                   3 : 'Thursday',
                                   4 : 'Friday',
                                   5 : 'Saturday',
                                   6 : 'Sunday'})
```
----
### 전재현님
#### 피드백 : mpg데이터셋 시각화 시 sns.regplot도 사용가능합니다~
```python 
sns.regplot(data = mpg,
            x='model_year',
            y='mpg')
```
----
### 김찬영님
#### 피드백 : groupby를 잘 사용하셨지만, for문이 2번이나 있어 데이터가 컸으면 오래 걸렸을 코드네요. 하지만 센스있게 x축명 회전시켜준 것은 너무 좋습니다~!
- 현 코드
```python
index=[i for i in range(24)]
date=[]
for i in range(2):
    for j in range(12):
        date.append(f'{2011+i}-{j+1}')
plt.figure(figsize=(15,5))
plt.bar(height=train.groupby(['Year','Month'])['count'].sum(),x=index)
plt.xlabel('Year and Month')
plt.ylabel('total rent')
plt.xticks(index,date,rotation=45)
plt.show()
```

- 수정 권장 코드
```python
#create new column "Year_Month"
train['Year_Month'] = train[['Year','Month']].apply(lambda x: '-'.join(x.values.astype(str)))
```
- 이런식으로 미리 컬럼을 만들어두면, barplot그렸을 때 자동으로 합계로 그려지게 됩니다.
----

