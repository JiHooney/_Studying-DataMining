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

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/385e3d8c-d526-4257-80b3-d9b9a2601a1c/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085802Z&X-Amz-Expires=86400&X-Amz-Signature=ebbdcd077c33622184158cfb63437bed1749f76ac092380dfd36f6794e23e948&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- 다항회귀모형

```jsx
* 다항회귀모형: 종속변수와 입력변수의 관계가 선형이 아니지만 이차함수로 적합할 수 있을 경우
		사용한다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/16e99c38-063d-41a7-aefb-7f595d62a3a4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085828Z&X-Amz-Expires=86400&X-Amz-Signature=82a5d21a410a17ab2a6a8f69ba18d8346eda1564f20c8ad2807988cea3759b21&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/76cd66ec-425c-4e15-b32f-9198174033ee/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085839Z&X-Amz-Expires=86400&X-Amz-Signature=81665f3f415cc1e8edf03b837ff12de2693cdce1aaffffac3f0dbe527b635492&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **능형회귀분석(Ridge Regression, 릿지회귀분석)**

```xml
능형회귀: 일반적으로 많은 수의 변수를 가지고 선형회귀분석을 하면 Train R-squared는 좋아지지만 
	Overfitting을 발생시킵니다. 따라서 능형회귀모형은 일반적인 선형회귀분석의 독립변수의 계수를
	추정하는 과정에서 패널티 항인 람다를 추가시켜서 모형의 분산을 줄여주게 됩니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/30f8a77a-de83-4d09-87fd-d581c72dbe49/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085850Z&X-Amz-Expires=86400&X-Amz-Signature=7e42ca68b4d9d52df8dfc5a345dfd1f93f829c5e5366081fcb06645ea56019f2&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **라쏘회귀분석**( Lasso Regression )

```xml
라쏘회귀분석: 릿지회귀와 비슷하게 패널티를 주지만 절댓값이 붙은 패널티항을 주기 때문에 작은 값의
	파라미터를 0으로 만들어 해당 변수를 모델에서 삭제하고 모델을 단순하게 해주어 해석에 용이하게 
	해줍니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/dba6a1fd-68f4-40c3-b625-e1e34f137ff1/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085859Z&X-Amz-Expires=86400&X-Amz-Signature=9364b1b7ad4ae4a0bf706fb818fd604fd74f2a94154d7976283faeb95376c2f1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

## 2. 로지스틱 회귀분석

- 로직스틱 회귀

```xml
-로지스틱회귀: 기존 회귀분석의 종속변수가 연속형 범주였다면 로지스틱 회귀분석을 종속변수가 범주형
	일 때 적용하는 회귀분석 기법입니다. 변수를 선택할 때 로지스틱 회귀는 로그우도함수의 값을
	이용합니다.

-모형: P(Y = 1|x) = exp(a + bx)/(1 + exp(a + bx))

-Odds Ratio(오즈비): Odds는 비이고, Odds ratio는 비의 비율이다.
	odds의 해석은 실패에 비해 성공할 확률의 비를 의미하며, odds = p / (1-p)이다.
	이때 Odds에 log를 취한 것이 바로 로짓( log (p/(1-p)) ) 이다.

-다중 로지스틱 회귀: 독립변수가 2개 이상이고 종속변수가 범주형 자료일 때(이때 범주가 2개이다.)
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/91a53ed7-27e6-4a4b-83f2-166ee2cf0a9a/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085908Z&X-Amz-Expires=86400&X-Amz-Signature=d07655808e09a28d49c79a461fae948481961ba5d6865e2ef794b5c558ad3ba1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7c4891ea-05b1-4708-87ef-8011b2a3d8e0/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085917Z&X-Amz-Expires=86400&X-Amz-Signature=ec4e9eb76152159a3f1ff97868d275806938db4488aa311c8690d18caa33a84d&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4e6a7812-412a-4d2d-99c3-bcc36a154494/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085924Z&X-Amz-Expires=86400&X-Amz-Signature=27953ebeacc53594381dbf9575780d8c1eeb3393a312fed65fccc97c39543eac&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a2b08302-2107-445a-8f41-9fb808fdbc46/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085932Z&X-Amz-Expires=86400&X-Amz-Signature=3f906b3577be07938353c6fbe6ed8d1856813a1884828c4c278c764b24371591&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

## 4. 의사결정나무

- **의사결정나무**

