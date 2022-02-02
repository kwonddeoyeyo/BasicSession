# Visualization Feedback

### 공통
1.	한 번에 여러 plotting을 할 때 아래 코드를 참고해주세요! Ex) 2개 위아래로
``` Python
fig,ax = plt.subplots(2,1, figsize = (15,10))
plt.subplot(2,1,1)
sns.barplot(data=, x=, y=)
plt.subplot(2,1,2)
sns.barplot(data=, x=, y=)
plt.show()
```


### 김채은
1.	한글폰트 다운로드
Local에서 가져올 때 file directory에 오류가 있는 것 같습니다. 채은님 코드에서 font_name이 프린트가 안되서 모르겠지만, 나눔 폰트는 스트링으로 “NanumBarunGothic”입니다.
``` Python
FONT_PATH = '/usr/share/fonts/truetype/nanum/NanumGothicEco.ttf'
plt.rc('font', family='NanumBarunGothic') 
```

2.	시각화 1번 – 따로 yearNum을 구하시지 않아도 간단하게 시각화할 수 있습니다. 채은님 변수로 코드를 작성해봤습니다.
``` Python
sns.barplot(data=train, x="year", y="count")
sns.barplot(data=train, x="month", y="count")
```
바차트가 현재 하신 것과 다르게 나올겁니다. 인사이트도 이에 따라 다시 도출하셔야 할 것 같습니다.

3.	시각화 2번 – 우선 숫자로 되어 있는 연/월 컬럼을 str으로 바꾸셔야 합니다. 그리고 연컬럼과 월컬럼을 간단한 concatenate으로 합칠 수 있습니다.
``` Python
train["year_month"] = train["year"] + "-" + train["month"]
```
그리고 시각화는 countplot이 아닌 barplot을 사용해주세요. (이게 더 잘 보입니다.)
``` Python
sns.barplot(data=train, x="year_month", y="count")
```

4.	시각화 3번 – 여기서 시각화는 모두 count를 y로 두시면 됩니다. 따로 series나 df를 추출하시지 않아도 됩니다. 그리고 bar plotting이 아닌 pointplot을 사용하시면 좋습니다. 채은님 변수 사용해서 코드 작성해드립니다. 한 번 적용해보세요!
``` Python
sns.pointplot(data=train, x="hour", y="count")
sns.pointplot(data=train, x="hour", y="count", hue="workingday")
sns.pointplot(data=train, x="hour", y="count", hue="weekday")
```

5.  고생하셨습니다!


### 전혜령
1.	시각화 부분 인사이트를 도출하지 않으셨습니다.

2.	3번은 전부 count column을 활용하시면 쉽게 시각화 가능하십니다.
3번 1) – 시간별 자전거 대여량은 총 시간이 아닌 각 시간 별로 발생한 횟수에 대한 차트를 그리시면 됩니다. bar보다는 pointplot를 추천합니다. 아래 코드는 혜령님이 쓰신 변수를 적용한 코드입니다.
``` Python
sns.pointplot(data=df, x="hour", y="count")
```
3번 2) – hue를 workingday로 사용하시면 됩니다. 근무일/휴일을 나누는 변수.
``` Python
sns.pointplot(data= df, x="hour", y="count", hue="workingday")
```
3번 3) – 관련 시각화 자료가 안 보입니다. Hue를 혜령님 변수로 dayofweek로 하시면 됩니다.

3.	고생하셨습니다!


### 김형민
1.	완벽하게 해내셔서 따로 수정 관련 피드백은 없습니다. 고생하셨습니다!

