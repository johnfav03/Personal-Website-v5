<script setup>

import NavStrip from './NavStrip.vue'

const props = defineProps([
    'title',
    'color',
    'pos',
    'off'
])


const emit = defineEmits([
    'toggle'
])


</script>


<template>

<div
    class="wrap"
    :style="{
        zIndex: 3 - pos,
        left: off
    }"
>

    <div class="cont">

        <slot />

    </div>


    <NavStrip
        :title="title"
        :color="color"
        @click="emit('toggle', pos)"
    />

</div>

</template>


<style scoped>

.wrap {

    height:100%;

    display:flex;

    position:fixed;

    top:0;
    left:0;

    transition: left .5s ease;

}


.cont {

    width:
        calc(100vw - 130px);

    height:100%;

    background:
        var(--bg-dark);

}

</style>