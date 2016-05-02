
<template lang="jade">

input( v-if="!multiple" type="file" @change="onChange" )
input( v-if="multiple" type="file" @change="onChange" multiple)

</template>


<script>

  /*! Copyright (c) 2016 Naufal Rabbani (http://github.com/BosNaufal)
  * Licensed Under MIT (http://opensource.org/licenses/MIT)
  *
  * Vue File Base64 @ Version 1.0.0
  *
  * refs: https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL
  */

  export default {

    props: {
      // Support Multiple File?
      multiple: {
        type: Boolean,
        default: false
      },
      // Pass the files info when it's done
      done: {
        type: Function,
        default: () => {}
      }
    },

    data(){
      return{
        files: []
      }
    },

    methods: {
      onChange(e){

        // get the files
        let files = e.target.files;

        // Process each file
        for (var i = 0; i < files.length; i++) {
          this.processFile(files[i])
        }

        // Pass the files info~
        this.done(this.files)

      }, // onChange()

      processFile(file){
        let reader = new FileReader()

        // Convert the file to base64 text
        reader.readAsDataURL(file)

        // on reader load somthing...
        reader.onload = () => {
          // Make a fileInfo Object
          let fileInfo = {
            name: file.name,
            type: file.type,
            size: Math.round(file.size / 1000)+' kB',
            base64: reader.result
          }
          // Push it to the state
          this.files.push(fileInfo)
        }

      } // processFile()

    }
  };

</script>
