# 데이터 마이닝 부수기

## 1. 데이터 마이닝의 기본 개념

- **데이터 마이닝이란?**

```xml
대용량의 데이터로부터 데이터 내의 존재하는 관계, 패턴, 규칙 등을 탐색하고 모형화해서 
새로운 지식을 추출하는 일련의 과정들
```

- **지도학습과 비지도학습**

```xml
* 지도학습: 독립 및 종속변수를 이용해서 독립변수에 따른 종속변수의 값을 예측하는 모형을 개발
-회귀: 연속형 종속변수
-분류: 범주형 종속변수
-기법: 회귀분석, 로지스틱 회귀분석, 의사결정나무, 신경망 등

* 비지도학습: 종속변수가 없고 독립변수들의 관계를 탐색적으로 분석하여 의미있는 값을 추출
-기법: 군집분석, 연관성분석, 주성분/인자분석
```

- **모형의 평가**

```xml
* 과적합: 매우 복잡한 모형을 사용하여 현재 주어진 데이터에 대해서는 학습오차는 굉장히 작지만 
예측오차는 큰 모형을 의미합니다. 따라서 지도학습 과정에서 학습오차를 너무 작게 하는 것은 좋지 
않은 것으로 알고 있습니다.

* ROC 곡선: 구축한 모형의 성능을 민감도와 특이도를 이용하여 판단
ROC곡선의 면적은 AUC(Area Under the Curve)라고 하고 이 값이 큰 모형을 좋은 모형이라고 합니다.
이 AUC는 대체로 0.5와 1 사이의 값이됩니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/242115f3-17ee-4be7-a73e-6b2f1080217c/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210906%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210906T035230Z&X-Amz-Expires=86400&X-Amz-Signature=c98e6c0a7c6fa9df7eea2d33fd09529a4a25c676519033c73326c3f24ce56761&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

## 2. 선형회귀모형

- **단순회귀모형**

```xml
* 모형: y = a + bx + c (c는 오차항, 평균0, 분산 a^2)
선형회귀모형: 독립변수와 종속변수의 관계가 선형인 방정식을 가진다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/109c3390-52e7-4d66-a24a-9d8bd24f3330/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210906%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210906T035243Z&X-Amz-Expires=86400&X-Amz-Signature=d75830ce82d718085239120c9839dce75e0340b663264de94207a2ffc7006866&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/8156bfc7-d7d2-4aaf-8b0f-cfcd4f009adb/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210906%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210906T035253Z&X-Amz-Expires=86400&X-Amz-Signature=f1690cf2d3bfd7a2df968a46e66e0a594b31af2292929645d99a466773df7dae&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

```xml
* 선형회귀모형에 사용되는 가정
-선형성: 독립변수와 종속변수 간의 관계가 선형적
-등분산성: 오차의 분산이 독립변수와 무관하게 일정
-정규성: 오차의 분포가 정규분포

* 가정들의 검증 방법
-선형성: 단순선형회귀모형에서는 독립, 종속변수를 산점도로 이용해서 확인하고
		다중회귀모형에서는 잔차와 종속변수와의 산점도를 이용합니다.
```

- **다중선형회귀**

```xml
다중선형회귀: 독립변수가 2개 이상인 선형회귀 모형입니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/f6a1c40f-e753-44a5-8d09-f44913e1fd08/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210906%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210906T035303Z&X-Amz-Expires=86400&X-Amz-Signature=0b763afac2d340b9b92bbf4e09d111097f2e60ee01449d6fbf377a59379971d8&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/872666ff-54dc-4b7a-b9a0-ba1a543625e2/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210906%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210906T035312Z&X-Amz-Expires=86400&X-Amz-Signature=6ce373329f8cc7d14596e278f915a4bdef791f0fd590eeffec6b656e52abed0b&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)