```xml
* 의사결정나무: 의사결정 규칙을 나무 구조로 도표화해서 분류 및 추정을 수행하는 분석 방법입니다.
	특히 범주형과 연속형 데이터에 대한 예측이 가능합니다.

* 순수도와 불순도&불확실성: 의사결정나무는 한 번 분기할 때마다 변수 영역을 두 개로 구분하게 됩니다. 
	이때 구분하는 기준은 순수도와 불순도에 따라 분기됩니다.
	즉, 각 마디에서 분리변수와 분리 기준의 설정은 생성된 두 개의 자식마디의 순수도의 합이 가장 큰
	혹은 불순도의 합이 가장 작은 분리변수와 분리기준이 선택됩니다.

* 불순도의 측정
	* 범주형일 때
		- 카이제곱 통계량
		- 지니지수
		- 엔트로피 지수
	* 연속형일 때
		- 분산분석에 의한 F-통계량
		- 분산의 감소량

```

## 5. 신경망

- **신경망**

```xml
* 신경망: 인간의 두뇌 구조를 모방한 지도학습 방법으로서 여러 개의 뉴런들이 상호 연결하여 입력값에
	대한 최적의 출력값을 예측해주는 모형입니다.

* 용어정리
	- MLP( Multi-Layer Perceptron ): 입력층, 은닉층, 출력층으로 구성
	- SLP( Single-Layer Perceptron ): 입력층, 출력층으로만 구성
	- 입력층: 각 입력변수에 대응되는 노드로 구성. 노드의 수는 입력변수의 개수와 같음
	- 은닉층: 입력층으로부터 전달되는 변수값들의 선형결합을 비선형함수로 처리하여 출력층 또는
			다른 은닉층에 전달해준다.
	- 출력층: 목표변수에 대응되는 노드로서 분류모형에서는 그룹의 수 만큼의 출력노드가 생성됩니다.
	- 활성화 함수: 입력 신호의 총합을 출력 신호로 변환하는 함수를 일반적으로 활성화 함수라고 합니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2111a936-1048-4439-9d49-9340e39fbc32/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085942Z&X-Amz-Expires=86400&X-Amz-Signature=22026a51f4c0f7dd3c73faba64c6eaec420185032883f784c0d284223faafa39&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **다층 신경망(MLP)**

```xml
* 다층신경망: 계산층이 여러 개이며, 추가적인 중간 계산층을 은닉층이라고 부른다. 
	모든 계산층이 자신의 계산 결과를 입력에서 출력으로의 순방향으로 전달하는 구조를 
	순방향신경망이라고 한다.

* 시그모이드 함수: 신경망 안에서 데이터들을 처리할 때 계단함수(0과 1이 결과값)가 아닌 s자
	곡선 함수인 시그모이드 함수를 이용하면 더 다양한 처리가 가능해집니다.
	단극성, 양극성 두 종류가 있음
	* 단극성: 증가함수이며, 출력값이 0과 1사이의 값을 갖습니다. 로지스틱 함수와 유사합니다.
	* 양극성: 증가함수이며, -1과 1사이의 값을 갖고 f(0) = 0입니다.

* 역전파 학습 법칙
	1. 처음에 가중치는 랜덤
	2. 훈련 입력패턴을 신경망의 입력층에 전달
	3. 입력층에서 은닉층, 출력층까지 입력패턴을 전파
	4. 출력 패턴이 목표패턴과 다르면 그 오차를 계산한 후 출력층에서 입력층까지 신경망을 따라서
		거꾸로 오차가 전파
	5. 오차를 줄일 수 있도록 가중치 재조정
	6. 목표패턴 찾을 때까지 위 과정 반복

* 경사하강법( 역전파 알고리즘 )
	* 함수 최적화 문제: 어떤 목적함수가 있을 때 이 함수를 최대 혹은 최소로 하는 변수나 파라미터의
		값을 찾는 문제.
	* 그래디언트: 함수의 특정 위치에서 함수의 값이 가장 커지는 인접한 위치로의 방향을 나타냄(미분값)
	* 경사하강법: 함수의 그레디언트를 사용하여 함수의 값이 최소가 되는 위치의 파라미터를 찾는 방법입니다.
	* 역전파 알고리즘은 경사 하강법을 적용하여 오차 함수의 값이 최소가 되는 가중치를 찾는 학습 알고리즘입니다.
	* 단순히 경사하강법을 사용하면 극솟값만 찾는 경우가 있는데 이를 방지하기 위해 초기값을 여러 개
		두어서 극소값이 아닌 최소값을 찾아야 한다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/6a5d63eb-32b1-4a12-b731-1a5a7737b97c/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T085951Z&X-Amz-Expires=86400&X-Amz-Signature=a4ae6ca6c9c3f50cd86d4aa714a90a18f461752fb1eb6139c1dfada59f2e33cd&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

## 6. 연관성 분석

- **연관성분석**

