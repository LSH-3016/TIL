#Java Collection이란?
### ▶ `데이터의 집합, 그룹`
![](./CS_IMG/Java_Collection.png)

## Collection을 사용하는 이유
* ### `일관된 API`
    #### Collection의 일괄된 API를 사용하여 Collection 밑에 있는 모든 클래스(ArrayList,Vector,LinkedList 등) Collection에서 상속받아 통일된 메서드를 사용
* ### `프로그래밍 노력 감소`
    #### 객체 지향 프로그래밍의 추상화의 기본 개념이 성공적으로 구현
* ### `프로그램 속도 및 품질 향상`
    #### Collection API를 사용하여 더 쉬운 구현과 성능 향상

<hr/>

## List Interface
#### 순서가 있는 데이터의 집합으로 데이터의 중복을 허용
* ### `ArrayList`
    #### 단방향 포인터 구조로 각 데이터에 대한 인덱스를 가지고 있어 조회 기능에 성능이 뛰어남
    ###### 동적 배열을 제공하며, 표준 배열보다 느릴 수 있지만 배열에서 많은 움직임이 필요한 프로그램에서 유용
    ###### 컬렉션에서 개체를 추가, 삭제하면 ArrayList의 크기가 자동으로 조정
  <pre><code>ArrayList<'Integer'> a = new ArrayList<'Integer>();</code></pre>
* ### `LinkedList`
    #### 양방향 포인터 구조로 데이터 삽입, 삭제가 빈번할 경우 데이터의 위치정보만 수정하면 되기에 유용
    ###### 스택,큐,양방향 큐 등을 만들기 위한 용도로 쓰임
    ###### 요소가 연속 된 위치에 저장되지 않고 모든 요소가 데이터 부분과 주소 부분이 있는 별도의 객체에 저장
    ###### 포인터와 주소를 사용해서 데이터를 가져옴
  <pre><code>LinkedList<'Integer'> a = new LinkedList<'Integer'>();</code></pre>
* ### `Vecotr`
    #### 과거에 대용량 처리를 위해 사용했으며, 내부에서 자동으로 동기화처리가 일어나 비교적 성능이 좋지 않고 무거워 잘 쓰이지 않음
    ###### Vector는 동기화 되고, ArrayList는 동기화 되지 않음
    ###### 동적 배열을 제공하고, 표준 배열보다 느리지만 많은 움직임이 필요한 프로그램에서 유용
  <pre><code>Vector<'Integer'> a = new Vector<'Integer'>();</code></pre>
* ### `stack`
    #### 스택 클래스 모델 및 스택 데이터 구조를 구현할 때 주로 사용
    ###### 후입 선출을 기본 원칙으로 함
  <pre><code>Stack<'String'> a = new Stack<'String'>();</code></pre>

<hr/>

## Set Interface
#### 순서를 유지하지 않는 데이터의 집합으로 데이터의 중복을 허용하지 않음
* ### `HashSet`
    #### 입력되는 데이터가 동일한 순서로 삽입되는 것을 보장하지 않음
    ###### NULL 요소 삽입을 허용
    ###### 가장빠른 임의 접근 속도, 순서 예측 불가
  <pre><code>HashSet<'String'> a = new HashSet<'String'>();</code></pre>
* ### `TreeSet`
    #### Tree를 사용하여 저장
    ###### 데이터의 순서는 오름차순으로 유지
    ###### 정렬방법을 지정할 수 있음
  <pre><code>TreeSet<'String'> a = new TreeSet<'String'>();</code></pre>

<hr/>

## Map Interface
#### 키(key), 값(Value)의 쌍으로 이루어진 데이터의 집합으로 순서가 유지되지 않음
* ### `HashMap`
    #### 중복과 순서가 허용되지 않으며 null값이 올 수 있음
  <pre><code>HashMap<'Integer','String'> a = new HashMap<'Integer','String'>();</code></pre>