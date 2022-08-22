### 타입

- 단순 원시 타입: string. number, boolean, null, undefined
  - typeof null // object => 언어 자체의 버그
- 복합 원시 타입(객체 하위 타입): Objects, Arrays, Functions, RegExps
- 자바스크립트 엔진은 상황게 맞게 문자열 원시 값을 자동으로 String 객체로 강제변환하여 메서드 접근이 기능하게 도외준다.
  - Date 값은 리터럴 형식이 없어서 반드시 생성자 형식으로 생성해야 한다.
- 되도록 생성자 형식은 지양하고 리터럴 형식을 사용. 추가 옵션이 필요한 경우에만 생성자 형식을 시용하자.

### 내용 (그래서 내용이 뭐야? 제목이 왜 내용이징..)

- 객체 프로퍼티명은 언제나 문자열이다. 문자열 이외의 디른 원시 값을 쓰면 우선 문자열로 변환된다.
- ES6부터는 계산된 프로퍼티명 이리는 기능 추가: myObject[prefix+name] 형태의 계산식 값
- 자바스크립트에서 '힘수'와 '메서드'란 말은 서로 바꿔 사용할 수 있다. (그래서 프로퍼티와의 차이는 뭔데?)
```javascript
function anotherFunction() { /*. .*/ }
var anotherObject = { c: true}
var anotherArray = [];
var myObject = {
  a: 2,
  b: anotherObject,// 사본이 아닌 레퍼런스다! 
  c: anotherArray, // 역시 레퍼런스다!
  d: anotherFunction
};
anotherArray.push( anotherObject, myObject );
```
- 얕은 복사 후 생성된 새 객체의 a 프로퍼티는 원래 값 2가 그대로 복사되지만 b, c, d 프로퍼티는 원 객체의 레퍼런스와 같은 대싱을 가리키는 또 다른 레퍼런스다.
- 깊은 복사는 anotherArray가 anotherObject와 myObject를 가리키는 레퍼런스를 갖고 있으므로 원래 레퍼런스가 보존되는 게 아니라 이들까지 함께 복사된다.
- JSON.stringify 로 대안은 될 수 있음
- 프로퍼티 서술자... 생소.. 쓸일 많낭?


