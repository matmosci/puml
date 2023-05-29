<script setup>
const props = defineProps(["title"]);
</script>
<template>
    <h1 class="node-header">{{ title }}</h1>
</template>
<style>
.node-header {
    font-size: 1em;
    margin: .2em 0;
    padding: 0 .2em;
}
</style>
