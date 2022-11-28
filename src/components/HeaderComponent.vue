<script setup lang="ts">
</script>

<template>
  <div className="header p-6 lg:p-12 grid-cols-2 lg:grid-cols-3">
    <div className="justify-self-start">nav</div>
    <div className="justify-self-end lg:justify-self-center">logos</div>
    <div className="header__socials justify-self-end hidden lg:block grid-cols-4 gap-x-4">
      <a className="svg_icon"><img src="../assets/instagram.svg" /></a>
      <a className="svg_icon"><img src="../assets/spotify.svg" /></a>
      <a className="svg_icon"><img src="../assets/tiktok.svg" /></a>
      <a className="svg_icon"><img src="../assets/youtube.svg" /></a>
    </div>
  </div>
</template>

<style lang="scss">
.header {
  display: grid;
  background: transparent;
  color: var(--color-navigation-text);
  box-sizing: border-box;

  .svg_icon {
    stroke: #fff;
    cursor: pointer;
    img { 
      width: 20px;
      height: 20px;
    }

  }
  &__socials {
    display: grid;
  }
}
</style>
