# 접근성

### 접근성 전용 숨김

`position:absolute`로 레이아웃에서 분리하고, 
`width/height:1px`으로 최소 크기로 줄인 뒤, 
`margin/padding/border:0`으로 여백·테두리를 없애고, 
`overflow:hidden`과 `clip`/`clip-path`로 표시 영역을 잘라 시각적으로 완전히 숨기며, 
`white-space:nowrap`으로 줄바꿈을 막는다.
해당 코드는 화면에는 안 보이지만 접근성 트리에는 남아 스크린리더가 읽을 수 있게 만드는 sr-only(접근성 전용 숨김) 패턴이다.

```css
._hidden {
  overflow: hidden;
  white-space: nowrap;
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  position: absolute;
  width: 1px; height: 1px;
  margin: 0; padding: 0; border: 0;
}
```
