<template>
        <button @click="count++">Clicked {{ count }} times!</button>
</template>

<script setup>
import {ref,onBeforeMount, onMounted, onBeforeUnmount, onUnmounted} from 'vue';
onBeforeMount(() => {
  console.log('OnBeforeMount: ButtonCounter.vue');
});
onMounted(() => {
  console.log('OnMounted: ButtonCounter.vue');
});
onBeforeUnmount(() => {
  console.log('OnBeforeUnmount: ButtonCounter.vue');
});
onUnmounted(() => {
  console.log('OnUnmounted: ButtonCounter.vue');
});

const count = ref(0);

</script>
