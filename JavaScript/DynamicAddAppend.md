# append() 동적 추가
- append는 컨텐츠를 선택된 요소 내부의 마지막 부분에 삽입


## 활용 예시
- 아래와 같은 HTML 코드가 있다고 가정
```
<div id="test">
  <div id="test1"></div>
</div>
```

- JavaScript append를 활용한 코드
```
$("#test").append('<div id="test2"></div>');
```

- 결과 : 컨텐츠를 선택된 요소 내부의 마지막 부분에 추가가 된다.
```
<div id="test">
  <div id="test1"></div>
</div>
```
