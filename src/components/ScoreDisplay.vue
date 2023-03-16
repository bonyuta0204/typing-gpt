<template>
  <div class="score-display">
    <p>得点: {{ score }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'ScoreDisplay',
  setup() {
    const score = ref(0); // 仮のスコアデータです。後で親コンポーネントから受け取るように変更できます。

    return {
      score,
    };
  },
});
</script>

<style scoped>
.score-display {
  margin-top: 24px;
  font-size: 18px;
}
</style>

