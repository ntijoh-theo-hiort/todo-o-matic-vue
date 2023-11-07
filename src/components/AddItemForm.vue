<script setup lang="ts">
const emit = defineEmits(['addItem'])
let todoName = ""


function addItem() {
    emit('addItem', todoName)
}

</script>

<template>
    <form @submit.prevent @submit="addItem()">
        <input id="text" v-model="todoName" type="text" placeholder="Add Items">
        <input type="submit">
    </form>
</template>

<style scoped>
li {
    display: flex;
}
</style>