```xml
* 연관성 분석: 데이터 안에 존재하는 항목들간의 연관규칙을 발견하는 기법
	이를 통해 손님의 장바구니에 들어있는 품목간의 관계를 알아본다는 의미에서 장바구니 분석이라고 함
```

- **연관성 규칙**

```xml
* 유용한 규칙: (예) 목요일 식료품 가게를 찾는 고객은 아기 기저귀와 맥주를 함께 구입하는 
	경향이 있다
* 자명한 규칙: (예) 한 회사의 전자제품을 구매하던 고객은 전자제품을 살 때 같은 회사의 제품을 
	사는 경향이 있다
* 설명이 불가능한 규칙: (예) 새로 연 건축 자재점에서는 변기덮게가 많이 팔린다
```

- **연관성분석의 측도**

```xml
* 지지도: 두 품목 A와 B의 지지도는 전체 거래항목 중 항목A와 항목B가 동시에 포함하는 거래의 비율
	지지도 = P(A ∩ B) = A와 B가 동시에 포함된 거래수 / 전체 거래수
* 신뢰도
* 향상도: 3가지 품목을 포함하는 연관성 규칙 중 가장 신뢰도가 높은 규칙은 "B와 C를 구매하면
	A도 구매한다."이며 이 연관성 규칙의 신뢰도는 신뢰도 구하는 공식에 의해 구할 수 있습니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/69e939a7-d31c-4643-891c-824ae903cb23/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T090000Z&X-Amz-Expires=86400&X-Amz-Signature=af35575d6d3d1ff35faed2a269a656ec70bb8e56c3c2573b173f73a2680bfa11&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/0735cc7e-8fc9-4698-b630-3cc2bd246984/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T090008Z&X-Amz-Expires=86400&X-Amz-Signature=84904b088e3031f4717b3d1551dc122ddedbe20679a26b4e48237857a36f670f&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

## 7. 군집분석

- **군집분석**

```xml
모집단 또는 범주에 대한 사전 정보가 없는 경우 주어진 관측값들 사이의 거리 또는 유사성을 이용하여
전체를 몇 개의 집단으로 그룹화하여 각 집단의 성격을 파악함으로써 데이터 전체의 구조에 대한
이해를 돕고자 하는 분석법
* 군집화
	* 군집화의 기준: 동일한 군집에 속하는 개체는 여러 속성이 비슷하고, 서로 다른 군집에 속한
		관찰치는 그렇지 않도록 구성
```

- **거리**

```xml
군집분석에서는 관측값들이 서로 얼마나 유사한 지 또는 유사하지 않은 지를 측정할 수 있는 측도가 필요
보통 유사성보다는 비유사성을 기준으로 하며 거리를 사용합니다.
```

- **계층적 군집분석**

```xml
가까운 관측값들끼리 묶는 병합방법과 먼 관측값들을 나누어가는 분할 방법이 있습니다. 
주로 병합 방법이 사용됩니다.

* 병합방법
	1. 처음에 n개의 자료를 각각 하나의 군집으로 취급
	2. n개의 군집 중 가장 거리가 가까운 두 개의 군집을 병합하여 n-1개의 군집 형성
	3. n-1개의 군집 중 가장 가까운 두 군집을 병합하여 군집을 n-2개로 줄임
	4. 이를 반복하여 계속하여 군집의 수를 줄임
	5. 이 과정은 시작부분에는 군집의 크기는 작고 동질적이며, 
		끝부분에서는 군집의 크기는 커지고 이질적이 됩니다.
	군집들간의 거리를 측정하는 방법은 여러가지가 있습니다.( 최단거리, 최장거리, 평균거리 등등 )

* 최단연결법: 두 군집 사이의 거리를 각 군집에서 하나씩 관측값을 뽑았을 때 나타날 수 있는
	거리의 최소값으로 측정
* 최장연결법: 두 군집 사이의 거리를 각 군집에서 하나씩 관측값을 뽑았을 때 나타날 수 있는
	거리의 최대값으로 측정
```

- **비계층적 군집분석**

```xml
* K-평균 군집: 사전에 결정된 군집수 K에 기초하여 전체 데이터를 상대적으로 유사한 K개의 군집으로
	구분합니다. 관측값간의 평균거리와 군집간의 평균거리를 비교함으로써 수행합니다.
	가장 좋은 방법은 자료의 시각화를 통한 최적 군집수 K의 결정인데, 자료의 시각화를 위해서는
	차원의 축소가 필수적이고, 이를 위하여 주성분 분석방법을 사용합니다.

