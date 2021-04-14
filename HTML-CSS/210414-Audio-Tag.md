# \<audio>

소리 콘텐츠를 삽입.

- **autoplay**가 지정된 경우, **preload**는 무시됨.

|속성|의미|값|기본값|
|-------|---|---|---|
|autoplay|준비되면 바로 재생|불린(Boolean)|
|controls|제어 메뉴를 표시|불린(Boolean)|
|loop|재생이 끝나면 다시 처음부터 재생|불린(Boolean)
|preload|페이지가 로드될 때 파일을 로드할지의 지정(힌트 제공)|`none`:로드하지 않음<br>`metadata`:메타데이터만 로드<br>`auto`:전체 파일로드|`metadata`|
|src|콘텐츠 URL|`URl`|
|muted|음소거 여부|불린(Boolean)

```css
audio {display: inline;}
```