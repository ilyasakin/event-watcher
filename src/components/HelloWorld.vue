<template>
  <div>{{ state.count }}</div>
</template>

<script setup>
import { defineProps, reactive } from 'vue';

defineProps({
  msg: String,
});

const state = reactive({ count: 0 });

const emit = () => console.log('hey');
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
