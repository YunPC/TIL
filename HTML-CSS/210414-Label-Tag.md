# \<label>

라벨 가능 요소(labelable)의 제목(Caption)

- **for** 속성으로 라벨 가능 요소를 참조하거나 콘텐츠로 포함
- 라벨 가능 요소: \<button>, \<input>, \<progress>, \<select>, \<textarea>

|속성|의미|
|---|----|
|for|참조한 라벨 가능 요소의 `id` 속성 값|

```html
<!-- 라벨 가능 요소를 참조 -->
<input type="checkbox" id="user-agreemnet"/>
<label for="user-agreement">동의하십니까?</label>

<!-- 라벨 가능 요소를 포함 -->
<label><input type = "checkbox" />동의하십니까?</label>
```

```css
label {display:inline;}
```