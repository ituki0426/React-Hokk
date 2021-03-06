# 1 useStateとは


stateと、state更新関数を返すフックです。


このフックを利用すれば、コンポーネント（関数）内で、state管理が出来ます。


「state」とは、画面に表示されるデータやUIの状態など、アプリケーションが保持している情報のことです。


# 2 useStateの構文


useStateの構文は以下のようになります。



```javascript
const [state, state 更新関数]  = useState(stateの初期値);
```

例えば、初期値の「count」というstateと、countを更新する「setCount」という関数を定義する場合以下のようになる。


```javascript
const [count, setCount] = useState(0)
```

また、state更新関数は、値や関数を渡すことでstateを更新することが出来る。


例えば、以下のようにsetCountに10を渡せば、stateであるcountが更新されて10になります。


```javascript
setCount(10);
```


# 3 useStateの利用


```javascript
import { useState,useEffect } from 'react'
import React, { Component } from 'react';

export default function App() {
  const [count , setCount] = useState(10);
  const decrement = () =>{
    setCount(count - 2);
  };
  const increment = () =>{
    setCount(count + 2);
  };
  return(
    <>
    <p>Count: {count}</p>
    <button onClick={decrement}>-</button>
    <button onClick={increment}>+</button>
    </>
  );
  }
```


# 4 オブジェクトを扱う


```javascript
import { useState,useEffect } from 'react'
import React, { Component } from 'react';

export default function App() {
  const [vote, setVote] = useState({kinoko:0,takenoko:0});
  const voteKinoko = () =>{
    setVote({...vote,kinoko:vote.kinoko+1});
  };
  const voteTakenoko = () =>{
    setVote({...vote,takenoko:vote.takenoko+1});
  }
  return(
    <>
    <p>キノコ:{vote.kinoko}</p>
    <p>タケノコ:{vote.takenoko}</p>
    <button onClick={voteKinoko}>キノコ</button>
    <button onClick={voteTakenoko}>タケノコ</button>
    </>
  );
  }
```






















