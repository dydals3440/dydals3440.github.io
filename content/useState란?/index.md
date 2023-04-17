---
emoji: 📶
title: useState Hook에 대해 자세하게 알아보자!
date: '2023-04-17 22:11:00'
author: dydals3440
tags: react useState
categories: react
---

# useState에 대해서 알아보자!

<span style="color:blue">**useState**</span>는 리액트에서 가장 많이 사용하는 훅 중 하나로, 상태를 업데이트 한다고 생각하면 좋습니다.

```js
import { useState } from 'react';

const [state, setState] = useState(초기값);
```

[name, setName], [people, setPeople] 과 같이 사용할 수 있다. 이름은 딱히 중요하지 않다. <span style="color:blue">**useState**</span> Hook을 import 해와야 하며, 초기값에는 문자열, 객체
<span style="color:blue">**setState**</span>를 통해 우리의 state 값을 변경할 수 있다. <span style="color:blue">**setState**</span>를 사용해서 state를 변경할 떄마다 컴포넌트는 렌더링이 계속 됩니다.

---

## useState의 특징

1. state값이 이전 상태 값과 연관된 경우

```js
setState((prevState) => {
  // 일들
  return newState;
});
```

2. <span style="color:blue">**useState**</span>를 통해 초기값을 받아올떄 어떠한 무거운 값을 해야할떄 <span style="color:blue">**useState**</span>의 인자로 콜백함수를 넣어주면 맨 처음 렌더링이 될떄 1번만 시행되게 할 수 있습니다.

이 부분은 아래에서 코드 실습으로 자세하게 설명 해보겠습니다.

