<script setup lang="ts">
import { ref } from 'vue'
import todoItem from "./components/TodoItem.vue"
import AddItemForm from "./components/AddItemForm.vue"

// function logEvent(e : Event) {
//   console.log(e)
// }

let todoItems = ref([
  { id: 0, text: "Wash Dishes" },
  { id: 1, text: "Go Outside" },
  { id: 2, text: "Quit Anime Addiction" }
])

function addItem(todoName: string) {
  const id = Math.max(...todoItems.value.map(todoItem => todoItem.id)) + 1
  
  if (todoName !== "") {
    todoItems.value.push({ id: id, text: todoName })
  }
}

</script>

<template>
  <search-bar />
  <h1>Add Items</h1>
  <AddItemForm @addItem="(todoName: string) => { addItem(todoName) }" />
  <h1>Items</h1>
  <todoItem v-for="item in todoItems" :id=item.id.toString() :text="item.text" />
  <!-- <HelloWorld v-for="message in messages" :key="message.id" id="${message.id.toString()}" @updated="logEvent" :msg="message.text" /> -->
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
