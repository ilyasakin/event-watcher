<template>
  <div id="app" tabindex="0" ref="main" @keydown="hello">
    <div>{{ event.key }}</div>
  </div>
</template>

<script setup>
import { ref, onMounted, reactive } from 'vue';
const event = reactive({ key: undefined, code: undefined });
const hello = (e) => (event.key = e.key);

const main = ref(null);
onMounted(() => {
  main.value.focus();
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  height: 100%;
}
</style>
