
<template>
  <div align="center">
    <h1>Vue, File To Base64 Converter</h1>
    <p>*) Try To Upload Some Image~</p>

    <file-base64
      :multiple="true"
      :done="getFiles"
    />

    <div class="text-center">
      <img
        v-for="img in files"
        :key="img.name"
        alt=""
        :src="img.base64"
      >
    </div>

    <div v-if="files.length != 0">
      <h3 class="text-center mt-25">
        Callback Object
      </h3>
      <div
        class="pre-container"
        align="left"
      >
        <pre>{{ files }}</pre>
      </div>
    </div>
  </div>
</template>

<script>

import fileBase64 from './vue-file-base64.vue'

export default {

  components: { fileBase64 },

  data () {
    return {
      files: []
    }
  },

  methods: {
    getFiles (files) {
      this.files = files
    }
  }
}

</script>
