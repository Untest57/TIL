# Tips

## Promise
- `Promise.race(...)` 사용할 때 빈 배열이 들어가지 않도록 주의해라  
  무한 대기한다

## IntersectionObserver
- 동적으로 만들어 넣는 요소를 감시 할때  
  완전히 자리를 잡고 넣던가  
  콜백이 불렸을 때(화면에 들어왔을 때나 나갔을 때) `entries.isIntersecting` 를 체크해라  
  가끔 자리 잡기 전에 불리는 경우가 있다.

## Typescript
- `Object.` 메소드들을 key 타입을 지키면서 사용하는 법
  https://www.npmjs.com/package/object-typed  
  ```sh
  npm i object-typed
  # OR
  yarn add object-typed
  ```

## nvm
- 윈도우에서 주의점
  `nvm` 설치나 설정 시 꼭 관리자 권한으로 할 것  
  이후 사용은 상관없음
  이유: node.js 폴더의 링크를 바꾸는 식으로 적용하는데 이때 보통 'Program Files' 에 깔려서 여기 접근하는데 관리자 권한이 필요하다.


## Font
### weight - name
| Value | Common weight name        |
| ----- | ------------------------- |
| 100   | Thin (Hairline)           |
| 200   | Extra Light (Ultra Light) |
| 300   | Light                     |
| 400   | Normal, Regular           |
| 500   | Medium                    |
| 600   | Semi Bold (Demi Bold)     |
| 700   | Bold                      |
| 800   | Extra Bold (Ultra Bold)   |
| 900   | Black (Heavy)             |