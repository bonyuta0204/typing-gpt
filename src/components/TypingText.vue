<template>
  <div class="typing-text" @keydown="handleKeyDown" tabindex="0">
    <div class="japanese-text">
      {{ japaneseText }}
    </div>
    <div class="romaji-text">
      <span
        v-for="(char, index) in romajiText"
        :key="index"
        :class="{ 'typed-char': isCharTyped(index) }"
      >
        {{ char }}
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from "vue";

export default defineComponent({
  name: "TypingText",
  setup() {
    const japaneseText = ref("こんにちは");
    const romajiText = ref("Konnichiwa");
    const currentPosition = ref(0);

    const isCharTyped = (index: number) => {
      return index < currentPosition.value;
    };

    const handleKeyDown = (event: KeyboardEvent) => {
      if (event.key.length === 1) {
        const currentChar = romajiText.value.charAt(currentPosition.value);
        if (event.key.toLowerCase() === currentChar.toLowerCase()) {
          currentPosition.value++;
        }
      }
    };

    onMounted(() => {
      document.querySelector(".typing-text")?.focus();
    });

    return {
      currentPosition,
      japaneseText,
      romajiText,
      isCharTyped,
      handleKeyDown,
    };
  },
});
</script>
<style scoped>
.typing-text {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 24px;
}

.japanese-text {
  margin-bottom: 8px;
}

.romaji-text span {
  transition: color 0.3s ease;
}

.typed-char {
  color: blue;
}
</style>
