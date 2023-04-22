# Chapter 2. 퍼블리싱 심화 및 자바스크립트 기초 (1)

## 📝 학습 목표

---

1. 레이아웃을 잘 짜보자구요…!
2. 자바스크립트의 마스터가 되어야 합니다…!

## 📸잠깐 ! 스터디 인증샷은 찍으셨나요?📸

---

- 스터디리더께서 대표로 매 주차마다 한 장 남겨주시면 좋겠습니다!🙆💗
  (사진을 저장해서 이미지 임베드를 하셔도 좋고, 복사+붙여넣기해서 넣어주셔도 좋습니다!)

[https://www.notion.so](https://www.notion.so)

## 🎯 핵심 키워드

---

<aside>
💡 주요 내용들에 대해 조사해보고, 자신만의 생각을 통해 정리해보세요!
레퍼런스를 참고하여 정의, 속성, 장단점 등을 적어주셔도 됩니다.
조사는 공식 홈페이지 **Best**, 블로그(최신 날짜) **Not Bad**

</aside>

- 변수
  | | 재할당(Reassignable) | 변경(Mutable) |
  | ----- | -------------------- | ------------- |
  | let | Yes | Yes |
  | const | No | Yes |
  **변수가 가리키고있는 `object의 값을 변경`하는것은 `let`, `const` `둘다 가능`합니다.**

  - var

    # Var(💩)

    그동안 코딩을 하면서 우리는 `var`, `let`, `const` 라는 변수가 있다는 것은 알았을 것이다. `const`는 재할당이 필요 없는 경우 자주 사용하고, `let`은 재할당이 필요한 경우 사용, `var`은 사용하는 경우를 보지못했을 것이다. 그러고 대부분의 강사마다 사용하지말라고 아마 추천을 할 것이다. 그이유는 무엇인지에 대해 알아보자!

    ***

    # var을 사용하지 않는 이유!

    1. `**변수를 선언하는 키워드 없이 선언 & 할당이 가능**`하다.

       즉, 선언인지 재할당인지 구분하기가 매우 어렵다.

       ```jsx
       // 1. 변수를 선언하는 키워드 없이 선언 & 할당이 가능함
       // 선언인지, 재할당인지 구분하기 어려워요
       something = '💩'; // var를 선언하지 않음
       console.log(something);
       ```

    ***

    1. 중복 선언이 가능하다. (버그 유발, 실수 유발, 협업시 더 곤란해지고 어려워짐)

       ```jsx
       var poo = '💩'; // 어떤 poo를 썼는지 이해가 안됨 ㅠ
       var poo = '💩';
       console.log(poo);

       // 첫번째 변수 선언+초기화
       var a = 10;
       console.log(a); // 10

       // 두번째 변수 선언+초기화
       var a = 20;
       console.log(a); // 20

       // 세번째 변수 선언(초기화X)
       var a;
       console.log(a); // 20
       ```

       `var`로 선언한 변수는 중복해서 선언이 가능합니다.

       이 경우, 마지막에 할당한 값이 변수에 저장이 됩니다.

       하지만, 초기화 없이 `var a;` 처럼 선언만 한 경우에는 선언문 자체가 무시됩니다.(에러 발생 X)

       위와 같은 이유로 기존에 선언을 한 변수의 존재를 까먹고, 값을 재할당하게 되는 등의 실수가 발생하기 쉽습니다.

       이를 해결해서 나온 것이 `let`, `const` 입니다. 위와 같이 중복해서 선언했을 경우, `let`, const는 `SyntaxError: Identifier 'b' has already been declared` 에러가 발생합니다.

    ***

    1. 블록 레벨 스코프 작동이 되지 않는다.

       `**스코프란?**`

       유효한 참조 범위를 의미합니다. 예를 들어, 함수 내부에서 선언된 변수는 함수 내부에서만 참조가 가능합니다.

       3-1. `var : function-level scope` (함수 레벨 스코프)

       ```
       // 4. 함수 레벨 스코프만 지원 됨
       function example() {
         var dog = "🐕";
       }
       console.log(dog); // dog is not defined

       // var를 사용하면 나도 모르게 버그를 발생시키게 됨..

       ```

       `var`은 `함수 내부에 선언된 변수만 지역변수로 한정`하며, `나머지는 모두 전역변수`로 간주합니다.

       위와 같이 **example 함수 내부에서 선언된 dog라는 변수는 function 함수 내부에서만 참조가 가능**합니다. 외부에서 참조할시 에러가 발생합니다.

       그러나, 함수를 제외한 영역에서는 `var`로 선언한 변수는 전역변수로 취급됩니다.

       ```jsx
       if (true) {
         var a = 10;
         console.log(a); // 10
       }
       console.log(a); // 10
       ```

       ```jsx
       var apple = '사과';
       {
         var apple = '🍎';
         {
           var apple = '🍏';
         }
       }
       console.log(apple); // 원래라면 함수 바깥에 있으므로 "사과"가 출력되야 하는데 초록 사과가 출력됨
       ```

       ***

       3-2. **`let, const : block-level scope (블록 레벨 스코프)`**

       ```jsx
       if (true) {
         let a = 10;
         const b = 20;
         console.log(a); // 10
         console.log(b); // 20
       }

       console.log(a); // ReferenceError: a is not defined
       console.log(b); // ReferenceError: a is not defined

       function test() {
         let c = 30;
         console.log(c); // 30
       }
       console.log(c); // ReferenceError: a is not defined
       ```

       `let`, `const`로 선언된 변수는 `함수 내부는 물론, if, for 등의 코드블럭에서 선언된 변수도 지역변수로 취급`합니다.

       정리해보면

       **`var` : 함수 내부에 선언된 변수만 지역변수로 인정하는 `함수 레벨 스코프`
       `let`, `const` : 블록 내부에서 선언된 변수까지도 지역변수로 인정하는 `블록 레벨 스코프`**

    ***

  - let

    # let

    `let`은 재할당이 가능합니다.

    ```jsx
    //변수 선언
    let a;

    // 변수 선언과 값의 할당 (메모리 어딘가에 0이라는 값을 할당)
    // a라는 변수는 메모리 주소를 가리킵니다.(메모리 주소 0x000006)
    // 메모리 주소를 변수로 사용하면 기억하기 어렵고, 가시성이 떨어집니다.
    let a = 0;

    // 값의 재할당 (value reassigning)
    a = 1;
    ```

    ```jsx
    let a = 0;
    console.log(a);

    // 0이 출력됨

    a = 1;
    console.log(a);

    // 재할당되어 1이 출력됨

    let b;
    console.log(b);

    // undefined 출력 아무것도 정해지지 않은 상태입니다.

    b = 2;
    console.log(b);

    // 2 출력
    ```

  - const

    # const

    `const`는 재할당이 불가능합니다.

    ```jsx
    // let 재할당이 가능
    let a = 1;
    a = 2;

    // const 재할당이 불가능
    // 1. 상수
    // 2. 상수변수 또는 변수
    const text = 'hello'; // 한번 값을 할당하면 재할당 불가능.
    text = 'hi'; // Uncaught TypeError: Assignment to constant variable.

    // 1. 상수(상수로 사용할때는 항상 대문자를 이용합니다. 단어와 단어사이 분리할떄는 _ 를 활용합니다.)
    const MAX_FRUITS = 5;

    // 2. 재할당 불가능한 상수변수 또는 변수
    const apple = {
      name: 'apple',
      color: 'red',
      display: '사과 사진',
    };

    // apple = {}; 한번 할당하고 재할당이 불필요한 경우에는 const를 활용합니다.
    console.log(apple);
    // const로 선언한 경우에도 .name, .display등으로 객체값을 변경할 수 있습니다.
    apple.name = 'orange';
    apple.display = 'green apple 이미지';
    console.log(apple);
    ```

    **변수가 가리키고있는 `object의 값을 변경`하는것은 `let`, `const` `둘다 가능`합니다.**

- 함수선언

  ### 함수란?

  특정한 일을 수행하는 코드들의 집합을 `함수`라고 합니다.

  ### 함수를 사용하면 좋은 점!

  1. `유지 보수성`
  2. `높은 가독성`
  3. `재사용 가능`

  ### 함수 만드는 방법 예시!

  ```jsx
  function add(a, b) {
    return a + b;
  } // 함수 정의

  add(1, 2); //함수 호출
  // 즉 1과 2는 a,b 에 전달이 됩니다.

  // function: 함수 정의 키워드
  // add : 함수 이름
  // (a, b) : 매개변수, 인자 (parameter)
  // return a + b; 결과값 반환
  ```

  ### 함수의 이름을 지을시 유의사항!

  1. 수행하는 일을 잘 나타낼 수 있는 이름을 지어야합니다.
  2. 매개변수 이름 또한 `의미있게 작성`해야 합니다.

  ### 함수 선언시 어느 메모리 공간에 할당되는가?

  함수 또한 선언시 `힙이라는 메모리 공간에 할당`이 되어집니다. (정보가 가득 담겨져있으니 메모리 셀 하나가 아닌 여러개로 이루어집니다.)
  `함수이름 add`는 `메모리에 객체가 담겨져있는 메모리 주소를 담고 있습니다.`
  또한 함수의 이름은 함수를 참조하고 있습니다.
  즉, sum에 add를 할당했으므로 `**sum은 add의 메모리 주소(함수의 객체의 주소)를 참조**`하고 있는걸 확인할 수 있습니다.
  후에 `콜백함수시 매우 중요한 포인트`가 되는 부분이니 확실하게 이해합시다.

  ### Default Parameters

  매개변수의 기본값은 무조건 undefined이다. 즉, `return undefined`
  매개변수의 정보는 함수 내부에서 접근이 가능한 `arguments`라는 객체에 저장이 됩니다.
  `Default Parameter`를 사용하면 주어진 값이 없거나 undefined가 전달될 경우, 매개변수를 기본으로 초기화 할 수 있습니다.
  즉, 값이 전달되지 않는 함수 파라미터의 기본값을 설정하는 방법입니다, 함수에서 매개 변수가 제공되지 않은 경우 값이 정의되지 않습니다. 이 경우, 지정한 기본값이 컴파일러에 의해 적용됩니다.

  ```jsx
  function greet(name = 'noob master') {
    console.log('Welcome mr.' + name);
  }

  greet('Jagathish'); // Welcome mr.Jagathish
  greet(); //Welcome mr.noob master
  greet(''); // Welcome mr.

  // 다음은 기본 매개 변수를 사용하는 또 다른 예입니다. 값이 정의되지 않은 경우(undefined)에만 적용됩니다. null에는 적용되지 않고 null이 출력되는점 참고해야합니다.
  function test(num = 1) {
    console.log(num);
  }

  test();
  1;
  test(undefined);
  1;
  test(null);
  null;
  test('');
  ('');
  test(false);
  false;
  test(NaN);
  NaN;

  // 어떤 순서든 Default Parameter를 사용할 수 있으며 이는 기본 Parameter 이후에 기본 파라미터가 아닌 파라미터를 사용할 수 있음을 의미합니다.

  function test(a = 10, b, c = 100, d) {
    console.table(a, b, c, d);
  }
  test(undefined, 10); // 10,10,100,undefined
  test(100); // 100, undefined, 100 , undefined
  test(); // 10, undefined, 100, undefined
  ```

  ### Rest Parameters (몇개의 인자를 받을지 모를떄 사용합니다.)

  ```jsx
  // Rest 매개변수 Rest Parameters
  // 몇개의 인자를 받을지 모를떄 사용이 가능합니다.
  function sum(...numbers) {
    console.log(numbers);
  }
  sum(1, 2, 3, 4, 5, 6, 7, 8);

  // (8)  [1, 2, 3, 4, 5, 6, 7, 8]

  // 아래와 같이 사용할 수도 있습니다.

  function sum(a, b, ...numbers) {
    console.log(a); // 1
    console.log(b); // 2
    console.log(numbers); // [3, 4, 5, 6, 7, 8]
  }

  sum(1, 2, 3, 4, 5, 6, 7, 8);
  // (6) [3, 4, 5, 6, 7, 8]
  ```

- ES6

  - 화살표 함수

    # 화살표 함수 표현(arrow function expression)

    전통적인 함수 표현의 간편한 대안입니다. 하지만, 화살표 함수는 몇 가지 제한점이 있습니다.
    **사용 방법**

    ```jsx
    const name = () => {};
    ```

    **실제 사용 예시**

    ```jsx
    // 일반 함수 표현식
    let add = function (a, b) {
      return a + b;
    };

    // 화살표 함수 표현식
    let add = (a, b) => a + b;
    ```

    1. 인수가 하나밖에 없을시 인수를 감싸는 괄호를 생략할 수 있다. 괄호를 생략하면 코드의 길이를 줄일 수 있다.

    ```jsx
    let double = (n) => n * 2;
    ```

    1. 인수가 하나도 없을 땐 괄호를 비워놓으면 된다.

    ```jsx
    let double = () => console.log('인수 내놔');
    ```

    1. 평가해야 할 표현식이나 구문이 여러 줄인 화살표 함수

    ```jsx
    let add = (a, b) => {
      let result = a + b;
      return result; // 중괄호를 사용했다면, return 지시자로 결괏값 반환 필요!
    };

    add(1, 2); // 3
    ```

  - spread 연산자

    # spread 연산자 (전개 구문)

    모든 Iterable(반복 가능한 것)은 `spread 연산자(EcmaScript 2018)`를 활용할 수 있습니다.
    즉, 순회 가능한 것을 의미합니다.
    `func(…iterable)` , `[…iterable]`, `{ …obj }` 와 같이 사용할 수 있습니다.
    예제.

    ```jsx
    function add(a, b, c) {
      return a + b + c;
    }

    const nums = [1, 2, 3];
    ```

    위의 함수의 인자들에 nums의 값들을 순서대로 넣고 싶다고 가정해봅시다.

    ```jsx
    console.log(add(nums[0], nums[1], nums[2]));
    ```

    이렇게 해도 상관은없습니다. 하지만, 더 편한 방법이 있습니다. 이러한 경우에 `spread 연산자`를 활용하면 좋습니다!

    ```jsx
    console.log(add(...nums));
    ```

    nums 배열 안에 있는 값들이 하나하나 저장되어서 더해집니다.

    ### Rest Parameters 에서 spread 연산자 활용

    ```jsx
    // Rest Parameters
    function sum(first, second, ...nums) {
      console.log(nums); // [ 0, 1, 2, 4, 5, 6 ]
    }

    sum(1, 2, 0, 1, 2, 4, 5, 6);
    ```

    `Rest Parameters`에서 spread 연산자를 활용하여 첫번쨰 숫자인 1, 두번쨰 숫자인 2를 제외하고, 나머지 숫자를 쭈르륵 적용해서 출력해줍니다.

    ### spread 연산자를 활용하여 concat과 같은 기능 사용하기!

    먼저, `concat`이 무엇인지 간략하게 아래 코드로 설명해보겠습니다.

    ```jsx
    // Array Concat (두배열을 더하는 것)
    const fruits1 = ['🍏', '🥝'];
    const fruits2 = ['🍓', '🍌'];
    let arr = fruits1.concat(fruits2);

    console.log(arr); // ["🍏", "🥝", "🍓", "🍌"]
    ```

    위의 코드와 동일한 결과를 `spread 연산자`를 활용해 출력

    ```jsx
    // Spread 연산자 활용
    const fruits1 = ['🍏', '🥝'];
    const fruits2 = ['🍓', '🍌'];

    let arr = [...fruits1, ...fruits2];
    console.log(arr); // ["🍏", "🥝", "🍓", "🍌"]
    ```

    ### spread 연산자 Object에서 활용

    ```jsx
    // Object
    const ellie = {
      name: 'Ellie',
      age: 20,
      home: {
        address: 'home',
      },
    }; // home 같은 경우는 shallow copy가 일어난다.

    const updated = {
      ...ellie,
      job: 's/w engineer',
    };
    console.log(ellie); // update가 된 것이기에 기존의 ellie는 변동이 없습니다. { name: 'Ellie', age: 20, home: { adress: "home" } }
    console.log(updated); // { name: 'Ellie', age: 20, home: { adress: "home" }, job: 's/w engineer' }
    ```

  - 템플릿 문자열

    # Template literals

    `템플릿 리터럴`은 내장된 표현식을 허용하는 문자열 리터럴입니다.

    1. 표현식/문자열 삽입
    2. 여러 줄 문자열
    3. 문자열 형식화
    4. 문자열 태깅
       `템플릿 리터럴`은 위와 같은 기능을 제공합니다.
       `템플릿 리터럴`은 런타임 시점에서 일반 자바스크립트 문자열로 처리/변환 됩니다.
       Front-End에서는 HTML을 데이터와 결합해서 DOM을 다시 그려야하는 일이 빈번하기 떄문에, 템플릿을 좀 더 쉽게 편집하고 작성해야 할 필요가 있어, 이러한 기능이 추가되었습니다.

    ***

    ### Expression interpolation (표현식 삽입법)

    ES6 이전에는 아래와 같이 일반 문자열 안에 직접 삽입했습니다.

    ```jsx
    var i = 20;
    var j = 5;
    var c = "JS";
    var str = "저는 " + (i + j) + "살이고" + k + "를 좋아합니다.
    console.log(str); // 저는 25살이고 JS를 좋아합니다.
    ```

    템플릿 리터럴이 적용된 시점에서는 아래와 같이 작성할 수 있다.

    ```jsx
    let i = 20;
    let j = 5;
    let c = 'JS';
    let str = `저는 ${i + j}이고 ${c}를 좋아합니다.`;
    console.log(str); // 저는 25살이고 JS를 좋아합니다.
    ```

    ```(백틱)`을 활용하여, `+ 연산자`를 사용할 때보다 가독성이 좋은 코드를 사용할 수 있습니다.

    ***

    ### Tagged templates

    템플릿 리터럴의 발전된 형태로 하나의 Tagged templates이 있습니다. 태그를 사용하여 템플릿 리터럴을 함수로 Parsing 할 수 있습니다.
    아래 코드는 기본 함수와 동일한 태그 함수입니다.

    ```jsx
    let person = 'Lee';
    let age = 28;

    let tag = function (strings, personExp, ageExp) {
      let str0 = strings[0];
      let str1 = strings[1];
      console.log('str0 : ' + str0);
      console.log('str1 : ' + str1);

      let ageStr;
      if (ageExp > 99) ageStr = 'centenaian';
      else ageStr = 'youngster';

      return str0 + personExp + str1 + ageStr; // 이 함수 내에서 template literal 반환 가능
    };
    let output = tag`that ${person} is a ${age}`;
    console.log(output);
    ```

    태그 함수의 첫 번째 인수는 문자열 값의 배열을 포함합니다. 나머지 인수는 표현식과 관련됩니다. 이 첫 번째 인수, 즉 문자열 값의 배열은 표현식을 기준으로 split이 됩니다.

    ```jsx
    let myTag = function(strings, a, b, c) {
    	console.log(`문자열 배열 길이 : ${strings.length}`; // 4
    	for(let i = 0; i < strings.length; i+=1) {
    		console.log(`문자열 요쇼 [${i}]: ${strings[i]}`);
    	}
    	console.log(a);
    	console.log(b);
    	console.log(c);
    }
    let html = 5;
    let css = 3;
    let js = 'es10';
    let string = myTag`HTML${html}, CSS${css}, JavaScript ${js}`;
    ```

    Tagged templates는 데이터 별로 상황(조건)이 다른 경우 유용하게 쓰일 수 있습니다.

    ```jsx
    const ramenList = [
      {
        brand: '농심',
        items: ['신라면', '짜파게티', '참치마요', '둥지냉면'],
      },
      {
        brand: '삼양',
        items: ['삼양라면', '불닭볶음면'],
      },
      {
        brand: '오뚜기',
        itmes: [],
      },
    ];

    console.log(`구매가능한 ${ramenList[0].brand}의 라면 : ${ramenList[0].items}`);
    //구매가능한 농심의 라면 : 신라면,짜파게티,참치마요,둥지냉면
    console.log(`구매가능한 ${ramenList[1].brand}의 라면 : ${ramenList[1].items}`);
    //구매가능한 삼양의 라면 : 삼양라면,불닭볶음면
    console.log(`구매가능한 ${ramenList[2].brand}의 라면 : ${ramenList[2].items}`);
    //구매가능한 오뚜기의 라면 : undefined
    ```

    위와 같이 ramenList 데이터가 들어오는 경우, 오뚜기의 라면 데이터는 아직 추가가 안되어 있고, 그 결과 undefined라는 결과가 나왔습니다. 이런 경우에 tagged templates로 해결할 수 있다.

    ```jsx
    const ramenList = [
      {
        brand: '농심',
        items: ['신라면', '짜파게티', '참치마요', '둥지냉면'],
      },
      {
        brand: '삼양',
        items: ['삼양라면', '불닭볶음면'],
      },
      {
        brand: '오뚜기',
        itmes: [],
      },
    ];

    function fn(strings, brand, items) {
      let str;
      if (undefined === items) {
        str = brand + '의 라면은 재고가 없습니다!';
      } else {
        str = strings[0] + brand + strings[1] + items;
      }
      return str;
    }

    console.log(fn`구매가능한 ${ramenList[0].brand}의 라면 : ${ramenList[0].items}`);
    //구매가능한 농심의 라면 : 신라면,짜파게티,참치마요,둥지냉면
    console.log(fn`구매가능한 ${ramenList[1].brand}의 라면 : ${ramenList[1].items}`);
    //구매가능한 삼양의 라면 : 삼양라면,불닭볶음면
    console.log(fn`구매가능한 ${ramenList[2].brand}의 라면 : ${ramenList[2].items}`);
    //오뚜기의 라면은 재고가 없습니다!
    ```

    ***

    ### Multi-line strings

    템플릿 리터럴을 사용하면 여러 줄의 문자열도 나눠서 작성할 필요가 없습니다.

    ```jsx
    console.log("string text line 1\n + "string text line 2");
    // string text line 1
    // string text line 2
    ```

    템플릿 리터럴은 리터럴 안에서 개행을 해주면 됩니다.

    ```jsx
    //템플릿 리터럴
    console.log(`string text line 1
    string text line 2`);
    ```

    각 상황에 따라 편한 방식을 이용!

    ***

    ### Nesting templates (중첩 템플릿)

    특정 조건을 만족하는 경우마다 다른 문자열을 변수에 저장하고 싶을 때, 템플릿을 중첩해서 작성하는 것이 가독성이 더 좋을 때가 있습니다. 아래 예시 코드들로 비교해 보겠습니다.

    ```jsx
    // ES5
    var classes = 'header';
    classes += isLargeScreen() ? `` : item.isCollapsed ? ' icon-expander' : 'icon-collapser';
    ```

    ```jsx
    // ES6, Not use nesting templates
    const classes = `header ${
      isLargeScreen() ? `` : item.isCollapesd ? 'icon-expander' : 'icon-collapser'
    }`;
    ㅌㅈ;
    ```

    ```jsx
    // ES6, Used nesting templates
    const classes = `header ${
      isLargeScreen() ? `` : `icon-${item.isCollapsed ? 'expander' : 'collapser'}`
    }`;
    ```

    ***

    ### Raw strings (원래 문자열)

    Raw string은 이스케이프 문자를 해석하지 않은 일반 문자열입니다.
    String.raw 태그함수를 사용하면 템플릿 문자열을 입력한 대로 출력할 수 있습니다.

    ```jsx
    let s = String.raw`xy\n${1 + 1}z`;
    console.log(s); //xy\n2z
    ```

    태그 함수를 만들어 원래의 문자열을 반환하려면 첫 번쨰 인자의 raw 프로퍼티를 사용하면 됩니다.

    ```jsx
    let tag = function (strings) {
      return strings.raw[0];
    };

    let str = tag`Hello\nWorld.`;
    console.log(str); // Hello\nWorld.
    ```

  - 비구조 할당

    # 비구조화 할당(Destructuring Assignment)

    비구조화 할당이란?
    배열이나 객체의 속성 혹은 값을 해체하여 그 값을 변수에 각각 담아 사용하는 자바스크립트 표현식이다.
    각 배열과 객체의 비구조화 할당에 대해 하나씩 알아가보자!

    ***

    ### 비구조화를 사용하지 않았을 경우!

    ```jsx
    const colors = [green, yellow, pink];
    const green = colors[0];
    const yellow = colors[1];
    const pink = colors[2];
    ```

    ### 비구조화를 사용했을 경우!

    ```jsx
    //비구조화 할당 문법
    const [green, yellow, pink] = ['green', 'yellow', 'green'];

    // green => 'green'
    // yellow => 'yellow'
    // pink => 'pink'
    ```

    둘의 차이점을 봐봅시다!
    비구조화 할당을 사용하지 않으면 배열의 인덱스를 활용하여 우리가 원하는 변수에 할당을 해주어야 했습니다.
    비구조화 할당을 사용했을 경우!
    좌측에는 변수명 집합, 우측에는 해당 변수에 할당할 배열만 넣어주면 알아서 우리가 원하는대로 할당이 되는 것을 확인할 수 있습니다.

    ***

    ### 선언에서 분리한 할당 및 변수 값 교환

    ```jsx
    // 선언에서 분리한 할당
    const colorList = ['red', 'yellow', 'green'];
    let red, yellow, green;

    [red, yellow, green] = colorList;

    // 변수 값 교환
    let a = 1;
    let b = 3;

    [a, b] = [b, a];
    console.log(a); // 3
    console.log(b); // 1
    ```

    기존에는 temp라는 임시변수를 통해 swap을 했으나, 비구조화 할당을 통해 그 임시 변수가 필요하지 않고 위 예제처럼 서로 교환이 가능합니다.

    ***

    ### 기본 값 할당

    ```jsx
    // 기본 값 할당 X
    const [a, b, c] = [1, 2];
    console.log(a, b, c); // 1 2 undefined
    ```

    변수 집합의 길이보다 우측의 할당하려는 배열의 길이가 길 경우에는 아무런 상관 없지만 위의 코드와 같이 우측의 할당하려는 배열의 길이가 짧을 경우에는 undefined를 출력하게 된다.
    이러한 undefined를 방지하기 위해서 아래와 같은 방법을 사용할 수 있다.

    ```jsx
    // 기본값 할당 O
    const [a = 1, b = 2, c = 3] = [4, 5];
    console.log(a, b, c); // 4, 5, 3
    ```

    기본값을 할당할 경우, 비구조화 할당을 하려는 값이 undefined일 때 기본값을 대신 사용하여 할당합니다. 그래서 위 예제에서 기본 값을 할당했을 경우, c변수만 기본값이 주입되는 것을 확인할 수 있습니다.

    ***

    ### 원래의 key 대신 다른 변수명 사용하기! (ft. 기본값 할당)

    ```jsx
    // 새로운 변수명 할당과, 기본값 할당의 동시 사용
    const { a: aa = 4, b: bb = 5, c: cc = 6 } = { a: 1, b: 2 };
    console.log(aa); // 1
    console.log(bb); // 2
    console.log(cc); // 6
    ```

    객체 비구조화는 동일한 key 값을 통해 할당된다고 설명을 하였는데, 할당을 받고나서 새롭게 사용할 변수명을 콜론(;)을 통해 변경이 가능하다.
    그리고 동시에 기본값 할당 역시 사용할 수 있다.

    ***

    ### 변수에 객체의 나머지 값들 할당하기 (ft. 객체 결합 / 합치기 / 깊은 복사)

    - 나머지 매개 변수 및 확산 연산자 (Rest parameter & Spread operator) 라고도 한다.

    ```jsx
    // 객체의 나머지 값 할당!
    const { a, ...b } = { a : 1, b: 2, c: 3};
    console.log(a); // 1
    console.log(b); // {b : 2, c : 3}

    // 객체의 결합
    const obj1 = {a : 1, b : 2, c : 3};
    const obj2 = {c : 4, d : 5, e : 6};
    const obj3 = {...obj1, ...obj2};

    // 객체의 복사
    const obj1 = {a : 1, b : 2, c : 3};
    const obj2 = {
    	...obj1,
    	c: 4
    	d: 5
    }
    console.log(obj3); // {a : 1, b : 2, c : 4, d : 5};
    ```

    **✅ 참고**
    [구조 분해 할당 - JavaScript | MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
    [[ES6+] 배열 및 객체의 비구조화 할당- Destructuring Assignment (ft. 나머지 매개 변수 및 확산 연산자 - Rest parameter and Spread operator)](https://mine-it-record.tistory.com/466)

- 동기 / 비동기

  ### 동기 / 비동기

  ```jsx
  // JavaScript is synchronous
  // Execute the code block in order after hoisting(호이스팅 된 이후부터 코드가 동기적으로 실행)
  // hoisting: var, function declaration(함수 선언, var같은 경우 코드 맨위로 올라감)
  console.log('1');
  console.log('2');
  console.log('3');
  // 1 => 2 => 3 (동기적으로 순서맞게 출력)

  console.log('1');
  setTimeout(() => {
    console.log('2');
  }, 1000); // 1초 후에 function 을 다시 불러줘(call back)
  console.log('3');
  // 1 => 3 => 2 (비동기적으로 출력 setTimeout은 대표적인 Browser API)
  ```

  1. Synchronous callback

  ```jsx
  console.log('1');
  setTimeout(() => {
    console.log('2');
  }, 1000); // 1초 후에 function 을 다시 불러줘(call back)
  console.log('3');

  // 동기적 콜백
  function printImmediately(print) {
    print();
  }

  printImmediately(() => console.log('hello'));

  // 1 => 3 => hello => 2

  // 실제 작동과정

  // 동기적 콜백 (함수 선언문이므로 제일 위로 호이스팅)
  function printImmediately(print) {
    print();
  }

  console.log('1');
  setTimeout(() => {
    console.log('2');
  }, 1000); // 1초 후에 function 을 다시 불러줘(call back)
  console.log('3');

  printImmediately(() => console.log('hello'));
  ```

  1. Asynchronous callback (위에 코드에 이어서 작성했다고 가정)

     똑같이 호이스팅이 되지만, 비동기 콜백이기에 2초후에 출력되는거임.

  ```jsx
  // 비동기 콜백
  function printWithDelay(print, timeout) {
    setTimeout(print, timeout);
  }
  printWithDelay(() => console.log('async callback'), 2000);

  // 1 => 3 => hello => 2 => async callback
  ```

  ***

  - 콜백함수 + 중요한 함수의 불변성 정리

    # 콜백함수란?

    콜백함수 정의?

    1. 다른 코드의 인수로서 넘겨주는 실행 가능한 코드

    2. 어떤 이벤트에 의해 호출되어지는 함수
       즉, 콜백함수는 특정 작업이 실행되고 난 뒤에 추가로 실행되는 함수를 의미합니다.

    ***

    ### 예제

    ```jsx
    // 콜백함수
    const add = (a, b) => a + b;
    const multiply = (a, b) => a * b;

    // 전달된 action은 콜백함수이다.
    // 전달된 당시에 함수를 바로 호출해서 반환된 값을 전달하는 것이 아닌
    // 함수를 가리키고 있는 함수의 reference(참조 값)이 전달된다.
    // 그래서 함수는 고차함수(calculator)안에서 필요한 순간(호출하고 싶을때) 호출이 나중에 콜백이됨
    function calculator(a, b, action) {
      let result = action(a, b);
      console.log(result);
      return result;
    }

    calculator(1, 2, add); // 3
    calculator(1, 2, multiply); // 2

    // 고차함수안에서 필요한 순간에 호출이 된다는 예시
    function calculator(a, b, action) {
      if (a < 0 || b < 0) {
        return; // (조건에 부합할시 계산하지 않음)
      }
      let result = action(a, b);
      console.log(result);
      return result;
    }

    calculator(-11, -2, add); // 호출이 안됨(조건문이 통과가 안되므로)
    calculator(-1, -2, multiply); // 호출이 안됨(조건문이 통과가 안되므로)
    ```

    ### **중요한 함수의 불변성 정리!**

    ```jsx
    function display(num) {
      num = 5;
      console.log(num);
    }
    const value = 4;
    display(value); // 5 출력
    console.log(value); // 4 출력

    // 원시 값은, 전달되거나 할당될떄 값에 의해서 복사가 됩니다.
    // 함수를 호출 할때, value = 4자체가 복사되어 함수에 전달되어집니다.
    // 복사된 4가 이제 함수 지역변수(num)에 할당이 될 것이고, 5가 출력이 됩니다.
    // 기존의 value에는 4가 유지됩니다. (위와 같이 작성하는 것은 좋은 코드가 아닙니다.)
    ```

    위의 코드 처럼 함수 내부에서 외부로부터 주어진 인자의 값을 변경하는 것은 좋지 않습니다.
    상태 변경이 필요한 경우에는, 새로운 상태를(오브젝트, 값) 만들어서 반환해야 합니다.
    원시 값 - 값에 의한 복사
    객체 값 - 참조에 의한 복사
    객체 일 경우에는 메모리 주소가 전달되므로, 결국에 동일한 오브젝트를 가리키므로, 큰 문제가 발생합니다.
    아래의 예시를 봐봅시다.

    ```jsx
    function displayObj(obj) {
      console.log(obj);
    }
    const yongmin = { name: 'yongmin' };
    displayObj(yongmin); // {name: 'yongmin'}
    ```

    원시 값일 때와 다르게, 객체 값은 참조에 의한 복사: 즉, 주소 값이 복사가 되는 동일한 오브젝트를 가리키므로 본래의 ellie 또한 변경이 된 것을 확인할 수 있습니다.

    ```jsx
    function displayObj(obj) {
      obj.name = 'Bob'; // 외부로 부터 주어진 인자(Object)를 내부에서 변경하는 것은 좋지않다.
      console.log(obj);
    }
    const ellie = { name: 'yongmin' };
    displayObj(yongmin); // {name: 'Bob'}
    console.log(yongmin); // {name: 'Bob'}
    ```

    **어떻게 해결할까?**

    1. 변경한다는 것을 정확하게 명시 (함수이름으로)
    2. `object literal`을 사용하여 변경해준다.

    ```jsx
    const yongmin = { name: 'yongmin' };
    changeName(yongmin);
    console.log(yongmin); // {name: 'Bob'}

    function changeName(obj) {
      // 1. 이름부터 변경하는 느낌을 주도록! 호출하는 사람이 헷갈리지 않도록
      return { ...obj, name: 'Bob' }; // {name: 'Bob'}
      // 반활할떄는 새로운 오브젝트 만들기!
    }
    ```

  - Promise

    # Promise

    Promise는 내가 무겁고 오래걸리는 일이 있다면 코드 내부에서 조금 더 비동기적으로 처리하게 도움을 줍니다.
    Promise를 이용해서 언제끝날지는 몰라도, 일이 끝나면 원하는 일을 수행할 수 있도록 약속을 해줍니다.
    내가 일이 끝난 후 등록할 수 있는 .then
    에러가 발생했을 때 잡을 수 있는 .catch
    최종적으로 모든 일이 끝났을때 사용할 수 있는 .finally
    이렇게 3종류가 있습니다.

    ```jsx
    function runInDelay(seconds) {
      // 프로미스 오브젝트를 리턴
      return new Promise((resolve, reject) => {
        if (!seconds || seconds < 0) {
          reject(new Error('Seconds가 0보다 작음'));
        }
        setTimeout(() => {
          resolve();
        }, seconds * 1000);
      });
    }

    runInDelay(2)
      .then(() => console.log('타이머 완료'))
      .catch(console.error)
      .finally(() => console.log('끝났다!'));

    // 타이머 완료 , 끝났다 순으로 호출이 되는 것을 확인!
    // 만약 2가 아닌 -1을 넣었다면 Seconds가 0보다 작음, 끝났다 이렇게 호출됨.

    // 아래 처럼 하는 것보다 위의 promise 코드가 깔금하다.
    try {
    	runInDelay(() => {
    		console.log('타이머 완료!')
    		}
    } catch (error) {}
    ```

    위의 방식이 promise를 만드는 방식이다.
    promise 객체를 만들을 때에는 new 연산자를 활용하여 만들어야 합니다.
    생성자 안에는(new Promise(이 부분을 의미)) promise를 만들 수 있는 콜백함수를 전달해야합니다. 콜백함수는 promise에 의해 호출이 되고, resolve(성공)시 호출할 것, reject(실패)시 호출할 것을 전달해주면 됩니다.

    ***

    ### Promise의 함수들!

    ```jsx
    function fetchEgg(chicken) {
      return Promise.resolve(`${chicken} => 🥚`);
    }
    fetchEgg('🐔') //
      .then((egg) => console.log(egg)); // 🐔 => 🥚
    ```

    위와 같이 Promise의 resolve 함수를 new 연산자를 사용하지 않고 바로 선언할 수 있다.
    Promise Chaining(.then 계속 사용)

    ```jsx
    function fetchEgg(chicken) {
      return Promise.resolve(`${chicken} => 🥚`);
    }

    function fryEgg(egg) {
      return Promise.resolve(`${egg} => 🍳`);
    }

    function getChicken() {
      return Promise.resolve(`🍀 => 🐓`);
    }

    getChicken() //
      .then((chicken) => fetchEgg(chicken))
      .then((egg) => fryEgg(egg))
      .then((friedEgg) => console.log(friedEgg));

    // 🍀 => 🐓 => 🥚 => 🍳
    // 먼저 치킨을 갖고와서, fetchEgg안에서 계란을 갖고오는 것 까지 성공,
    // 계란을 다시 fryEgg함수에 전달하여, 계란프라이를 들고와서 friedEgg를 호출함!
    ```

    중간에 .catch를 이용해서 에러 발생시 에러를 핸들링할 수 있다.

    ```jsx
    function fetchEgg(chicken) {
      return Promise.resolve(`${chicken} => 🥚`);
    }

    function fryEgg(egg) {
      return Promise.resolve(`${egg} => 🍳`);
    }

    function getChicken() {
      return Promise.reject(new Error('치킨 어디감?'));
      // return Promise.resolve(`🍀 => 🐓`);
    }

    getChicken() //
      .then((chicken) => fetchEgg(chicken))
      .then((egg) => fryEgg(egg))
      .then((friedEgg) => console.log(friedEgg))
      .catch((error) => console.log(error.name)); // Error
    ```

    에러의 원인만 제공받는 것이 아닌, 에러를 실제로 나타난 이유를 알고, 바로 다른 값을 리턴하여 promise chain을 유지할 수 도있습니다.

    ```jsx
    function fetchEgg(chicken) {
      return Promise.resolve(`${chicken} => 🥚`);
    }

    function fryEgg(egg) {
      return Promise.resolve(`${egg} => 🍳`);
    }

    function getChicken() {
      return Promise.reject(new Error('치킨 어디감?'));
      // return Promise.resolve(`🍀 => 🐓`);
    }

    getChicken() //
      .catch((error) => {
        console.log(error.name);
        return '🐣';
      })
      .then((chicken) => fetchEgg(chicken))
      .then((egg) => fryEgg(egg))
      .then((friedEgg) => console.log(friedEgg));

    // Error
    // 🐣 => 🥚 => 🍳
    ```

    코드를 조금더 깔끔하게 작성할 수 있다. ( 더 이해하기 쉽다 )

    ```jsx
    getChicken() //
      .catch((error) => '🐣') // 치킨을 가져오는데 실패하면 병아리를 갖고온다.
      .then(fetchEgg) // 이 병아리를 이용해 계란 갖고오고
      .then(fryEgg) // 계란을 프라이한 후
      .then(console.log); // 출력!
    ```

    catch의 위치에 따라서 더 의미있는 코딩을 할 수 있습니다.

    ***

    ### Promise의 병렬처리 (여러 함수들)

    아래는 바나나와, 사과를 가져오는 코드입니다. 오렌지를 가져올 수 없기에 error 또한 포함됩니다.

    ```jsx
    function getBanana() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve('🍌');
        }, 1000);
      });
    }

    function getApple() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve('🍏');
        }, 3000);
      });
    }

    function getOrange() {
      return Promise.reject(new Error('no orange'));
    }

    // 바나나와 사과를 같이 가지고 오기! (배열에 담기)
    getBanana() //
      .then((banana) =>
        getApple() //
          .then((apple) => {
            return [banana, apple];
          })
          .then(console.log),
      );
    ```

    ```jsx
    function getBanana() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve('🍌');
        }, 1000);
      });
    }

    function getApple() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve('🍏');
        }, 3000);
      });
    }

    function getOrange() {
      return Promise.reject(new Error('no orange'));
    }

    // 바나나와 사과를 같이 가지고 오기! (배열에 담기)
    getBanana() //
      .then((banana) =>
        getApple() //
          .then((apple) => {
            return [banana, apple];
          })
          .then(console.log),
      );

    // 4초 후에 출력됨. (순차적으로 promise를 진행하니 바나나의 시간 1초, 사과의 시간 3초 총 4초 걸림)

    // 위를 해결하기위해
    // Promise.all 병렬적으로 한번에 모든 Promise를 처리
    Promise.all([getBanana(), getApple()]) // 바나나 사과를 같이 시작, 즉 사과가 끝나는 3초떄 출력 1초 단축
      .then((fruits) => console.log('all', fruits));

    // Promise.race 주어진 Promise 중에 가장 빨리 수행된 것이 이김!
    // 제일 빨리 수행된 결과값만 출력합니다.
    Promise.race([getBanana(), getApple()]).then(
      (fruit) => console.log('race', fruit), // race 🍌 (1초 후에 출력)
    );

    // Promise.all Error 버전

    // 성공을 해야지 then으로 넘어가는데 orange에서 에러가 발생되었기에 아무런 결과값이 출력되지 않습니다.
    Promise.all([getBanana(), getApple(), getOrange()]) // Orange가 없으므로 에러
      .then((fruits) => console.log('all-error', fruits))
      .catch(console.log);

    // 위의 문제를 해결하기 위해
    // Promise.allSettled()
    Promise.allSettled([getBanana(), getApple(), getOrange()]) // Orange가 없으므로 에러
      .then((fruits) => console.log('all-error', fruits))
      .catch(console.log);
    ```

    ![스크린샷 2023-04-05 오전 12.34.59.png](Chapter%202%20%E1%84%91%E1%85%A5%E1%84%87%E1%85%B3%E1%86%AF%E1%84%85%E1%85%B5%E1%84%89%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%B5%E1%86%B7%E1%84%92%E1%85%AA%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8C%E1%85%A1%E1%84%87%E1%85%A1%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%B8%E1%84%90%E1%85%B3%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20%2010241ce33d044a88917e60d6cb788186/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-04-05_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%258C%25E1%2585%25A5%25E1%2586%25AB_12.34.59.png)

  - async, await

    # async, await

    Promise의 장점은 콜백 함수를 사용하지 않고, 조금 더 사용할 때 깔끔하게 사용할 수 있는 점이 있다. .then을 연속해서 사용하게 되면, 한번에 코드를 이해하기 어렵습니다.
    async await 같은 경우는 비동기적인 코드를 동기적인 형태로(절차적) 코드를 작성 할 수 있습니다.
    먼저 Promise로 작성된 코드를 보겠습니다.

    ```jsx
    function getBanana() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve('🍌');
        }, 1000);
      });
    }

    function getApple() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve('🍏');
        }, 3000);
      });
    }

    function getOrange() {
      return Promise.reject(new Error('no orange'));
    }

    // 바나나와 사과를 같이 가지고 오기! (배열에 담기)
    function fetchFruits() {
      return getBanana() //
        .then((banana) =>
          getApple() // 중첩된 콜백 보기 나쁨... (방지하기위해 async/await)
            .then((apple) => [banana, apple]),
        );
    }

    fetchFruits() //
      .then((fruits) => console.log(fruits)); // 4초 후에 ['🍌', '🍏'] 출력
    ```

    이 코드를 async await 으로 변경해보겠습니다.

    ```jsx
    // function 앞에 async를 붙여 비동기 함수임을 나타냄
    // 비동기처럼 행동을 하고, Promise가 리턴이 됨 (함수 내부를 동기적으로 변경가능)
    async function fetchFruits() {
      // 바나나 라는 값 자체를 기다렸다가 Promise니 await을 통해 banana에 할당
      // 그냥 getBanana()만 한다면 Promise값을 할당하므로 await을 해주어야함.
      const banana = await getBanana();
      const apple = await getApple();
      return [banana, apple];
    }
    // getBanana()와 getApple()은 Promise를 리턴하는데 .then으로 엮는 것이 아니라
    // async를 활용하여 비동기 코드를, 동기적으로 작성할 수 있습니다.
    // 단, Promise를 리턴하는 함수를 호출할 때는 await이라는 키워드를 써서 기다렸다가 Promise값이 resolve가 되면 그 값을 변수에 기다렸다가(await) 할당합니다.
    // 그냥 값을 return할지라도, async라는 키워드가 붙여졌기에 함수의 값은 배열을 resolve하는 promise가 만들어집니다.

    fetchFruits() //
      .then((fruits) => console.log(fruits)); // 4초 후에 ['🍌', '🍏'] 출력
    ```

    아까 Promise에서 작성한 코드를 다시 async/await으로 변경해보자!

    ```jsx
    function fetchEgg(chicken) {
      return Promise.resolve(`${chicken} => 🥚`);
    }

    function fryEgg(egg) {
      return Promise.resolve(`${egg} => 🍳`);
    }

    function getChicken() {
      return Promise.reject(new Error('can not find 🐓'));
    }

    getChicken()
      .catch(() => '🐔')
      .then((chicken) => fetchEgg(chicken))
      .then((egg) => fryEgg(egg))
      .then((meal) => console.log(meal))
      .catch((error) => console.log(error));
    ```

    async/await으로 변경!

    ```jsx
    // 1. 함수 표현
    async function makeFriedEgg() {
      let chicken;
      // await이 있으므로, getChicken에서 반환된 promise 객체의 성공여부가 결정되어야
      // try 구문이 끝납니다. 실패시 catch 구문 실행!
      try {
        chicken = await getChicken(); // 치킨을 가져오는 것을 시도!
      } catch {
        chicken = '🐔';
      }
      const egg = await fetchEgg(chicken);
      return fryEgg(egg); // Promise 객체 그대로를 반환합니다.
    }

    makeFriedEgg(); // Promise 🐔 => 🥚 => 🍳

    // 2. 화살표 함수
    const makeFriedEgg = async () => {
      let chicken;
      try {
        chicken = await getChicken(); // 치킨을 가져오는 것을 시도!
      } catch {
        chicken = '🐔';
      }
      const egg = await fetchEgg(chicken);
      return fryEgg(egg);
    };

    makeFriedEgg(); // Promise 🐔 => 🥚 => 🍳
    ```

    출력시 promise 값이 아닌, 일반 값으로 전달받고 싶으면 어떻게 해야하는지 궁금해서 찾아봤다.

    ```jsx
    makeFriedEgg(); // Promise 객체 리턴 🐔 => 🥚 => 🍳
    // 일반 값으로 리턴받고 싶으면 .then을 활용해야한다. .catch를 활용하거나
    makeFriedEgg().then(console.log); // 🐔 => 🥚 => 🍳
    ```

    에러 발생시에는 `.catch(console.error);` 이런식으로 활용해도 된다!!

    1. Promise Chaning 유의사항!

    ```jsx
    function fetchEgg(chicken) {
      return Promise.resolve(`${chicken} => 🥚`);
    }

    function fryEgg(egg) {
      return Promise.resolve(`${egg} => 🍳`);
    }

    function getChicken() {
      return Promise.reject(new Error('can not find 🐓'));
    }

    // 1. 함수 만들기
    function makeFriedEgg() {
      return getChicken()
        .catch(() => '🐔')
        .then(fetchEgg)
        .then(fryEgg)
        .then(console.log);
    }

    makeFriedEgg().then(console.log); // undefined 출력
    ```

    ```jsx
    // then 체인을 쓸때 return getChicken()을 통해 promise를 리턴하는 경우
    // 아래에서 console.log를 출력했을때 계란이 전달되면, 계란을 출력하고 아무런 것도 리턴하지 않기 때문에
    // 값을 리턴하지 않고, console.log에만 출력함. // 아무것도 리턴하지 않기때문에
    ```

    이를 해결하는 방법? 결과값을 받아와서 마지막에 결과값을 리턴해주면 됩니다.

    ```jsx
    function makeFriedEgg() {
      return getChicken()
        .catch(() => '🐔')
        .then(fetchEgg)
        .then(fryEgg)
        .then((result) => {
          console.log(result);
          return result; // 🐔 => 🥚 => 🍳
        });
    }
    ```

    ### **async/await와 promise.then/catch**

    - `async/await`을 사용하면 `await`가 대기를 처리해주기 때문에 `.then`이 거의 필요하지 않다. 또한, `.catch` 대신 일반 `try/catch`를 사용할 수 있다는 장점도 있다. 항상 그러한 것은 아니지만, `promise.then`을 사용하는 것보다 `async/await`를 사용하는 것이 대개는 더 편리하다
    - 그런데 문법 제약 때문에 `async`함수 바깥의 최상위 레벨 코드에선 `await`를 사용할 수 없다. 그렇기 때문에 관행처럼 `.then/catch`를 추가해 최종 결과나 처리되지 못한 에러를 다룬다.

## 📢 학습 후기

---

- 이번 주차 워크북을 해결해보면서 어땠는지 회고해봅시다.
  동기/비동기에 대해서 다시 한번 복습할 수 있는 계기가 되어서 좋았다.
  특히, Promise와 async/await의 등장 배경과, 작동 원리에 대해서 다시 복습할 수 있었다.
  Promise 문법에 대해서 복습하게되어서 좋았다.
- 핵심 키워드에 대해 완벽하게 이해했는지? 혹시 이해가 안 되는 부분은 뭐였는지?

<aside>
📢

</aside>

## ⚠️ 스터디 진행 방법

---

1. 스터디를 진행하기 전, 워크북 내용들을 모두 채우고 스터디에서는 서로 모르는 내용들을 공유해주세요.
2. 미션은 워크북 내용들을 모두 완료하고 나서 스터디 전/후로 진행해보세요.
3. 다음주 스터디를 진행하기 전, 지난주 미션을 서로 공유해서 상호 피드백을 진행하시면 됩니다.

## ✅ 실습 체크리스트

---

- [x] JavaScript 실습 사이트에서 위 키워드에 있는 모든 개념들을 학습하세요.
      [JavaScript ES6](https://www.w3schools.com/js/js_es6.asp)

## 🔥 미션

---

1. 저번 챕터에 진행한 미션에 JavaScript를 적용해서 조금더 동적인 페이지를 만들어보아요!

   1. 버튼을 누르면 게시물이 사라진다던가…
   2. 스크롤이 가로로 된다던가…
   3. 버튼을 누르면 게시물이 복제된다던가…

   ### 내가 구현한 JS 동적 기능!

   ***

   1. Auto type effect + speed control (input요소를 제어해서 타이핑하는 효과 집어넣기)
   2. Left Navbar 넷플릭스의 주요 색상인 (빨강색, 흰색, 검정색을 활용하여 Navbar를 만듬!)
   3. Hidden Toggle Search 구현! (나름의 디자인 포함…)

[화면 기록 2023-04-05 오후 2.27.35.mov](Chapter%202%20%E1%84%91%E1%85%A5%E1%84%87%E1%85%B3%E1%86%AF%E1%84%85%E1%85%B5%E1%84%89%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%B5%E1%86%B7%E1%84%92%E1%85%AA%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8C%E1%85%A1%E1%84%87%E1%85%A1%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%B8%E1%84%90%E1%85%B3%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20%2010241ce33d044a88917e60d6cb788186/%25E1%2584%2592%25E1%2585%25AA%25E1%2584%2586%25E1%2585%25A7%25E1%2586%25AB_%25E1%2584%2580%25E1%2585%25B5%25E1%2584%2585%25E1%2585%25A9%25E1%2586%25A8_2023-04-05_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_2.27.35.mov)

## ⚡ 트러블 슈팅

---

<aside>
💡 실습하면서 생긴 문제들에 대해서, **이슈 - 문제 - 해결** 순서로 작성해주세요.

</aside>

<aside>
💡 스스로 해결하기 어렵다면? 스터디원들에게 도움을 요청하거나 **너디너리의 지식IN 채널에 질문**해보세요!

</aside>

- ⚡이슈 No.1 (예시, 서식만 복사하시고 지워주세요.)
  **`이슈`**
  👉 앱 실행 중에 노래 다음 버튼을 누르니까 앱이 종료되었다.
  **`문제`**
  👉 노래클래스의 데이터리스트의 Size를 넘어서 NullPointException이 발생하여 앱이 종료된 것이었다.
  **`해결`**
  👉 노래 다음 버튼을 눌렀을 때 데이터리스트의 Size를 검사해 Size보다 넘어가려고 하면 다음으로 넘어가는 메서드를 실행시키지 않고, 첫 노래로 돌아가게끔 해결
  **`참고레퍼런스`**
  - 링크

## 🤔 참고 자료

---

[https://velog.io/@khy226/동기-비동기란-Promise-asyncawait-개념](https://velog.io/@khy226/동기-비동기란-Promise-asyncawait-개념)

[동기, 비동기란? (+Promise, async/await 개념)](https://velog.io/@khy226/동기-비동기란-Promise-asyncawait-개념)

[https://www.youtube.com/watch?v=s1vpVCrT8f4](https://www.youtube.com/watch?v=s1vpVCrT8f4)

[JavaScript ES6](https://www.w3schools.com/js/js_es6.asp)

---

Copyright © 2023 컴공선배 All rights reserved.
