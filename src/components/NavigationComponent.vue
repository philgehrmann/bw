<script setup>
import HeaderComponentNavigation from "../components/HeaderComponentNavigation.vue";
import { ref, reactive, computed } from "vue";
const props = defineProps(["state"]);
const NavStatus = reactive(ref('deactive'));

const NavState = computed(() => {
  return props.state;
});
</script>

<template>
  <div>
    <div class="navigation h-screen w-full absolute" :class="NavState">
      <HeaderComponentNavigation @toggleNav="(n) => NavState = n"/>
      <div class="navigation__frame p-6 lg:p-12">
        <h1><a href="">About Me</a></h1>
        <h1><a href="">Bookings</a></h1>
        <h1><a href="">Videos</a></h1>
        <h1><a href="">Spotify</a></h1>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.navigation {
  background: var(--vt-c-white);
  clip-path: circle(0% at 50% 50%);
  transition: all 0.8s ease-out;
  z-index: 30;
  width: 100%;

  &.active {
    clip-path: circle(100% at 50% 50%);
    transition: all 0.8s ease-out;
    width: 100%;
    box-shadow: rgb(103 0 255 / 40%) 0px 10px 60px 0px;
    width: 100%;
  }
  &__frame {
    color: var(--vt-c-black);
    text-align: center;
    
    @media (max-width: 1024px) {
        display: grid;
        align-items: center;
        justify-items: center;
        hight:100vh;
      }

    h1 {
      text-transform: uppercase;
      text-transform: uppercase;
      letter-spacing: 0.1rem;
      font-size: 8.5rem;
      color: transparent;
      -webkit-text-stroke: 1px var(--vt-c-black);

      @media (max-width: 1024px) {
        font-size: 3.5rem;
          }
      &:hover {
        color: rgb(229, 0, 255);
        -webkit-text-stroke: 1px var(--vt-c-black);
        transition: all 0.4s ease;
      }
    }
  }
}
</style>
