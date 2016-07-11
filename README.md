# vue file base64
[Vue](http://vuejs.org) Component for Converting Files to base64. It's based on [Dev Mozilla Website](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL)

[DEMO](https://rawgit.com/BosNaufal/vue-file-base64/master/index.html)


## Install
You can import [vue-file-base64.vue](./src/js/components/vue-file-base64.vue) to your vue component file like [this](./src/js/components/app.vue) and process it with your preprocessor.

You can install it via NPM
```bash
npm install vue-file-base64
```


## Import Module
```javascript
import fileBase64 from 'vue-file-base64'
// Or
var fileBase64 = require('vue-file-base64');
```

## Usage
```html
<template>

  <file-base64
    v-bind:multiple="true"
    v-bind:done="getFiles">
  </file-base64>

</template>


<script>

  import fileBase64 from 'vue-file-base64';

  export default {

    components: { fileBase64 },

    methods: {
      getFiles(files){
        console.log(files);
      }
    }
  };

</script>
```

## Props
#### multiple (Boolean)
Is your component support multiple file?

#### done (Function)
Callback Function When File has done proceed


## Thank You for Making this useful~

## Let's talk about some projects with me
Just Contact Me At:
- Email: [bosnaufalemail@gmail.com](mailto:bosnaufalemail@gmail.com)
- Skype Id: bosnaufal254
- twitter: [@BosNaufal](https://twitter.com/BosNaufal)

## License
[MIT](http://opensource.org/licenses/MIT)
Copyright (c) 2016 - forever Naufal Rabbani
