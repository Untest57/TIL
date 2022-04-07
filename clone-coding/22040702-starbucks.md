# 220407 스타벅스 클론

## 오픈 그래프 [자세히](https://ogp.me/)

### 카카오톡
```html
<meta property="og:type" content="website" />
<meta property="og:site_name" content="Starbucks" />
<meta property="og:title" content="Starbucks Coffee Korea" />
<meta property="og:description" content="스타벅스는 세계에서 가장 큰 다국적 커피 전문점으로, 64개국에서 총 23,187개의 매점을 운영하고 있습니다." />
<meta property="og:image" content="./images/starbucks_seo.jpg" />
<meta property="og:url" content="https://starbucks.co.kr" />
```

- og:type: 페이지의 유형(E.g, website, video.movie)
- og:site_name: 속한 사이트의 이름
- og:title: 페이지의 이름(제목)
- og:description: 페이지의 간단한 설명
- og:image: 페이지의 대표 이미지 주소(URL)
- og:url: 페이지 주소(URL)

### 트위터 [자세히](https://developer.twitter.com/en/docs/twitter-for-websites/cards/guides/getting-started)
```html
<meta property="twitter:card" content="summary" />
<meta property="twitter:site" content="Starbucks" />
<meta property="twitter:title" content="Starbucks Coffee Korea" />
<meta property="twitter:description" content="스타벅스는 세계에서 가장 큰 다국적 커피 전문점으로, 64개국에서 총 23,187개의 매점을 운영하고 있습니다." />
<meta property="twitter:image" content="./images/starbucks_seo.jpg" />
<meta property="twitter:url" content="https://starbucks.co.kr" />
```
- twitter:card: 페이지(카드)의 유형(E.g. summary, player)
- twitter:site: 속한 사이트의 이름
- twitter:title: 페이지의 이름(제목)
- twitter:description: 페이지의 간단한 설명
- twitter:image: 페이지의 대표 이미지 주소(URL)
- twitter:url: 페이지 주소(URL)

### SEO  
검색엔진최적화

## 폰트
google font 같은 사이트를 찾아서 라이센스를 확인하고  
`<link>` 로 연결하고 `font-family` 설정

## Icons
google material icons 같은 사이트를 찾아서 가이드대로 추가 후 사용
google material icons 은 기본 사이즈가 24px

## 기본
```css
/* common */
body {
  color: #333;
  font-size: 16px;
  font-weight: 400;
  line-height: 1.4;
}
img { 
  display: block;
}
```

## 기술 모음

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

### 


## 헤더와 드롭다운 메뉴

## 헤더
로고가 포함된 영역
[최상위 요소들 가운데 정렬](#align-center-root)

#### 로고
[가운데 정렬](#align-center-fixed)

#### 서브 메뉴
[ul-li 메뉴](#menu-using-ulil)

#### 검색