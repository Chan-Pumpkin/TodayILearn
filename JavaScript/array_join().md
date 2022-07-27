## Array.join()

배열의 모든 요소를 연결해 하나의 문자열을 만듬

## 문법

```jsx
arr.join([separator])
```

## 예제

```jsx
var a = ['aa', 'bb', 'cc'];
var myVar1 = a.join();      // myVar1에 'aa,bb,cc'을 대입
var myVar2 = a.join(', ');  // myVar2에 'aa, bb, cc'을 대입
var myVar3 = a.join(' + '); // myVar3에 'aa+ bb + cc'을 대입
var myVar4 = a.join('');    // myVar4에 'aabbcc'을 대입
```

## 참고

[Array.prototype.join() - JavaScript | MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

[[javascript] join() 함수 - 배열의 원소를 문자열로 합치기](https://yeoncoding.tistory.com/46)
