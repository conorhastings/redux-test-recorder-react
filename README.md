## Redux Test Recorder React

`npm install redux-test-recorder-react --save-dev`

A react component that provides a gui to the <a href="http://github.com/conorhastings/redux-test-recorder">redux-test-recorder</a> redux middleware which can be used to auto generate reducer tests for redux applications through testing UI interactions. You can use use the props exported by the middleware and pass those to the TestRecorder component at your application root.

```js
import {store, recordProps } from './store';
import TestRecorder from 'redux-test-recorder-react';
const Counter = ({count, dispatch}) => {
  return (
    <div>
      <button onClick={() => dispatch(increment())}>+</button>
      <h1>{count}</h1>
      <button onClick={() => dispatch(decrement())}>-</button>
    </div>
  );
}

const ConnectedCounter = connect(state => {
  return {count: state};
})(Counter);
const Root = () => {
  return (
    <div>
      <Provider store={store}>
        <div><ConnectedCounter /><TestRecorder {...recordProps} /></div>
      </Provider>
    </div>;
};
```

You can see more comprehensive documention in the <a href="http://github.com/conorhastings/redux-test-recorder">redux-test-recorder</a> repo. 

