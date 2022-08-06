# 시간복잡도 (Time Complexity)
#### ▶ 입력값의 변화에 따라 연산을 실행할 때, 연산 횟수에 비해 시간이 얼만큼 걸리는가를 정의한 것
###### 효율적인 알고리즘 : 입력값이 커짐에 따라 증가하는 시간의 비율을 최소화한 알고리즘

## 시간복잡도 표현 방법
* #### 최선의 경우 (Best Case) → 빅 오메가 표기법 사용 (Big-Ω Notation)
* #### 평균의 경우 (Average Case) → 빅 세타 표기법 (Big-θ Notation)
* #### 최악의 경우 (Worst Case) → 빅 오 표기법 사용 (Big-O Notation)
#### 프로그램 실행되는 과정에서 소요되는 `최악의 시간까지 고려`하기 위해 `빅 오 표기법` 사용
###### 프로그램 설계시 이 정도 시간까지 걸릴 수 있다를 고려해야하기 때문

## O(1) → 일정한 복잡도(Constant Complexity)
![](../CS_IMG/Time_Complexity_O(1).webp)
### 입력 값이 증가하더라도 시간이 늘어나지 않음
### ▶ 즉, 입력 값의 크기와 관계없이 즉시 출력 값을 얻어낼 수 있음
### 데이터가 증가하여도 성능에 영향을 거의 미치지 않음

## O(n) → 선형 복잡도(Linear Complexity)
![](../CS_IMG/Time_Complexity_O(n).webp)
### 입력 값이 증가하면 같은 비율로 시간이 증가함

## O(log n) → 로그 복잡도(Logarithmic Complexity)
![](../CS_IMG/Time_Complexity_O(log%20n).webp)
### O(1) 다음으로 빠른 시간복잡도
### 예시) BST
### ▶ 원하는 값을 탐색할 때, 노드를 이동할 때마다 경우의 수가 절반으로 줄어듬

## O(n^2) → 2차 복잡도(Quadratic Complexity)
![](../CS_IMG/Time_Complexity_O(n2).webp)
### 입력 값이 증가함에 따라 시간이 n의 제곱수의 비율로 증가함


## O(2^n) → 기하급수적 복잡도(Exponential Complexity)
### 빅 오 표기법 중 가장 느린 시간 복잡도
### 예시) 피보나치 수열


<hr/>

# 공간복잡도 (Space Complexity)
#### ▶ 작성한 프로그램이 얼마나 많은 공간(메모리)을 차지하는지 분석하는 방법
#### `고정 공간` : 입력과 출력의 횟수나 크기와 관계없는 요구 (코드 저장 공간, 단순 변수, 고정 크기의 구조, 상수)
#### `가변 공간` : 동적으로 필요한 공간

### ※ 배열 크기, 동적 할당, 재귀 함수 등이 공간 복잡도에 영향을 끼침

<hr/>

참고자료
* [HANAMON](https://hanamon.kr/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-time-complexity-%EC%8B%9C%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84/)
* [shitai.koto](https://velog.io/@shitaikoto/Algorithm-Time-complexity)
* [ai_researcher.log](https://velog.io/@cha-suyeon/Algorithm-%EC%8B%9C%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84-%EA%B3%B5%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84)
* [코딩 팩토리](https://coding-factory.tistory.com/609)