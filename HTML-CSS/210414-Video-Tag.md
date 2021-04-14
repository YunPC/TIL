# /<video>

동영상 콘텐츠(MP4)를 삽입

- **autoplay**가 지정된 경우, **preload**는 무시됨.

|속성|의미|값|기본값|
|--------|---|---|---|
|autoplay|준비되면 바로 재생|불린(Boolean)|
|controls|제어 메뉴를 표시|불린(Boolean)|
|crossorigin|가져 오기가 CORS를 사용하여 수행되어야하는지 여부|`anonymous`, `use-credentials`|
|loop|재생이 끝나면 다시 처음부터 재생|불린(Boolean)|
|muted|음소거 여부|불린(Boolean)|
|poster|동영상 썸네일 이미지 URL|URL|
|preload|페이지가 로드될 때 파일을 로드할지의 지정(힌트 제공)|`none`:로드하지 않음<br>`metadata`:메타데이터만 로드<br>`auto`:전체 파일로드|`metadata`|
|src|콘텐츠 URL|`URl`|
|width|동영상 가로 너비|
|height|동영상 세로 너비|

```css
video {display: inline;}
```