<script setup>
import { reactive } from "vue";
import Node from "../components/Node.vue";
// const nodes = reactive([
//     {
//         id: "1", title: "The first node", elements: [
//             { type: "text", data: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Facere minus repellendus deserunt corporis!" }
//         ],
//         position: { x: 15, y: 15 }
//     },
//     {
//         id: "2", title: "The second node", elements: [
//             { type: "image", data: "download.jpeg" }
//         ],
//         position: { x: 5, y: 50 }
//     }
// ])
// localStorage.setItem("nodes", JSON.stringify(nodes))
const nodes = reactive(JSON.parse(localStorage.getItem("nodes")));
function onmove(node) {
    const id = node.id
    nodes.find(n => n.id === id).position = node.position;
    localStorage.setItem("nodes", JSON.stringify(nodes))
};
</script>
<template>
    <div id="workspace">
        <Node v-for="node in nodes" :key="node.key" :node="node" @move="() => onmove(node)" />
    </div>
</template>
<style>
#workspace {
    position: relative;
    width: 100%;
    height: 100vh;
    background-color: #222;
    box-shadow: inset 0 1px 2px #000;
    background-image: radial-gradient(#fff, transparent 1px);
    background-size: 20px 20px;
}

@media(prefers-color-scheme: light) {
    #workspace {
        background-color: #fff;
        box-shadow: inset 0 1px 2px #444;
        background-image: radial-gradient(#888, transparent 1px);
    }
}
</style>