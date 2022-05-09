# 220509 예습

## 예습
prevent default - 기본 동작 방지
이벤트 버블링 정지 - stop propagation
이벤트 버블링 vs 이벤트 캡처링
이벤트 캡처링
```js
.addEventListener('...', cb, {
  capture: true
})
```
`event.currentTarget` vs `event.target`
이벤트 종류
load, click, input, keydown, moveenter, mouseleave, scroll, resize


### DOM 이벤트 흐름
1. Capturing Phase - 이벤트가 하위 요소로 전파
2. Target Phase - 이벤트가 실제 Target 요소로 전달
3. Bubbling Phase - 이벤트가 상위 요소로 전파  
단계는 나눠져 있지만 2번은 실제로 처리되지 않고, 2번에서 1, 3번이 실행된다.

- `event.eventPhase`  
  현재 이벤트 단계 확인
- `.addEventListener`  
  순서대로 실행(먼저 추가된 것 부터)
- `.addEventListener`  
  로 지정한 이벤트를 모두 실행한 뒤 브라우저 기본 동작이 실행됨


### Event Bubbling(이벤트 버블링)
한 요소에 이벤트가 발생(Target Phase)하면 자기 자신 -> 부모 -> 조상 순서로  
최상위까지(`<html>` 요소 -> `document` -> 때때로 `window`) 이벤트 핸들러가 동작  
거의 대부분 이벤트에서 발생


### `.target` vs `.currentTarget` === `this`
- `.target`  
  실제 이벤트가 발생한 요소
- `.currentTarget` === `this`  
  현재 이벤트가 실행 중인 요소  
  실제 이벤트의 실행된 요소가 아닌 캡처링/버블링에 의해 상위 요소에서 핸들러가 작동할 수도 있다.


### `.stopPropagation()`  
버블링 중단


#### `.stopImmediatePropagation()`
다른 핸들러 동작까지 막음


### Event Capturing(이벤트 캡쳐링)
이벤트가 최상위(window?) 에서 시작 아래로 전파되는 것  
```js
.addEventListener('...', cb, { capture: true })
.addEventListener('...', cb, true)
```
Capturing 단계에서 핸들러 동작

Capturing 옵션을 줬으면 `.removeEventListener(...)` 도 옵션을 줘야함


### 브라우저 기본 동작
태그에 따라 브라우저에 의해 정해진 동작  


#### 막기
```js
// 1
event.preventDefault();

// 2 '.addEventListener 로 등록한 경우가 아닌 경우 - event.on{EVENT} = '
return false;
```


#### `.addEventListener(..., { passive: true })`  
브라우저에게 `.preventDefault()` 를 호출하지 않겠다고 알림  
기본 동작이 막힐 일 없으니 브라우저 기본 동작이 막힘 없이 실행됨(`touchmove`에 의한 발생한 스크롤링 같은거?)


#### `event.defaultPrevented`  
버블링 단계에서 전에 처리된(하위 요소) 핸들러가 기본 동작을 막았는지(`.preventDefault()`) 확인  
`.stopPropagation()` 으로 버블링을 막으면 상위에서는 그 이벤트가 발생했는지 알수 없음으로 버블링은 막지 않고  
기본 동작을 막았는지 확인해서 처리하는 것을 추천