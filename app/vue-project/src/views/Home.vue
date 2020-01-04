<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" v-on:click='consoleTest'>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  methods:{
    consoleTest() {
      console.log("ConsoleTest");
      console.log(process.env.VUE_APP_API_URL_BASE);
    }
  }
  
}
</script>
