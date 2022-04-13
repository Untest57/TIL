# 220405 CSS 속성

## 표현
### 단위
- px
  픽셀
- %
- em
  요소의 글꼴 크기
- rem
  루트 요소(html)의 글꼴 크기
- vw / vh
  뷰포트 가로/세로 너비의 백분율

### 색상 표현
- 색상 이름
  red, tomato
- Hex(RGBA)
  #000, #000000, #00000000
- RGB
  rbg(255, 255, 255)
- RGBA
  rbga(255, 255, 255, 1.0)
- HSL
  hsl(120, 100%, 50%)
- HSLA
  hsla(120, 100%, 50%, 1.0)

## 단축
- 보통  
  (top, right, bottom, left)  
  (top, bottom), (left, right)  
  top, (left, right), bottom  
  top, right, bottom, left  

## 박스 모델
- `width, height`  
  가로/세로 너비  
  auto | 단위(px, em, vw 등)  
  - auto  
    - Inline  
      가로/세로를 컨텐츠 크기로 줄임  
      적용 안됨  
    - Block  
      가로는 부모 요소만큼 늘리고 세로는 컨텐츠 크기로 줄임  
- `max-width, max-height`  
  최대 가로/세로 너비  
  none | auto | 단위  
- `min-width, min-height`  
  최소 가로/세로 너비  
  auto(0) | 단위
- `margin`  
  요소의 <b>외부</b> 여백을 지정 하는 단축 속성  
  0 | auto | 단위(단축) | %(부모 요소의 가로 너비를 비율로)
  - `auto`  
    가운데 정렬 
    `display: block`, 크기가 지정되어 있을 때, 좌우만
- `margin-방향`
- `padding`  
  요소의 <b>내부</b> 여백을 지정 하는 단축 속성  
  요소의 크기가 커짐  
  0 | 단위 | %(부모 요소의 가로 너비에 대한 비율)
- `padding-방향`  
- `border`  
  요소의 테두리 선을 지정하는 단축 속성  
  medium none black  
  선-두께 선-종류 선-색상  
  (border-width) (border-style) (border-color)  
  - `border-width`  
    요소 테두리 선두꼐의 단축 속성  
    medium | thin | thick | 단위  
  - `border-style`  
    요소 테두리 선 스타일의 단축 속성  
    none | solid(일반 선) | dotted(점선) | dashed(파선) | 등등  
  - `border-color`  
    요소 테두리 선의 색상을 지정하는 단축 속성  
    요소글자색 | 색상 | transparent  
  - `border-방향-속성`  
- `border-radius`  
  요소의 모서리를 둥굴게 까는 단축 속성(왼쪽 상단에서 시계)  
  단위의 반지름 정원 만큼 남김  
  0 | 단위  
- `box-sizing`  
  요소의 크기 계산 기준을 지저  
  content-size | border-box  
  - content-size  
    컨텐츠 크기만  
  - border-box  
    content + padding + border
- `overflow`  
  요소의 크기 이상으로 내용이 넘쳤을 떄, 보여짐을 제어하는 단축 속성  
  visible | hidden | scroll(강제로) | auto(넘치는 부분만)  
  - `overflow-x / overflow-y`   
- `display`  
  요소의 화면 출력(보여짐) 특성  
  block | inline | inline-block | flex | grid | none(안 보임) | 등등
- `opacity`  
  요소의 투명도  
  0.0 - 1.0

## 글꼴, 문자
- `h1-6`  
- `font-style`  
  글자의 기울기  
  normal | italic
- `font-weight`  
  글자의 두께(가중치)  
  normal(400) | bold(700) | bolder(상위(부모)) | lighter(상위(부모)) | 100-900
- `font-size`  
  글자의 크기  
  16px | 단위 | %(부모) | smaller | larger | xx-small-xx-large(7단계)
- `font-height`  
  한 줄의 높이, 행간과 유사  
  normal | 숫자-소수점(요소의 글꼴 크기의 배수) | 단위
- `font-family`
  글꼴(서체) 지정
  글꼴1, "글꼴 2", ... **글꼴계열**;
  - 글꼴계열
    - serif - 바탕체 계열
    - sans-serif - 고딕체 계열
    - monospace - 고정너비(가로폭이 동등)
    - cursive - 필기체 계열
    - fantasy - 장식 글꼴 계열
- `color`  
  글꼴의 색상  
  rgb(0, 0, 0) | 색상
- `text-align`  
  문자의 수평정렬 방식  
  left | right | center | justify
- `text-decoration`  
  문자의 장식(선)  
  none | underline | overline | line-through(중앙)
- `text-indent`  
  문자의 첫 줄의 들여쓰기
  0 | 단위

## 배경
- `background-color`  
  요소의 배경 색상  
  transparent | 색상
- `background-image`  
  none | url("경로") | gradient
  - gradient
    - `linear-gradient([각도나 to], color1, color2)` [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient#syntax)
- `background-repeat`  
  repeat | repeat-x | repeat-y | no-repeat
- `background-position`  
  0% 0% | (top, bottom, center), (left, right, center) | center | 단위(x, y)
- `background-size`  
  auto | x(단위), y(단위) | x(단위, 비율 유지) | cover(비율 유지, 요소의 더 넓은 **너비**에 맞춤) | contain(비율 유지, 요소의 더 짧은 **너비**에 맞춤)
- `background-attachment`
  요소의 배경 이미지 스크롤 특성
  scroll(요소 따라서) | fixed(뷰포트 고정, 스크롤 X) | local(요소 내 스크롤시)


