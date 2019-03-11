<template>
  <div id="app">
    <img alt="3deposit logo" src="./assets/logo.png" height="128" width="128">
    <Banner msg="Deposit Form"/>
    <Fields v-bind:fields="fields"/>
  </div>
</template>

<script>
import Banner from './components/Banner.vue'
import Fields from './components/Fields.vue'

export default {
  name: 'app',
  components: {
    Banner,
    Fields
  },
  data() {
    return {
      fields: {
        creatorName: {
          label: 'Creator Name',
          type: 'text',
          value:''
        },
        objectType: {
          label: 'Object Type',
          type: 'select',
          choices: ['3d model', 'VR', '360 video'],
          value: ''
        },
        modelFileType: {
          label: 'File Type',
          type: 'select',
          choices: ['obj', 'glTF'],
          value: ''
        }
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
