<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)

const emit = defineEmits(['updated'])

function emitUpdate(e : Event) {
  e.preventDefault()
  emit('updated', count.value)
}

</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <form @submit="emitUpdate" action="#">
    <button>show current value</button>
  </form>

</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
