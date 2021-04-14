# \<fieldset>, \<legend>

같은 목적의 양식을 그룹화(`<fieldset>`)하여 제목(`<legend>`)을 지정

```html
<form>
    <fieldset>
        <legend>Coffee Size</legend>
        <label>
            <input type="radio" name="size", value="tall">
        </label>
        tall
        <label>
            <input type="radio" name="size", value="grande">
        </label>
        grande
        <label>
            <input type="radio" name="size", value="venti">
        </label>
        venti
    </fieldset>
</form>
```

## \<fieldset>

같은 목적의 양식을 그룹화
|속성|의미|값|
|---|---|---|
|disabled|그룹 내 모든 양식 요소를 비활성화|불린(Boolean)|
|form|그룹이 속할 하나 이상의 `<form>`의 `id` 속성 값|
|name|그룹의 이름