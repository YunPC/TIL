# 부모와 자식 요소

태그A가 태그B의 콘텐츠로 사용되면, 태그 B는 태그A의 부모 요소, 태그A는 태그B의 자식요소이다.

```html
<PARENT>
    <CHILD></CHILD>
</PARENT>
```

```html
<section class ="fruits">
    <h1>과일 목록</h1>
    <ul>
        <li>사과</li>
        <li>딸기</li>
        <li>바나나</li>
        <li>오렌지</li>
    <ul>
</section>

<!-- 다음과 같이 이해할 수 있다. -->
<섹션영역 class ="fruits">
    <주제1>과일 목록</주제1>
    <순서없는목록>
        <항목>사과</항목>
        <항목>딸기</항목>
        <항목>바나나</항목>
        <항목>오렌지</항목>
    <순서없는목록>
</섹션영역>
```

