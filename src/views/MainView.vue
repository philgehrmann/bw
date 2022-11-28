<script setup>
    import { RouterLink, RouterView } from "vue-router";
    import HeaderComponent from "../components/HeaderComponent.vue";
</script>

<template>
    <main className="main__content">
      <HeaderComponent />
      <RouterView />
    </main>
</template>

<style scoped lang="scss">
</style>

