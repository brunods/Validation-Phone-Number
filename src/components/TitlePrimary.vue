<script setup>
defineProps({
    title: String
})
</script>

<template>
    <h1>{{ title }}</h1>
</template>

<style scoped>
h1{
    margin: 30px 0;
    color: #50ff93;
    font-weight: 200;
}
</style>