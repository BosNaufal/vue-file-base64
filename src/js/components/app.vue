
<template lang="jade">

div
  h1.text-center Vue File to Base64 Converter

  .text-center.mt-25
    p.text-center *) Try To Upload Some Image~
    file-base64( v-bind:multiple="true" v-bind:done="getFiles" )

  div.text-center
    img(
      v-bind:src="img.base64"
      v-for="img in files"
    )

  div( v-if="files.length != 0" )
    h3.text-center.mt-25 Callback Object
    .pre-container
      pre {{ files | json 2 }}

</template>

<script>

  require('../../sass/main.sass')

  import fileBase64 from './vue-file-base64.vue';

  export default {

    data(){
      return{
        files: []
      }
    },

    components: { fileBase64 },

    methods: {
      getFiles(files){
        this.files = files
      }
    }
  };

</script>
