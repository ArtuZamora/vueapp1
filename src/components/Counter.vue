<script setup>
import { ref } from 'vue';

const counter = ref(0);

const increment = (value = 1) => {
  counter.value += value;
};
</script>

<template>
  <button @click="increment(5)">Increment</button>
  <p>Counter: {{ counter }}</p>
</template>
