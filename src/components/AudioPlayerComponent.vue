<script setup>
import { ref, onMounted } from "vue";

const visiterName = ref("");
const AudioContext = ref(window.AudioContext || window.webkitAudioContext);

function initAudioplayer() {
    console.log(AudioContext);
}
onMounted(() => {
    console.log("asdasdss213")
    initAudioplayer();
});
</script>

<template>
  <div className="bw_audioplayer w-full p-6 px-6 lg:p-6 fixed">
    <div className="bw_artist">Buttons</div>
    <div className="bw_song">Volumne</div>
    <div className="bw_songbar">progressbar</div> <!-- Afterwards implementation-->
    <div className="bw_songbar">Songchoose</div>
  </div>
</template>

<style lang="scss" scoped>
.bw_audioplayer {
  display: grid;
  bottom: 0;
  border-top: 1px solid var(--color-background-soft);
}
</style>

