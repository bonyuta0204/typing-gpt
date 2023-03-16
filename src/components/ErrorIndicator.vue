<template>
  <div class="error-indicator" v-if="hasError">
    誤入力がありました！
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'ErrorIndicator',
  setup() {
    const hasError = ref(false); // 誤入力の有無。後で実際の状態に応じて表示を切り替えられるように変更できます。

    return {
      hasError,
    };
  },
});
</script>

<style scoped>
.error-indicator {
  margin-top: 12px;
  color: #ff0000;
  font-size: 18px;
}
</style>

