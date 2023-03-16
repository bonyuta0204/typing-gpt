<template>
  <div id="app">
    <h1>タイピング練習ゲーム</h1>
    <TypingText />
    <ErrorIndicator />
    <ScoreDisplay />
  </div>
</template>


<script lang="ts">
import { defineComponent } from 'vue';
import TypingText from './components/TypingText.vue';
import ErrorIndicator from './components/ErrorIndicator.vue';
import ScoreDisplay from './components/ScoreDisplay.vue';

export default defineComponent({
  name: 'App',
  components: {
    TypingText,
    ErrorIndicator,
    ScoreDisplay,
  },
});
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
