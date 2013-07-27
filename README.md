naming-conventions
==================

내가 주로 사용하는 네이밍 컨벤션


## 변수명

### 복수형과 List
- 복수형: 어떤 요소를 포함한 네이티브 배열
- List: 어떤 요소의 집합을 래핑한 컬렉션인 경우

        var fruits = [ 'Apple', 'Banana', 'Cherry' ];
        var fruitList = new FruitList('Apple', 'Banana', 'Cherry');


### 복수형과 Map
- 복수형: 네이티브 배열
- Map: key/value를 가진 맵

        var handlers = [ func, func, func, ... ];
        var handlerMap = {
          onclick: func,
          onmousemove: func
        };


### 정규식
`r` 접두사를 쓴다.

        var rName = /^[a-zA-Z]+$/;


## 메서드의 파라미터

필수인 경우 각각의 인자로 정의하고, 옵션인 경우 `opts`라는 이름의 객체로 받는다.

````
function registerUser(id, name, opts) {
  // id, name은 필수
  // opts는 옵션
}

registerUser(1234, 'user a', {
  phone: '123-1234',
  address: 'Seoul'
});
````


## 메서드명

### makeX vs. createX
- make: 어떤 틀에서 만들어낸다.
- create: 아무 것도 없는 것에서 만들어낸다.

        function makeRedCar();
        function createRandomNumber();


### removeX vs. deleteX
- removeX: 복구할 수 없도록 완전히 제거한다.
- deleteX: 삭제하지만, 보이지 않거나 또는 다시 복구할 수 있다.


### X & tryX
- X: 작업 중 오류가 발생하면 에러를 던짐
- tryX: 오류가 발생하면 에러를 잡고, 결과에 따라 true/false를 리턴함. 파라미터로 건낸 값에 결과를 할당함.

        function parse(str) {
          var parsed;
          if (typeof str === 'string') {
            // parse string
            return parsed;
          }
          throw new Error('parsing error');
        }

        function tryParse(str, result) {
          try {
            result.out = parse(str);
            return true;
          } catch (e) {
            return false;
          }
        }


### cleanX & clearX
- cleanX: 지저분한 것들을 깨끗이 치운다. 예) 빌드 전 디렉토리를 지운다.
- clearX: 방해가 되는 것들을 치운다. 예) 음?

### push & pop
### add & remove

