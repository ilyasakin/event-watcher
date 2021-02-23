<template>
  <div class="box">
    <div class="title">{{ title }}</div>
    <div class="text">{{ text }}</div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
  title: String,
  text: String,
});
</script>

<style lang="scss" scoped>
.box {
  border: 4px solid #000000;
  padding: 2rem;
  box-sizing: border-box;
}

.title {
  font-weight: 700;
}

.text {
  font-size: 1.25rem;
}
</style>
