# 220406 CSS 속성


## 배치
- `position`  
  요소의 위치 지정 기준  
  static | relative | absolute | fixed | sticky
  - `static`  
    없음
  - `relative`  
    요소 자신을 기준  
    원래 자기가 배치되어 할 위치 기준이며 원래 배치되어 할 공간은 그대로 유지
  - `absolute`  
    위치 상 부모 요소를 기준
    상위 요소를 따라가면서 position(기준-static 제외) 이 지정된 가장 가까운 요소를 기준  
    - 보통 부모요소에 `position` 지정해줘야 의도대로
  - `fixed`  
    뷰포트(브라우저)를 기준  
    화면이 스크롤되거나 해도 화면 내에 고정됨
  - `sticky`  
    스크롤 영역 기준
  
- `absolute, fixed` 는 display 가 block 으로 바뀜

- `top, bottom, left, right`  
  요소의 각 방향 별 거리 지정  
  auto | 단위  
  - auto 는 보통 원래 자기가 있어야 할 위치  

### 요소 쌓임 순서(Stack order)
어떤 요소가 사용자와 더 가깝게 있는지(위에 쌓이는지 ) 결정
1. 요소에 position 속성의 값이 있는 경우 위에 쌓임(static X)
2. 1번 조건이 같은 경우, z-index 속성의 숫자값이 높을 수록
3. 1번과 2번 조건까지 같은 경우, HTML의 다음 구조일 수록 위에 쌓임

- `z-index` 
  요소의 쌓임 정도를 지정
  auto(부모 요소와 동일) | 숫자


## 플렉스(정렬)
`display: flex`  
`display: inline-flex`  인라인 요소 같이  
Flex Container의 화면 출력(보여짐) 특성  
1차원 정렬  
display: flex 를 선언한 요소는 Flex Container, 자식들은 Flex Items  

```
|       ^                                            |
|       |               <-- 주 축, Main-axis  ->      |
|  교차축, Cross-axis                                 |
(시작점)                                             (끝점)
```

### Flex Container
- `flex-direction`  
  주 축 설정  
  row(행-좌우) | row-revers(행-우좌) | column(열-위아래) | column-reverse(열-아래위)
- `flex-wrap`  
  Flex Items 묶음(줄 바꿈) 여부
  nowrap | wrap | wrap-revers
- `justify-content`  
  주 축의 정렬 방법  
  flex-start | flex-end | center | space-between(Item 사이 균등) | space-around(Item의 외부 여백 균등)
- `align-content`  
  교차 축의 <u>여러 줄</u> 정렬 방법
  stretch | flex-start | flex-end | center | space-between(Item 사이 균등) | space-around(Item의 외부 여백 균등)
- `align-items`  
  교차 축의 <u>한 줄</u> 정렬 방법
  stretch | flex-start | flex-end | center | baseline
- `flow-flow`  

### Flex Items
- `order`  
  Flex Item 순서
  0 | 숫자
- `flex-grow`  
  Flex Item의 증가 너비 비율
  Flex Container 주축 너비가 Item들 전체 너비보다 커졌을 때 나머지 부분을 차지하는 비율
- `flex-shrink`  
  0 | 숫자  
  Flex Item의 감소 너비 비율
  Flex Container 주축 너비가 Item들 전체 너비보다 작아졌 때 줄어든 부분만큼 줄어드는 비율
  1 | 숫자  
- `flex-basis`  
  Flex Item 의 공간 배분 전 <u>기본</u> 너비
  auto(Content 크기) | 숫자
- `flex`  
  (flex-grow), (flex-shrink), flex-basis
- `align-self`  

- Item들이 Content 크기 상관없이 비율대로 차지하기  
  ```css
  flex-grow: 비율;
  flex-basis: 0;
  ```

## 전환
- `transition`  
  요소의 전환(시작과 끝) 효과를 지정하는 단축 속성  
  (property) (duration-필수) (timing-function) (delay), ...
- `transition-property`  
  전환 효과를 사용할 속성 이름을 지정  
  all | 속성이름(,)
- `transition-duration`  
  전환 효과의 지속 시간
  0s | 시간(s)
- `transition-timing-function`
  전환 효과의 타이밍(Easing) 함수를 지정
  ease(느-빠-느) | linear(일정) | ease-in(느-빠) - ease-out(빠-느) | ease-in-out(느-빠-느) | cubic-bezier(n,n,n,n) | steps(n)  
  [Easing Function CheatSheet](https://easings.net/ko)  
  [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function)  
- `transition-delay`  
  전환 효과가 몇 초뒤에 시작할지 대기시간 지정  
  0s | 시간(s)

## 변환
- `transform`  
  요소의 변환 효과  
  변환함수1 변환함수2 ...  
  원근법 이동 크기 회전 기울임  
- 2D 변환
  - `translate(x, y)`  
  - `translateX(x)`  
  - `translateY(y)`  
    이동 함수
  - `scale(x, y)` 
  - `scaleX(x)`  
  - `scaleY(y)`  
    크기
  - `rotate(degree)`  
    회전
  - `skewX(x)`  
  - `skewY(y)`  
  - `skew(x, y)`  
    기울임 - 외각
  - `matrix(n,n,n,n,n,n)` 
- 3D 변환
  - `translate3d(x, y, z)`
  - `scaleZ(z)`
  - `scale3d(x, y ,z)`
  - `rotateX(x축)`
  - `rotateY(y축)`
  - `rotateZ(z축)`
  - `rotate3d(x축, y축, z축, 각도)`
  - `perspective(단위)`  
    원근법(거리)  
    가까울수록 입체감이 심하게 나타남 
- `perspective`  
  하위 요소를 관찰하는 원근 거리를 지정  
  단위  
  - 속성과 변환 함수 차이  
    | property                      | 적용 대상        | 기준점 설정        |
    | ----------------------------- | ---------------- | ------------------ |
    | perpective: 600px             | 관찰 대상의 부모 | perspective-origin |
    | transform: perspective(600px) | 관찰 대상        | tranform-origin    |  
    
    그리 인해 카메라 중점이 달라져서 보여지는게 달라짐
- `backface-visibility`  
  3D 변환으로 회전된 요소의 뒷면 숨김 여부
  visible | hidden


    
## 띄움
- `float`
  이미지나 기타 등에 지정하면 지정위치-크기 옆으로 인라인 요소가 흐름  
- `clear`
  플로팅 된 요소 해제

  ```css
  부모
  .clearfix::after {
    content: "";
    display: block;
    clear: both;
  }
  ```

## 애니메이션
## 그리드
## 다단
## 필터
