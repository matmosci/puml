<script setup>
const props = defineProps(["element"]);
</script>
<template>
    <div class="node-element">
        <img v-if="element.type === 'image'" :src="element.data" alt="">
        <p v-if="element.type === 'text'">{{ element.data }}</p>
    </div>
</template>
<style>
.node-element {
    border-top: 1px solid #111;
    padding: 0;
}

.node-element > p {
    margin: 0 .2em;
}

.node-element > img {
    width: 100%;
}
</style>
