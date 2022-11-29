<script setup>
  import { ref, onMounted } from "vue";
  import AudioPlayer from "vue3-audio-player";
  import "vue3-audio-player/dist/style.css";
</script>
<template>
  <AudioPlayer
    :option="{
      src: 'unholy.mp3',
    }"
  />
</template>

<style lang="scss">
.bw_audioplayer {
  display: grid;
  grid-template-columns: 15% 20% 40% 25%;
  bottom: 0;
  border-top: 1px solid var(--color-background-soft);

  audio {
    &::-webkit-media-controls-play-button {
      background-color: white;
      border-radius: 50%;
      color: white;
    }
    &::-webkit-media-controls-panel {
      background: #040404;
      border: 0;
      outline: none;
    }
  }
}
</style>
