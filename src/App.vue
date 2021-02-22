<template>
  <div id="app" tabindex="0" ref="main" @keydown="fireEvent">
    <div>Key: {{ event.key }}</div>
    <div>Code: {{ event.code }}</div>
    <div>KeyCode: {{ event.keyCode }}</div>
  </div>
</template>

<script setup>
import { ref, onMounted, reactive } from 'vue';
const event = reactive({ key: undefined, code: undefined, keyCode: undefined });

const main = ref(null);

onMounted(() => {
  main.value.focus();
});

const fireEvent = (e) => {
  event.key = e.key;
  event.code = e.code;
  event.keyCode = e.keyCode;
};
</script>

<style>
#app {
  padding: 2rem;
  font-family: --apple-system, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  height: 100%;
  outline: none;
  box-sizing: border-box;
}
</style>