![useState 시간 증가 실습](https://velog.velcdn.com/images/dydals3440/post/54ae9ef9-abd0-4d9b-a588-6f6254ed2488/image.mov)
위와 같은 시간을 1시간씩 증가시켜주는 버튼을 만들어 보겠습니다. 단, 24시간을 넘었을 떄 상태를 1시간으로 초기화 시켜주어야 합니다.

```js
function App() {
  const [time, setTime] = useState(1);
  let newTime;
  const handleClick = () => {
    if (time >= 24) {
      newTime = 1;
      alert('24시간을 넘어갈 수는 없습니다.');
    } else {
      newTime = time + 1;
    }
    setTime(newTime);
  };
  return (
    <>
      <span>현재 시각: {time}시</span>
      <button onClick={handleClick}>Update</button>
    </>
  );
}

export default App;
```

<span style="color:blue">**useState**</span>의 초기 값은 배열, 객체로 초기값을 설정해도 무관합니다.

아래와 같은 이미지를 구현해 보겠습니다.
![Upload](https://velog.velcdn.com/images/dydals3440/post/f4b4668d-8ae6-46b9-b6b6-7ebe4b29dd63/image.png)

```js
function App() {
  const [names, setNames] = useState(['김용민', '김살라']);
  return (
    <>
      <input type="text" />
      <button>Upload</button>
      <ul>
        {names.map((name, idx) => {
          return <li key={idx}>{name}</li>;
        })}
      </ul>
    </>
  );
}

export default App;
```

## 실습. 입력 값을 화면에 보이게 하기!!

![실습 예제 영상](https://velog.velcdn.com/images/dydals3440/post/e57fe1a4-966d-4c7a-be4b-865ef7081a52/image.mov)

일단은 어떻게 구현해 볼지 생각을 해보겠습니다.

1. [name, setName]이 있는데, name을 우리가 입력한 값을 추가해주기 위해서는 새로운 상태 [input, setInput]을 만들어, input창에 입력 받은 값으로 <span style="color:blue">**setNames**</span>을 초기화 해주면 됩니다.

2. 기존에 입력 받은 값들을 유지하면서 그 뒤에 우리는 추가하고 싶은 것이므로, prev를 사용해야한다는 것을 인지하고, return을 해야합니다.

### 구현 과정

1. 입력 값을 어떻게 받아올 것에 대한 고찰
   input값의 value를 받아와야 하기에 우리는 input 태그에 value를 추가해주었다. 그 후 ul을 만들어주었는데, 리액트에서는 key를 기반으로 렌더링이 진행되므로 항상 li에는 key값을 추가해주어야 하는 것을 기억해야한다.

![](https://velog.velcdn.com/images/dydals3440/post/ca110389-7514-4110-8709-364f01bc0f0b/image.png)

```js
function App() {
  const [names, setNames] = useState(['김용민', '김살라']);
  const [input, setInput] = useState('');
  return (
    <>
      <input type="text" value={input} />
      <button>추가</button>
      <ul>
        {names.map((name, idx) => {
          return <li key={idx}>{name}</li>;
        })}
      </ul>
    </>
  );
}

export default App;
```

2. 함수 만들기!

```js
function App() {
  const [names, setNames] = useState(['김용민', '김살라']);
  const [input, setInput] = useState('');

  const handleInput = (e) => {
    setInput(e.target.value);
    console.log(e.target.value);
  };

  const handleClick = () => {
    setNames(['김용민', '김살라', input]);
  };

  return (
    <>
      <input onChange={handleInput} type="text" value={input} />
      <button onClick={handleClick}>추가</button>
      <ul>
        {names.map((name, idx) => {
          return <li key={idx}>{name}</li>;
        })}
      </ul>
    </>
  );
}

export default App;
```

위와 같이 코드를 작성 하면 정상적으로 추가를 누르면 우리가 적은 것들을 유지하고 계속 새로운 것들이 추가 될 것 같지만 실제로는 그렇지 않다.
![](https://velog.velcdn.com/images/dydals3440/post/2a9ce14d-0a9f-45cd-b10f-55536a93fd58/image.mov)
아래 코드를 자세히 보자

```js
const [names, setNames] = useState(['김용민', '김살라']);

const handleClick = () => {
  setNames(['김용민', '김살라', input]);
};
```

실제로 <span style="color:blue">**setNames**</span>가 초기화를 할때, ['김용민', '김살라'] 는 유지하고 input 값만 handleInput으로 통해 변경된 값만 계속 바뀌기에 그렇다.

이럴떄는 어떻게 해야할까?

<span style="color:blue">**setClick**</span> 함수 내부에있는 상태를 업데이트 하는 코드는, 이전의 상태 초기값과 밀접하게 관련이 있다. 이러한 경우에는 <span style="color:blue">**setNames**</span> 인자안에 바로 값을 주는 것이 아닌 <span style="color:blue">**콜백함수**</span>를 전달하고, return 값을 새롭게 업데이트 되는 state를 전달해주면 된다. 이때 콜백의 인자에는 업데이트 이전의 상태를 갖고 있어야 합니다.

위에서 간략하게 설명했지만 이때 prev 라는 것을 사용하면 된다. 즉, 이전 상태 값을 계속 받아와, 거기에 추가를 해주는 것이다.

```js
const handleClick = () => {
  setNames((prev) => [...prev, input]);
};
```

위의 코드와 같이 <span style="color:blue">**이전의 값(prev)**</span>을 받아와 그 뒤에 우리가 입력한 값 즉, handleInput으로 받아온 값들을 계속해서 추가해주면 된다.![](https://velog.velcdn.com/images/dydals3440/post/eb498023-29dc-4aab-aaa8-a98930ffb309/image.mov)

---

<span style="color:blue">useState</span>를 통해 초기 값을 선언시, 무거운 일을 계속해서 수행할 떄 어떻게 해결할 수 있을까?

```js
const veryComplexWork = () => {
  console.log('매우 복잡하고 시간이 오래걸리고 짜증나는 작업중입니다.');
  return ['홍길동', '김민수'];
};

function App() {
  const [names, setNames] = useState(veryComplexWork());
  const [input, setInput] = useState('');

  const handleInput = (e) => {
    setInput(e.target.value);
    console.log(e.target.value);
  };

  const handleClick = () => {
    setNames((prev) => [...prev, input]);
  };

  return (
    <>
      <input onChange={handleInput} type="text" value={input} />
      <button onClick={handleClick}>추가</button>
      <ul>
        {names.map((name, idx) => {
          return <li key={idx}>{name}</li>;
        })}
      </ul>
    </>
  );
}

export default App;
```

이런식으로 초기값을 받을떄 매우 복잡한 일을 수행한다. 그럼 이 경우에는 매번 초기값을 받을떄마다
![](https://velog.velcdn.com/images/dydals3440/post/0e063ceb-2b24-4f6a-9766-77a7ba5baee4/image.mov)
계속 무거운 작업을 진행중인 것을 확인할 수 있다. 우리는 이런 것이 아니라, 최초 렌더링 시에만 무거운일을 할 수 있도록, 코드를 변경하고 싶다. 이 떄는 어떻게 하면 좋을까?

이때는 함수를 호출할 때 콜백함수를 통해 호출을 진행해주면 됩니다.

```js
const [names, setNames] = useState(() => veryComplexWork());
```

![](https://velog.velcdn.com/images/dydals3440/post/028d0d78-78e4-4a7b-a5d6-a5f3a88d5352/image.mov)

**UMC 활동에 대해 궁금하신 점이 있다면 아래 `댓글`로 남겨주세요!👇**
