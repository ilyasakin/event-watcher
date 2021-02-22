<template>
  <div id="app" tabindex="0" ref="main" @keydown="fireEvent">
    <div v-if="Object.values(event).every((value) => value === undefined)">
      Oops, no event fired so far ¯\_(ツ)_/¯
    </div>
    <div v-if="event.key">Key: {{ event.key }}</div>
    <div v-if="event.code">Code: {{ event.code }}</div>
    <div v-if="event.keyCode">KeyCode: {{ event.keyCode }}</div>
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

<style lang="scss">
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
  font-size: 1.5rem;
  display: flex;
  flex-direction: column;

  div:not(:first-child) {
    margin-top: 1rem;
  }
}
</style>
