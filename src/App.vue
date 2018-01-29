<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <div class="textarea">
      <vue-auto-textarea v-model="msg"></vue-auto-textarea>
    </div>
  </div>
</template>

<script>
import vueAutoTextarea from './components/vue-auto-textarea';
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components:{
    vueAutoTextarea
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
.textarea{
  width: 360px;
  margin: 0 auto;
  text-align: left;
}
</style>
