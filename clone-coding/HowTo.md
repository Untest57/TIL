# 기술 모음

## BEM(Block Element Modifier)
Block__Element--Modifier  
Block 은 많이 길어질수도 있음으로 Block 이 꼭 HTML 상 부모일 필요는 없다.    
상위요소 일수도 있다.  

## How To

### 최상위 요소들 가운데 정렬 {#align-center-root}
```html
  <body>
    <header|main|footer>
      <div class="inner">
        ...
      </div>
    </header|main|footer>
  </body>
```
```css
  body > header|main|footer > .inner {
    width: 지정;
    margin: 0 auto;
  }
```

### `img { display: block; }`
img 는 기본적으로 inline 으로 inline 요소는 기본적으로 baseline 정렬로 하단에 공간이 잡힌다.

### 수직수평 가운데 정렬

#### 가로세로 크기를 지정했을 때 {#align-center-fixed}

##### `position: absolute`, `margin: auto`, `오프셋: 0` 을 이용해 정렬하는 법  
```html
<div class="container">
  <div class="item"></div>
</div>
```
```css
.container {
  position: relative;
}
.item {
  position: absolute;

  width: 지정;
  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;

  height: 지정;
  top: 0;
  bottom: 0;
  margin-top: auto;
  margin-bottom: auto;
}
```

##### `위치지정: 50%; margin: (width|height) * 0.5` 로 정렬하는 법


### 메뉴  

#### `ul`, `li` 이용 {#menu-using-ulil}
```html
<ul class="menu">
  <li><a href="javascript:void(0)">1</a>
  <li><a href="javascript:void(0)">2</a>
  <li><a href="javascript:void(0)">3</a>
</ul>
```
```css
ul.menu {
  display: flex;
}
ul.menu li {
  display: relative;
}
ul.menu li::before {
  content: "";

  position: absolute;
  width: 1px;
  height: 12px;
  top: 0;  bottom: 0;
  margin: auto;

  background-color: #e5e5e5;
}
ul.menu li:first-child::before {
  display: none;
}
ul.menu li a {
  font-size: 12px;
  /* 클릭하기 편하게 영역 잡아주기 */
  padding: 11px 16px;
  display: block;
}
```

### 아무 일도 하지 않는 `a` 태그
`<a href="javascript:void(0)">LINK</a>`

### height|widht 크기 변경 시 `overflow: hidden` 으로 넘치는 부분 안 보이게 하기

