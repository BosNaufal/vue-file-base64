
<template>
  <div align="center">

    <h1>Vue, File To Base64 Converter</h1>
    <p>*) Try To Upload Some Image~</p>

    <file-base64 :multiple="true" :done="getFiles"></file-base64>

    <div class="text-center">
      <img src="" alt="" :src="img.base64" v-for="img in files">
    </div>

    <div v-if="files.length != 0">
      <h3 class="text-center mt-25">Callback Object</h3>
      <div class="pre-container" align="left">
        <pre>{{ files }}</pre>
      </div>
    </div>

  </div>

</template>

<script>

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
