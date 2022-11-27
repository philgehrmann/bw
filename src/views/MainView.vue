<script setup lang="ts">
    import { RouterLink, RouterView } from "vue-router";
    import HeaderComponent from "../components/HeaderComponent.vue";
    import AudioPlayerComponent from "../components/AudioplayerComponent.vue";
</script>

<template>
    <main className="main__content">
      <HeaderComponent />
      <RouterView />
      <AudioPlayerComponent />
    </main>
</template>

<style scoped lang="scss">
</style>

