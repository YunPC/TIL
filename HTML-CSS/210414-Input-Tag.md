# \<input>

사용자에게 입력 받을 데이터 양식

|속성|의미|값|기본값|특징|
|------|---|---|---|---|
|autocomplete|사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부|`on`, `off`|`on`|
|autofocus|페이지가 로드될 때 자동으로 포커스|불린(Boolean)|문서 내 고유해야 함
|checked|양식이 선택되었음을 표시|불린(Boolean)|`type`속성 값이 `radio`, `checkbox`일 경우만|
|disabled|양식을 비활성화|불린(Boolean)|
|form|\<form>의 `id`속성 값| |해당 \<form>의 후손이 아닐 경우만
|list|참조할 <datalist>의 `id`속성 값|
|max|지정 가능한 최대 값|숫자(Number)|`type`속성 값이 `number`일 경우만, `min`속성보다 큰 값만 허용
|min|지정 가능한 최소 값|숫자(Number)|`type`속성 값이 `number`일 경우만, `max`속성보다 큰 값만 허용|
|maxlength|입력 가능한 최대 문자 수|숫자(Number)|`524888`|`type`속성 값이 `text`, `email`, `password`, `tel`, `url`일 경우만|
|muliple|둘 이상의 값을 입력 할 수 있는지 여부|불린(Boolean)|`type`속성 값이 `email`, `file`일 경우만, `email`일 경우 `,`로 구분|
|name|양식의 이름|
|placeholder| 사용자가 입력할 값의 힌트| |`type`속성 값이 `text`, `search`, `tel`, `url`,`email`일 경우만|
|readonly|수정 불가한 읽기 전용|불린(Boolean)|
|step|유효한 증감 숫자의 간격|숫자(Number)|`1`|`type`속성 값이 `number`, `range`일 경우만|
|alt|이미지의 대체 텍스트| | `type`속성 값이 `image`일 경우만|
|type|입력 받을 데이터의 종류|별도 정리| `text`|

### 데이터 종류(Type)의 값(Values)

`type`속성에 입력할 수 있는 값의 목록

```html
<input type="button"/>
<input type="checkbox"/>
<input type="file"/>
<input type="text"/>
```

|값|데이터 종류|특징|
|-----|---|---|
|button|일반 버튼|`<button>`처럼 사용|
|checkbox|체크 박스|
|color|색상|IE 지원 불가|
|email|이메일|
|file|파일|
|hidden|보이지 않지만 전송할 양식|`value`속성으로 값을 지정|
|image|이미지 제출 버튼|`<img />`처럼 사용
|number|숫자|
|password|비밀|가려지는 양식|
|radio|라디오 버튼|같은 `name`속성 그룹 내 하나만 선택 가능|
|range|범위 컨트롤|`min`, `max`, `step`, `value`(기본값) 속성 사용|
|reset|초기화|해당 `<form>`범위 내 모든 양식
|search|검색
|submit|제출 버튼|해당 `<form>` 범위 내 고유한 양식|