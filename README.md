# Vue Global MFE
This module provides the HeaderMFE, FooterMFE and NavigationBar components. We can pass props (navlist) to NavigationBar which is a list of objects with name and slug (url to redirect on click).

Technologies used for development: This is a Vue Plugin which exports components using vite build tool. 

## Installation
Use the yarn or npm package manager to install the vue-global-mfe.

#### yarn installation
```bash
yarn add vue-global-mfe 
```

#### npm installation
```bash
npm install vue-global-mfe 
```

## Usage
```javascript
<template>
  <HeaderMFE/>
  <NavigationBar :navlist="list" />
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import {NavigationBar,HeaderMFE} from 'vue-global-mfe'
import 'vue-global-mfe/dist/style.css'

export default {
  name: 'App',
  components: {
    HelloWorld,
    NavigationBar,
    HeaderMFE
  },
  data(){
    return {
      list:['a','b','c','d','e','f','g','h','i','j']
    }
  }
}
</script>
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## For Publishing
Please follow below steps before making changes.
1. npm install
2. make changes
3. update version in package.json and update readme file if necessary
4. npm run build
5. test in local if it is working by npm link
6. raise PR to main.
Thanks !!
