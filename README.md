# React Native with Redux basic boilerplate

&nbsp;
### Node, NPM, Yarn, react-native, redux, react-redux


&nbsp;
## 00 Initial commit

* Initialize a new project for the boilerplate with the react-native cli.

```
$ react-native init boilerplate
```

* Git the result.




&nbsp;
## 01 Basic boilerplate

* Install Redux and react-redux

```
$  npm install --save redux react-redux

```

* Create the src folder, move App.js in it and edit index.js in order to find the new location of App.js.

*./index.js*

```
import { AppRegistry } from 'react-native';
import App from './src/App';

AppRegistry.registerComponent('manager', () => App);
```
* Create the reducers folder inside src. Create index.js inside reducers and inside combineReducers add a dummy reducer that returns an empty list.

*./src/reducers/index.js*

```
import { combineReducers } from 'redux';

export default combineReducers({
  boilerReducer: () => []
});
```

* Remove the default content out of App.js and replace it with the following basic boilerplate code for a react native with redux app.

*./src/App.js*
```
import React, { Component } from 'react';
import { Text,  View } from 'react-native';
import { Provider } from 'react-redux';
import { createStore } from 'redux';
import reducers from './reducers';

export default class App extends Component<{}> {
  render() {
    return (
      <Provider store={createStore(reducers)} >
        <View>
          <Text>
            React Native with Redux app basic boilerplate
          </Text>
        </View>
      </Provider>
    );
  }
}
```
