<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
    <v-btn @click="loadDataFromServer">Load data from server</v-btn>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

@Component({
  components: {
    HelloWorld,
  },
  methods:{
      async loadDataFromServer(){
          const response = await fetch("https://localhost:5001/WeatherForecast/temperatures")
          console.log(await response.json())
      }
  }
})
export default class Home extends Vue {}
</script>
