# Javascript  기초

- 변수 선언

  - let: 변할 수 있는 값
  - const: 변하지 않는 값

  1. 변수는 문자, 숫자, $, _만 사용 가능
  2. 첫 글자는 숫자가 될 수 없음
  3. 예약어는 사용할 수 없음
  4. 상수는 대문자로 알려 주기   예) const MAX_SIZE = 99;
  5. 변수명은 읽기 쉽고 이해할 수 있게 선언

  - 앞에 \을 넣어 주면 특수 문자 인식
  - ${변수}, ${표현식}

- 숫자는 사칙연산 가능

- typeof 연산자: 변수의 자료형을 알아냄 예) console.log(type of "안녕")

  

- 형 변환 (**대문자**로 쓰기)

  - String() -> 문자형으로 변환
  - Number() -> 숫자형으로 변환
    - true, false는 1, 0으로 변환
    - 문자는 NaN으로 변환
    - Number(null) -> 0, Number(undefined) -> NaN
  - Boolean() -> 불리언형으로 변환
    - false: 숫자 0, 빈 문자열 "", null, undefined, NaN
    - true: 문자 0, 공백

  ------

- alert: 알림

- prompt: 입력받음 -> 입력받은 값은 문자형

  ![image-20220719233337612](C:\Users\kiwio\AppData\Roaming\Typora\typora-user-images\image-20220719233337612.png)

  - 두 개의 값을 인수로 받을 수 있음 => 뒤의 값은 디폴트 값이 된다

    ![image-20220719233507649](C:\Users\kiwio\AppData\Roaming\Typora\typora-user-images\image-20220719233507649.png)

- confirm: 확인받음

  - 확인과 취소 버튼 있음 => 확인이면 true, 취소면 false

  ![image-20220719233553504](C:\Users\kiwio\AppData\Roaming\Typora\typora-user-images\image-20220719233553504.png)

- 단점: 스크립트 일시 정지, 스타링 X

----

a = 3 ->  a에 3을 넣어 주기

a == 3 -> a와 3을 비교, 값만 비교 (동등 연산자)

=== -> 타입까지 비교 (일치 연산자)

```javascript
const isAdult = age > 19;
if(!isAdult) {
    console.log('미성년자는 출입 불가능합니다.')
}
```

- 이러한 방식으로 boolean 변수로 사용 가능

```javascript
// 우선 순위
// 여자고, 이름이 Sally이거나 성인이면 통과

const gender = 'M';
const name = 'John';
const isAdult = true;

if(gender === 'F' && name === "Sally" || isAdult) {
	console.log('통과')
} else {
	console.log('실패')
}
// 이 경우 console에 '통과'로 찍힘
// AND 연산자가 우선순위가 높아서 'gender === 'F' && name === "sally"'가 먼저 처리되고,
// 그 이후에 isAdult가 처리되기 때문에

// 의도한 바대로 표현해 주려면 중간에 괄호를 쳐 줘야 한다
// 이름이 Sally이거나 성인
if(gender === 'F' && (name === "Sally" || isAdult)) {
	console.log('통과')
} else {
	console.log('실패')
}
```