---
emoji: 📔
title: UMC 3주차 워크북
date: '2023-04-10 00:00:00'
author: dydals3440
tags: UMC UMC3주차 UMC-4기
categories: UMC
---

# Chapter 3. 리액트 기초

## 🎯 핵심 키워드

---

- MPA / SPA
  # MPA
  Multi Page Application은 여러 개의 페이지로 구성된 Application을 의미합니다.
  MPA는 새로운 페이지를 요청할 떄마다 정적 리소스가 다운로드 되고, 그에 맞춰 전체 페이지를 다시 렌더링합니다! 인터넷 주소창에 주소를 입력하거나, 링크를 클릭하는 등 사용자가 어떠한 요청을 한다면 그에 맞는 html, 이미지 등의 파일들이 전부 다운로드 되고 다시 렌더링 됩니다.
  우리는 이래서 MPA를 SSR(Server Side Rendering) 방식으로 렌더링 한다고 말합니다.
  ![스크린샷 2023-04-05 오전 9.30.00.png](%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-04-05_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%258C%25E1%2585%25A5%25E1%2586%25AB_9.30.00.png)
  MPA는 Client가 Server에게 Initial Request시 HTML을 받습니다.
  Page가 마운트 될떄마다(리로드) post방식으로 다시 HTML을 받는 것을 확인할 수 있습니다.
  ### MPA 장점!
  - SEO 검색 엔진 최적화 관점에서 유리하다!
    - MPA는 완성된 형태의 HTML파일을 서버로부터 전달받는다. 따라서 검색엔진이 페이지를 크롤링하기에 적합하다.
  - 빠른 초기 로딩
    - 화면을 렌더링하기 위한 필수적 요소를 먼저 가져오기 떄문에 CSR보다 초기 로딩 속도가 빠릅니다.
  ### MPA 단점!
  - 새로운 페이지를 이동하면 화면이 깜빡인다. (불편한 사용자 경험)
    - 새로운 페이지를 요청할 떄마다 전체 페이지를 다시 렌더링 하기 때문입니다.
  - 프론트엔드와 백엔드가 밀접하게 연관되어 있다. (Tightly coupled!)
    - 프론트엔드와 백엔드가 서로 연관이 높아 개발이 복잡해질 수 있다.
  - 서버 부하 증가
    - 페이지를 요청할 떄 마다 페이지를 구성하는 모든 리소스 준비!
  ***
  # SPA
  Single Page Application은 한 개의 페이지로 구성된 Application을 의미합니다.
  SPA는 웹 애플리케이션에 필요한 모든 정적 리소스를 최초 한번에 다운로드합니다! 그 이후 새로운 페이지 요청이 있을 경우 페이지 갱신에 필요한 데이터만 전달받아 페이지를 갱신합니다. 어떤 링크를 클릭한다고 해서 그에 관련된 모든 파일을 다운받는게 아니라, 필요한 정보만 받아서 그 정보를 기준으로 업데이트 될 뿐이다.
  우리는 이래서 SPA를 CSR(Client Side Rendering) 방식으로 렌더링 한다고 말합니다.
  ![스크린샷 2023-04-05 오전 9.32.24.png](%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-04-05_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%258C%25E1%2585%25A5%25E1%2586%25AB_9.32.24.png)
  SPA는 클라이언트가 서버에게 Initial Request를 하면 HTML을 받습니다.
  다만, 추가적인 요청사항이 있으면 AJAX 통신을 통해 JSON 데이터를 받아 업데이트만 진행합니다!
  ### SPA 장점!
  - User Experience 👍
    - 전체 페이지를 업데이트 할 필요가 없고 변경된 부분만 업데이트하기에 효율이 좋다.
    - 전체 페이지를 업로드하면서 발생하는 ‘깜박’거림이 없다.
    - 페이지의 일부분만 변경되므로 App의 반응이 빠르다
  - 개발하기 쉽다.
    - 서버의 사용없이 개발 가능!
    - 크롬 디버깅 Easy
  - 로컬 데이터를 효과적으로 캐시(cache) 할 수 있다.
    - SPA의 Application은 서버에게 정적 리소스를 한번만 요청한다.
  - 빠른 속도 및 서버 부하 감소
    - 변경된 부분과 관련된 데이터만 오가기 때문에 서버의 부담을 줄임
      Cache란 데이터나 값을 미리 복사해 놓는 임시 장소이다.
      받은 데이터를 전부 저장한 후 이 데이터는 오프라인에서도 사용이 가능합니다.
      Cache에 데이터를 미리 복사해 놓으면 계산이나 별도의 접근 시간 없이 더 빠른 속도로 데이터에 접근할 수 있다.
  ### SPA 단점!
  - 초기 구동 속도가 느리다.
    - 초기의 웹 애플리케이션에 필요한 정적 리소스를 한번에 다 다운 받기 떄문에
  - SEO 검색 엔진 최적화의 관점에서 매우 불리합니다.
    이를 해결하기 위해 SPA에서도 CSR이 아닌 SSR 방식을 적용하는 케이스가 있습니다.
  ***
  ### 그래서 어떤 방식으로 개발해야해?
  ![스크린샷 2023-04-05 오전 9.51.36.png](%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-04-05_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%258C%25E1%2585%25A5%25E1%2586%25AB_9.51.36.png)
  **"콘텐츠 중심"**
  - Single-Page Application를 만드려고 할 때 모든 부분을 Client Side Rendering 방식으로 구현해야 하는 것은 아니다.
  - 어플리케이션을 구성하는 부분에 따라 단순 정보 제공과 같은 부분은 초기 로딩 속도가 빠른 Server Side Randering으로, 동적인 변화가 필요한 부분은 초기에 모든 js 파일을 다운받는 Client Side Rendering으로 개발하는 것이 좋다.
    이런 CSR와 SSR의 장점만을 합쳐서 만들어진 리액트 프레임워크가 바로 Next.js이다. Next.js는 기본적으로 정적 페이지를 만들어주지만 동적인 데이터도 처리할 수 있게 해준다.
  ***
  ✅ 참고!
  [SPA vs. MPA](https://velog.io/@thms200/SPA-vs.-MPA)
  - [Which one you actually need-“Single Page Application or Multi Page Application”](https://medium.com/@shifat.jaman/which-one-you-actually-need-single-page-application-or-multi-page-application-c0976d45ed93)
  - [Single Page Application & Routing](https://poiemaweb.com/js-spa)
  - [아하 프론트 개발기(1) — SPA와 SSR의 장단점 그리고 Nuxt.js](https://medium.com/aha-official/%EC%95%84%ED%95%98-%ED%94%84%EB%A1%A0%ED%8A%B8-%EA%B0%9C%EB%B0%9C%EA%B8%B0-1-spa%EC%99%80-ssr%EC%9D%98-%EC%9E%A5%EB%8B%A8%EC%A0%90-%EA%B7%B8%EB%A6%AC%EA%B3%A0-nuxt-js-cafdc3ac2053)
  - [Single Page or Multi-Page Application: Which One is Better?](https://www.esds.co.in/blog/single-page-or-multi-page-application-which-one-is-better/#sthash.6EFtBMC0.dpbs)
  - [Single-page application vs. multiple-page application](https://medium.com/@NeotericEU/single-page-application-vs-multiple-page-application-2591588efe58)
- 컴포넌트

  - 클래스형 컴포넌트

    # 클래스형 컴포넌트

    이제는 잘 사용하지 않지만, 함수형 컴포넌트 + Hooks으로 못하는 작업이 있을 경우, 또는 이전에 만들어진 리액트 관련 라이브러리의 경우에 유지보수를 해야할 경우에 클래스형 컴포넌트를 사용하기도 합니다.

    ***

    ### 선언 방식

    ```jsx
    import React, { Component } from 'react';

    class App extends Component {
      render() {
        const text = 'Hi Yongmin';
        return <div>{text}</div>;
      }
    }

    export default App;
    ```

    클래스형 컴포넌트는 class 키워드가 필요하며, Component를 상속받아야 합니다.
    화면에 표시하기 위한 render() 메서드가 반드시 필요합니다.

    ***

    ### State 사용

    `constructor` 안에서 `this.state`를 통해 초기 값을 설정 가능하며, `constructor` 없이도 초기 값을 설정할 수 있습니다. 아래 코드에서 볼 수 있든 클래스형 컴포넌트의 `state은 객체 형식`입니다.

    ```jsx
    // with constructor
    constructor(props) {
    	super(props);
    	this.state = {
    		name: 'yongmin',
    		items: []
    	};
    }

    // without constructor
    class App extends Component {
    	state = {
    		name: 'yongmin',
    		items: []
    	}
    }
    ```

    `this.setState` 함수로 state의 값을 변경할 수 있습니다.

    ```jsx
    onClick={() => {
    	this.setState({ price: price + 100});
    }}
    ```

    ***

    ### Props 사용

    props는 컴포넌트의 속성을 설정할 떄 사용하는 요소입니다. 읽기 전용이여야 하며, 컴포넌트 자체의 props를 수정해서는 안됩니다. 모든 React 컴포넌트는 자신의 Props를 다룰 때 순수 함수처럼 동작해야 하며, 수정되는 것은 state만 수정되어야 합니다.

    ```jsx
    class App extends Component {
    	render() {
    		const {name, age} = this.props; // this.props로 불러옵니다.
    		return {
    			<div>
    				안녕 나는 {name}이고, {age}살이야.
    			</div>
    		)
    	}
    }
    ```

    ***

    ### Event Handling

    함수 선언시 화살표 함수로 바로 선언이 가능하며, 적용하기 위해서는 this를 붙여야합니다.

    ```jsx
    handleClick = e => { ... }

    render() {
    	return (
    		<>
    			<input type='button' onClick={this.handleClick}>버튼</input>
    		</>
    	)
    }
    ```

    ***

    ✅ 참고
    [https://soopiri.tistory.com/23](https://soopiri.tistory.com/23)

  - 함수형 컴포넌트

    # 함수형 컴포넌트

    클래스형 컴포넌트보다 선언하기 편합니다, 메모리 자원을 클래스형 컴포넌트보다 덜 사용하고, 빌드한 결과물의 크기 역시 클래스형 컴포넌트에 비해 작기 때문에 최근에는 함수형 컴포넌트를 사용합니다.

    ***

    ### 선언 방식

    ```jsx
    import React from 'react';

    const App = () => {
      const text = 'Hi yongmin';
      return <div>{text}</div>;
    };

    export default App;

    /* 클래스형 컴포넌트
    import React, { Component } from 'react';
    
    class App extends Component {
    	render() {
    		const text = 'Hi Yongmin'
    		return <div>{text}</div>
    	}
    }
    
    export default App;
    */
    ```

    함수 자체가 렌더 함수이기 떄문에 render() 메서드를 사용하지 않아도 되고, Component를 상속 받지 않아도 된다.

    ***

    ### State 사용

    함수형 컴포넌트에서는 useState로 state을 관리합니다.

    ```jsx
    const App = () => {
    	const [name, setName] = useState('Yongmin');
    	const onButtonClick = {() => {
    		setName('Yongmin Kim');
      }}
    }
    ```

    setState같은 경우는 state를 변경해주는 함수입니다. useState의 파라미터는 state의 초기값입니다.

    ***

    ### Props의 사용

    렌더 함수의 parameter로 props를 전달받아 사용합니다.

    ```jsx
    const App = ({name, age}) => {
    	return(
    		<div>
    			안녕? 난 {name}이고, age만큼 나이먹었어..
    		</div>
    }
    ```

    ***

    ### Event Handling

    const 함수 형태로 선언해야 하고, this가 필요없습니다.

    ```jsx
    const handleClick = () => { ... }

    return (
    	<>
    		<input type='button' onClick={handleClick}>버튼</input>
    	</>
    )

    /* 클래스형 컴포넌트
    handleClick = e => { ... }

    render() {
    	return (
    		<>
    			<input type='button' onClick={this.handleClcik}/>버튼</input>
    		</>
    	)
    }

    함수 선언시 arrow로 바로 선언 가능, 적용하기 위해선 this를 붙여야함!
    */
    ```

- JSX 문법

  # JSX 문법

  Components의 필수 요건은 첫 글자는 대문자로 함수를 만들어야 합니다. 반환하는 값 또한 JSX로 반환해주면 됩니다. JSX는 html과 매우 유사합니다.
  유의사항 3가지

  1. React에서는 태그를 반환할떄 하나의 태그만 반환해야 합니다. 다수의 태그를 반환하고 싶다면 부모태그로 감싸주어야 합니다.

     ```jsx
     // App.js
     import logo from './logo.svg';
     import './App.css';

     export default function App() {
       return (
         <>
           <h1>Hello!</h1>
         </>
       );
     }
     ```

  2. React에서 class를 활용하고 싶으면 className을 활용해야 합니다.

     ```jsx
     // App.js
     import logo from './logo.svg';
     import './App.css';

     export default function App() {
       return (
         <>
           <h1 className="coffee">Hello!</h1>
         </>
       );
     }
     ```

  3. React에서 JavaScript코드도 사용이 가능합니다. 다만, 작성시 중괄호 {}로 묵어주어야 합니다.

     ```jsx
     // App.js
     import logo from './logo.svg';
     import './App.css';

     export default function App() {
       const name = '용민';
       return (
         <>
           <h1>Hello!</h1>
           <p>{name}</p>
         </>
       );
     }
     ```

  ***

  ### JSX 문법 정리 (심화)

  1. 자바스크립트 문법 사용시에 항상 중괄호{}로 묶어주어야 합니다.

     ```jsx
     // App.js
     import logo from './logo.svg';
     import './App.css';

     export default function App() {
       const name = '용민';
       return (
         <>
           <h1>{`Hello! ${name}`}</h1> // 자바스크립트 문법을 사용시 항상 중괄호로 묶어주어야
           합니다. Hello 용민 출력
           <ul>
             <li>122</li>
             <li>133</li>
             <li>144</li>
           </ul>
         </>
       );
     }
     ```

  1. 리스트를 만들떄는 자바스크립트 문법을 활용하자! (값을 접근 하는 item과 같은 경우는 중괄호로 묶어주어야 합니다.)

     ```jsx
     // App.js
     import logo from './logo.svg';
     import './App.css';

     export default function App() {
       const name = '용민';
       const list = ['122', '133', '144']; // 리스트 선언 맵핑을 통해 뻉글뺑글 돌면서 리스트로 출력될꺼임
       return (
         <>
           <h1>{`Hello! ${name}`}</h1> // 자바스크립트 문법을 사용시 항상 중괄호로 묶어주어야
           합니다. Hello 용민 출력
           <ul>
             {list.map((item) => (
               <li>{item}</li>
             ))}
           </ul>
         </>
       );
     }
     ```

     위의 list.map은 return 이 생략되었는데 생략되기 이전의 코드는 아래와 같다

     ```jsx
     {
       list.map((item) => {
         return <li>{item}</li>;
       });
     }
     ```

     화살표 함수 ⇒ 일반 함수로 변경

     ```jsx
     {
       list.map(function (item) {
         return <li>{item}</li>;
       });
     }
     ```

- Props / State

  # Props

  컴포넌트는, 데이터를 가진 하나의 ‘props’ 객체 인자를 받은 후 React 엘리먼트를 반환합니다. 이때 props는 속성을 나타내는 데이터입니다.
  props는 컴포넌트에서 컴포넌트로 전달하는 데이터입니다. 컴포넌트의 속성으로, 해당 컴포넌트를 불러와 사용하는 부모 컴포넌트에서만 설정이 가능합니다.

  ### props 지정하기!

  • props는 `<ComponentName prop1={propValue1} prop2={propValue2} ... />` 형태로 컴포넌트를 부를 때 함께 지정한다. 아래 코드에서는 Dog 컴포넌트에 name prop와 age prop를 지정하였다.

  ```jsx
  <Dog name="yong" age={10} />
  <Dog name="min" age={20} />
  ```

  위의 코드 처럼 같은 타입의 컴포넌트에 다른 props 값을 주어, 패턴이 반복되는 형태로 컴포넌트의 효율적인 재사용이 가능합니다.
  props에는 불리언 값(true, false), 숫자, 배열과 같은 다양한 형태의 데이터를 담을 수 있습니다. 공백 구분으로 여러 개를 담는 것도 가능합니다.
  props에 있는 데이터는 문자열인 경우를 제외하면 모두 중괄호 {} 로 감싸주어야합니다.

  ### props 받아서 사용하기!

  props는 읽기 전용이므로 컴포넌트의 내부에서 props를 수정해서는 안됩니다. 입력값을 수정하지 않는 함수를 순수 함수라고 호칭하며, 모든 React 컴포넌트는 자신의 props를 다룰 때 순수 함수처럼 동작해야 합니다.
  props를 받는 함수형 컴포넌트에 인자를 정의하면, props를 속성으로 가지는 객체 Object가 해당 인자로 전달된다. 컴포넌트 내부에서 사용 시, 객체에 존재하는 값을 가져오듯 점 연산자(.)를 사용하여 원하는 props를 꺼내어 사용할 수 있고, 이를 중괄호로 감싸 `{ [인자 이름].[props 이름] }`의 형태로 사용할 수 있습니다.

  ```jsx
  // 객체 인자를 통해 props 받아오기!
  function Dog(props) {
  	return {
  		<div>{props.name}</div>
  		<div>{props.age}</div>
  	}
  }
  ```

  props.name, props.age이런식으로 dot notation을 사용하는 것은 코드가 난해한 것 처럼 보인다.
  이런 경우에는 구조 분해 할당을 사용해 줄 수 있다.

  ```jsx
  function Dog({ name, age }) {
  	return {
  		<div>{name}</div>
  		<div>{age}></div>
  	}
  }
  ```

  ‘prop-types’ 라이브러리를 통해 컴포넌트의 특별한 프로퍼티인 propTypes를 선언하여 컴포넌트가 받은 props의 타입을 확인할 수 있습니다. defaultlProps 프로퍼티를 할당하여 초기 값을 정의할 수 있습니다.

  ```jsx
  // 컴포넌트 props 타입 확인
  Dog.defaultProps = {
    name: '이름',
    age: 0,
  };

  // 컴포넌트 props 타입 확인
  Dog.propTypes = {
    name: propTypes.string.isRequired,
    age: PropTypes.number,
  };
  ```

  ***

  # state

  state는 컴포넌트 내부의 동적 데이터를 의미합니다. props는 부모 컴포넌트가 설정하는 값으로 컴포넌트 자신은 props를 읽기 전용으로만 사용할 수 있습니다.
  state를 사용하는 방식에는 컴포넌트의 종류에 따라 2가지가 있습니다. 클래스형 컴포넌트에서는 컴포넌트 자체가 state를 지니는 방식으로 사용합니다. `함수형 컴포넌트에서는 useState`라는 함수, Hook을 통해 사용합니다.
  여러 개의 자식으로부터 데이터를 모으거나 두 개의 자식 컴포넌트들이 서로 통신하기 위해서는 조상 컴포넌트에 state를 정의합니다. 조상 컴포넌트가 props를 사용하여 자식 컴포넌트에 state를 다시 전달함으로서 서로 동기화가 됩니다.
  두 컴포넌트 간 state 값을 동기화 하는일, state를 공유하는 일은, 그 state 값을 필요로 하는 컴포넌트 간의 가장 가까운 공통 조상 컴포넌트로 state를 끌어올림으로 가능합니다.

- Virtual DOM
  ### Virtual DOM
  ***
  ### `Virtual DOM 탄생배경`
  Web의 복잡도가 점차 증가했고, DOM 조작이 점점 빈번하게 일어나게 되었습니다. 브라우저의 렌더 과정에 따라 DOM의 조작은 브라우저의 렌더 과정을 유발합니다. (렌더 트리 생성, 페인트 등등)
  즉, 10만번의 변화가 발생시에, 렌더링 과정또한 10만번 진행한다는 것입니다. 이 처럼 DOM 조작이 많이 발생하는 경우, 이는 `상당히 비효율적`입니다. `Virtual DOM은 이런 상황을 해결`하기 위해 탄생했습니다.
  ***
  ### `Virtual DOM의 작동과정?`
  `Virtual DOM`에 적용되어지는 변경 사항은 `DOM`에 바로 반영되지 않습니다.
  즉, 변경사항들을 `VirtualDOM`에 모아두었다가, 한번에 `DOM`에 전달되어집니다. 그러면 `DOM`은 업데이트를 1번만 하면 됩니다. 즉, 이경우에는 `Render` 처리 또한 1번만 이루어집니다.
  즉, `DOM 조작`이 아주 빈번할 경우 `Virtual DOM`은 `DOM을 조작하는 것에 비해 효율적으로 동작`합니다.
  ***
  ### `Virtual DOM 단점`
  `Virtual DOM`의 `작동원리는 하나의 레이어를 더 거쳐가기 떄문에`, DOM 조작이 아주 많지 않다면 DOM을 직접 조작하는 것 보다 `느립니다.`
  - Virtual DOM 조작 ⇒ DOM 조작 🐌(느림)
  - DOM 조작 🐇(빠름)
    하지만, 실제로 DOM 조작을 많이하는 경우는 별로 없습니다. 정상적인 상황에서 10만번의 DOM 조작 같은 건 일어날 일이 없습니다.
    그러니까 사실 대부분의 상황에서 웹 개발자들은 Virtual DOM을 이용할 필요가 없을 정도로, 그냥 DOM 사용해도 프로그램이 충분히 잘 돌아간다.
- Reconciliation (재조정)

  ### Reconciliation (재조정)

  React는 컴포넌트에서 prop이나, state이 변경될 때, 직전에 렌더링 된 요소와 새로 반환된 요소를 비교하여 실제 DOM을 업데이트 할지 말지 결정해야 한다. 이떄 두 element가 일치하지 않는다면, React는 새로운 요소로 DOM을 업데이트 하는데, 이러한 프로세스를 `reconciliation`이라고 한다.
  ![스크린샷 2023-04-09 오후 8.24.14.png](%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-04-09_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.24.14.png)

  ### 비교 알고리즘 (Diffing Algorithm)

  두 개의 트리를 비교할 떄, React는 두 엘리먼트의 root 엘리먼트부터 비교합니다.
  이후의 동작은 root 엘리먼트의 타입에 따라 달라집니다.

  1. element의 타입이 다른 경우: 이전 트리를 버리고 완전히 새로운 트리를 구축

  ```tsx
  // 이전 트리
  <div>
  	<Counter />
  </div>

  // 새로운 트리
  <span>
  	<Counter />
  </span>

  // 이전 Counter는 버리고 새로운 Counter를 사용합니다.
  ```

  1. DOM element의 타입이 같은 경우: 두 엘리먼트의 속성을 확인하여, 동일한 내역은 유지하고 변경된 속성들만 갱신이됩니다.

  ```tsx
  <div className="before" title="stuff" />

  <div className="after" title="stuff" />

  // className만 수정
  ```

  1. DOM 노드의 처리가 끝나면, React는 이어서 해당 노드의 자식들을 재귀적으로 처리한다.

  ### 자식에 대한 재귀적 처리

  DOM노드의 자식을 재귀적으로 처리할 떄, React는 기본적으로 동시에 두 리스트를 순회하고 차이점이 있으면 변경된 부분을 갱신합니다.

  ```jsx
  // 이전 트리
  <ul>
    <li>first</li>
    <li>second</li>
  </ul>

  // 새로운 트리
  <ul>
    <li>first</li>
    <li>second</li>
    <li>third</li>
  </ul>
  ```

  새로운 트리에서 third가 생김으로, `<li>third</li>`만 트리에 추가합니다.
  이떄, 자식노드들에 key값을 할당하는 것이 왜 중요한지 알 수 있다.
  만약에 `<li>third</li>` 를 앞에 추가해야하는 경우?

  ```jsx
  // 이전 트리
  <ul>
    <li>first</li>
    <li>second</li>
  </ul>

  // 새로운 트리
  <ul>
  	<li>third</li> // <- 여기!
    <li>first</li>
    <li>second</li>
  </ul>
  ```

  이떄는 first, second가 같음에도 전체 트리를 갈아엎어야합니다. (성능 저하를 야기합니다.)
  이 부분을 해결하기 위해 `key 속성`을 제공합니다.
  이렇게 되면, 300key를 가진 third만 새로운 트리에 추가합니다.

  ```jsx
  // 이전 트리
  <ul>
    <li key="100">first</li>
    <li key="200">second</li>
  </ul>// 새로운 트리
  <ul>
  	<li key="300">third</li> // <- 여기!
    <li key="100">first</li>
    <li key="200">second</li>
  </ul>
  ```

- Event handling

  # Event handling

  React에서 이벤트를 처리하는 방식은 DOM 에서 이벤트를 처리하는 방식과 매우 유사합니다. 문법에서 몇가지 차이점이 존재합니다.

  1. React에서는 이벤트는 소문자 대신 camelCase를 사용합니다.
  2. JSX를 사용하여 문자열이 아닌 함수로 Event handler를 전달합니다.

  ```jsx
  // HTML
  <button onclick="activateLasers()">
  	Activate Lasers
  </button>

  // React
  <Button onClick={activateLasers} text="Activate Lasers" />
  ```

  1. React에서는 false를 반환해도 기본 동작을 방지할 수 없습니다. 반드시 preventDefault를 명시적으로 호출해야합니다.

  ```jsx
  // HTML에서 form을 제출할 때 가지고 있는 기본적인 동작을 방지하기 위해 아래와 같이 코드 작성
  <form onsubmit="console.log('You clicked submit.'); return false">
    <button type="submit">Submit</button>
  </form>;

  // React
  function Form() {
    function handleSubmit(e) {
      e.preventDefault();
      console.log('You clicked submit.');
    }

    return (
      <form onSubmit={handleSubmit}>
        <button type="submit">Submit</button>
      </form>
    );
  }
  ```

  ***

  ### Event handler에 인자 전달하기

  ```jsx
  <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
  <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
  ```

  두 경우 모두 React 이벤트를 나타내는 `e`인자가 ID 뒤에 두 번째 인자로 전달됩니다. 화살표 함수를 사용하면 명시적으로 인자를 전달해야 하지만 `bind`를 사용할 경우 추가 인자가 자동으로 전달됩니다.

## 📢 학습 후기

---

- 이번 주차 워크북을 해결해보면서 어땠는지 회고해봅시다.
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

- [ ] create-react-app으로 프로젝트 생성한 후 핵심 개념 학습하기
  - [ ] 컴포넌트
  - [ ] JSX
  - [ ] State, Props (useState)

## ☑️ 실습 인증 파트

---

- create-react-app으로 프로젝트 생성한 후 핵심 개념 학습하기
  - 컴포넌트
  - JSX
  - State, Props (useState)

## 🔥 미션

---

1. 학습한 개념을 바탕으로 1주차때 만들었던 서비스를 리액트로 만들기

   기존에 HTML, CSS, JS로만 구현한 넷플릭스 홈페이지는 리액트의 기능을 정상적으로 활용하기는 어려울 것 같아, 로그인 전의 메인페이지를 만들었다면, 이번에는 로그인 한 후의 메인페이지를 만들었습니다. 로그인 페이지 / SignUp 페이지를 구현하였습니다.

   1. The Movie DataBase 홈페이지에서 API를 받아서 한국어로 영화의 제목, 내용, 개봉일 등을 받아와 메인화면에 보여주었습니다.
   2. 각각 Upcoming Popular Trending 등의 Section에 맞게 API를 받아와 실제 넷플릭스 화면처럼 보여줄 수 있게 구현했습니다.
   3. 그 후 UID를 활용하여 우측 버튼 좌측 버튼을 눌러서 슬라이가 움직일 수 있도록 구현해주었습니다.
   4. Sign Up / Sign In 페이지도 구현하였습니다.

   . `useEffect` hook과, `useState` hook을 활용하여 구현했습니다

   version 1

   추후 이미지 첨부
   용량 문제 해결

   version 2

   추후 이미지 첨부
   용량 문제 해결

   1. 로그인 이전 메인 페이지, 로그인 페이지 추가
   2. 프로필 페이지 추가
   3. 넷플릭스와 매우 유사하게 디자인 진행. 메인 화면시 상단바 블랙 색상으로 고정 등…
   4. 여러 UI 수정

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

## 🤔 이것도 한 번 생각해봐요!

---

- setState말고 state를 직접 변경해주면 왜 화면 갱신이 안될까?
  state는 immutable(불변성)을 유지해야하기 때문입니다.컴포넌트는 현재의 this.state와 setState를 비교해서 업데이트가 필요한 경우에만 render 함수를 호출하는데, state를 직접 수정하게 되면 리액트가 render 함수를 호출하지 않아 상태 변경이 일어나도 렌더링이 일어나지 않을 수 있습니다. 상태 변경을 추적하고 변경에 따라 구성요소를 다시 렌더링하려면 setState를 사용해야 합니다.
  1. setState는 비동기적으로 동작하기 때문에 state가 직접 수정되어 여러번 상태를 업데이트 하는 경우, 이전 업데이트 내용이 다음 업데이트 내용에 덮어 쓰여질 수가 있어 예상치 못한 곳에서 버그가 발생 할 수 있습니다.
  2. PureComponent에서 동작하지 않습니다. PureComponent는 this.state와 setState를 비교해 업데이트가 필요한 경우에만 render함수를 호출해 줍니다. 이때, state를 직접 수정하게되면 기존의 this.state와 setState가 동일하므로 리액트는 render함수를 호출하지 않습니다.
     결론, state는 꼭 불변성을 유지하도록 직접 수정하지 말자!state의 object를 직접 수정하지 않고 새로운 object를 만들어 주려면 object의 할당과 spread 연산자를 알아두면 좋습니다. (map함수도, filter함수도 새로운 배열을 반환하기때문에 이럴때 사용하면 좋습니다.)

## 🤔 참고 자료

---

[[React] SPA란 무엇이며 언제 사용하는지...](https://codingmania.tistory.com/328)

[[React] SPA란?](https://typeof-bong.tistory.com/19)

[https://www.youtube.com/watch?v=BYbgopx44vo&ab_channel=PurelyFunctionaltv](https://www.youtube.com/watch?v=BYbgopx44vo&ab_channel=PurelyFunctionaltv)

[https://www.youtube.com/watch?v=YuqB8D6eCKE&ab_channel=우아한테크](https://www.youtube.com/watch?v=YuqB8D6eCKE&ab_channel=우아한테크)

[SPA vs MPA와 SSR vs CSR 장단점 뜻정리 - 하나몬](https://hanamon.kr/spa-mpa-ssr-csr-장단점-뜻정리/)

---

## 👨🏻‍💻 3주차 워크북 후기

기존에 만들었던 모든 페이지들을 HTML,CSS,JS에서 React로 변환하느라 고생을 했다.
기존에 했던 프로젝트가, 로그인 이전의 페이지만 구현을 해서, 이번에는 실제 넷플릭스처럼 API를 영화 데이터를 관리하는 외국 홈페이지에 받아서, 한국어 버전으로 변환하여 구현하였다.
나쁘지 않은 실습이였고, 나름 만족할 만한 프로젝트를 진행한 것 같다.

---

**UMC 활동에 대해 궁금하신 점이 있다면 아래 `댓글`로 남겨주세요!👇**
