<script setup lang="ts">
defineProps<{ text: string }>()

function removeListItem(e: Event) {
    const listItem = (e.target as HTMLButtonElement).parentElement
    if (listItem) { listItem.remove() }
}
</script>

<template>
    <li>
        <p>{{ text }}</p>
        <button @click="removeListItem">X</button>
    </li>
</template>

<style scoped>
li {
    display: flex;
}
</style>