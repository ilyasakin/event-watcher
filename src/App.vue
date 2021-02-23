<template>
  <div id="app" tabindex="0" ref="main" @keydown="fireEvent">
    <div class="container">
      <div class="page-title">Event Watcher</div>
      <div v-if="Object.values(event).every((value) => value === undefined)">
        Oops, no event fired so far ¯\_(ツ)_/¯
      </div>

      <Box v-if="event.key" title="Key" :text="event.key" />
      <Box v-if="event.code" title="Code" :text="event.code" />
      <Box v-if="event.keyCode" title="Key Code" :text="event.keyCode" />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, reactive } from 'vue';
import Box from './components/Box.vue';
const event = reactive({ key: undefined, code: undefined, keyCode: undefined });

const main = ref(null);

onMounted(() => {
  main.value.focus();
});

const fireEvent = (e) => {
  event.key = e.key;
  event.code = e.code;
  event.keyCode = e.keyCode.toString();
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
}

.container {
  display: flex;
  flex-direction: column;
  min-width: 480px;
  max-width: 480px;

  margin: 0 auto;

  div:not(:first-child) {
    margin-top: 1rem;
  }
}

.page-title {
  font-size: 1.75rem;
  font-weight: 700;
}
</style>
