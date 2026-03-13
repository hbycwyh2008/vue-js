<template>
  <div class="container bg-black text pt-3" :style="{height: '100vh'}">
    <h1 class="text-center text-success">ContactOpedia</h1>

    <div class="row align-items-center">
      <LuckyNumber />
      <LuckyNumberV2 />
    </div>
  </div>
</template>


<script setup>
import { ref, reactive } from 'vue';
import LuckyNumber from './components/LuckyNumber.vue';
import LuckyNumberV2 from './components/LuckyNumberV2.vue';





</script>