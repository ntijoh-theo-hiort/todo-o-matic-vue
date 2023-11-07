<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'

function logEvent(e : Event) {
  console.log(e)
}

const messages = ref([
  {id: 1, text: "Hello"},
  {id: 2, text: "Wassup"},
  {id: 3, text: "Wazzaaaaa"}
])
</script>


<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  
  <HelloWorld v-for="message in messages" :key="message.id" id="${message.id.toString()}" @updated="logEvent" :msg="message.text" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
