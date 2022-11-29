<script setup>
import HeaderComponentNavigation from "../components/HeaderComponentNavigation.vue";
</script>

<template>
  <div class="navigation h-screen w-full absolute">
    <HeaderComponentNavigation/>
  </div>
</template>

<style lang="scss">
.navigation {
    background: var(--vt-c-white);
    clip-path: circle(0.0% at 50% 50%);
    transition: all 0.8s ease-out;
    z-index: 30;

    &.active {
      clip-path: circle(100% at 50% 50%);
      transition: all 0.8s ease-out;
    }
}
</style>