* 단점
	- 군집이 겹치는 경우에 좋지 않습니다.
	- 이상치에 민감합니다.
	- 각 관측값이 할당된 군집에 속하지 않을 경우 불확실성에 대한 측정치가 없습니다.
```

- **가우스 혼합모형**

```xml
주어진 군집수 K에 대하여, 각 군집의 관측치의 분포가 미지의 평균과 분산을 따르는 정규분포 가정합니다.
자료를 가장 잘 분리할 수 있는 최적의 평균과 분산을 추정과 우도함수의 최대화의 두 단계를 반복적으로
수행함으로써 구합니다.
```

## 8. 기타 지도학습방법

- **K-근방 분류**

```xml
시험자료점과 가까운 k개의 훈련자료점의 y값들을 비교하여 가장 많은 class로 예측하는 방법입니다.
```

- **서포트 벡터 기계**

```xml
결정 경계, 즉 분류를 위한 기준 선을 정의하는 모델입니다. 그래서 분류되지 않은 새로운 점이 
나타나면 경계의 어느 쪽에 속하는 지를 확인해서 분류 과제를 수행할 수 있게 합니다.
따라서 이 결정 경계를 어떻게 정의하고 계산하는 지가 가장 중요합니다.
결정 경계는 데이터 군으로부터 최대한 멀리 떨어져 있을 때 가장 성능이 좋습니다.

이때 마진이란 결정 경계와 서포트 벡터 사이의 거리를 의미합니다.
따라서 최적의 결정 경계는 마진을 최대화한 것입니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/54baa5dc-4aa4-4efe-82e5-84890bb949d8/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T090016Z&X-Amz-Expires=86400&X-Amz-Signature=a163ae44d8108dd4d4082ef390f1bf840df33543430c5c66019241a0643fd102&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **앙상블 기법**

```xml
여러 분류 모형( 회귀분석, 의사결정나무, 신경망, 로지스틱 회귀 등등 )에서 얻은 결과들에
다수결 원칙을 적용하여 최종 예측치를 결정하는 기법입니다. 하나의 데이터가 주어지면 표본추출을
통해 다수의 훈련데이터를 생성하고 각 훈련데이터에 동일한 알고리즘으로 모형을 생성한 후 
그 결과를 결합하여 최종 예측을 합니다.

* 배깅(Bagging, Bootstrap Aggregation): 배깅은 샘플을 여러 번 뽑아(Bootstrap) 각 모델을 
	학습시켜 결과물을 집계하는 방법입니다.
	우선 주어진 데이터를 부트스트랩하고 만들어진 데이터로 모델을 학습시킵니다. 
	그리고 학습된 모델의 결과를 집계하여 다수결의 원리에 따라 최종 결과 값을 구합니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/f14b270f-1432-4c3d-93b3-29df0722ae2b/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T090026Z&X-Amz-Expires=86400&X-Amz-Signature=3e002a12f19e964f8f6ea9192dfa94ffa65501ecad4ff6f2e11fdb0d66235906&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **부스팅**

```xml
부스팅은 가중치를 활용하여 약 분류기를 강 분류기로 만드는 방법입니다. 
배깅의 경우 의사결정나무1과 의사결정나무2가 서로 독립적인 결과를 예측하지만 부스팅은
처음 모델이 예측한 결과를 두 번째 모델이 첫 번째 모델의 결과에 가중치를 부여해서 예측을 합니다.
이렇게 모델의 결과는 가중치를 부여받으면서 다음 모델에 영향을 줍니다.
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a35f2049-e2b8-4f4f-a3f2-7a85af6d79f8/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T090037Z&X-Amz-Expires=86400&X-Amz-Signature=c10a0c95d1766a0ee21dffa50c958d19bf8e7beb53a6e389cffe9842e5351199&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **배깅과 부스팅의 차이**

```xml
배깅은 병렬로 학습하는 반면, 부스팅은 순차적으로 학습합니다. 
부스팅은 배깅에 비해 에러가 더 적습니다. 즉 성능이 좋습니다. 하지만 속도가 느리고 오버피팅이
될 가능성이 높습니다. 
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/87d78521-6c1c-4703-92d7-87ac279aea03/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210907%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210907T090046Z&X-Amz-Expires=86400&X-Amz-Signature=21ed7aeae35f12ce6d7f6bad00bdaffe6100ffe0491920f74fa74e59d2508ba3&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **범핑(Bumping)**

```xml
부트스트랩 표본을 추출하여 모형을 적합하는 방법으로 배깅에서는 각 모형을 결합하여 예측하지만
범핑의 경우는 여러 모형 중 가장 예측력이 좋은 모형 하나만을 선택하고 이 모형을 이용하여
최종 예측을 합니다.
```
