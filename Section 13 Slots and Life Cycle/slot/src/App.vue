<template>
  <luckyNumberParentComponent>
    <p class="pt-2">We have two versions for picking lucky numbers!</p>
    <p>Click the button to toggle between those two versions.</p>
    <button @click="showMessage">what weill we learn</button>
    <h4 class="text-success">{{ message }}</h4>
    <hr/>
  </luckyNumberParentComponent>
</template>
<script setup>
import LuckyNumberParentComponent from './components/LuckyNumberParentComponent.vue';
import {ref} from 'vue';
const message = ref('');
function showMessage() {
  message.value = 'We will learn how to use slots.';
}
</script>