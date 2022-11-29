<script setup>
import { ref } from "vue";
let menuActive = ref(false);
</script>

<template>
  <div className="header p-6 lg:p-12 grid-cols-2 lg:grid-cols-3">
    <div className="justify-self-start self-center">
      <div
        @click="menuActive = !menuActive"
        v-bind:class="[
          menuActive
            ? ' header__navbtn-wrapper'
            : 'header__navbtn-wrapper active',
        ]"
      >
        <div className="header__navbtn"></div>
        <span>MENU</span>
      </div>
    </div>
    <div className="justify-self-end lg:justify-self-center header__logo">
      <img src="../assets/benedikt_warnke_logo.png" className="" />
    </div>
    <div
      className="header__socials justify-self-end hidden lg:block grid-cols-4 gap-x-4 self-center"
    >
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
  position: fixed;
  width: 100%;
  background: transparent;
  color: var(--color-navigation-text);
  box-sizing: border-box;
  z-index: 10;

  .svg_icon {
    stroke: #fff;
    cursor: pointer;
    img {
      width: 20px;
      height: 20px;
    }
  }
  &__socials {
    @media (min-width: 1024px) {
      display: grid;
    }
  }
  &__logo {
    width: 100px;

    @media (min-width: 1024px) {
      width: 20%;
    }
  }
  &__navbtn {
    position: absolute;
    z-index: 1;
    width: 30px;
    height: 2px;
    background: var(--color-navigation);

    @media (min-width: 1024px) {
      width: 40px;
    }

    &::after {
      position: absolute;
      content: "";
      width: 30px;
      height: 2px;
      margin-top: -7px;
      background: var(--color-navigation);
      transition: all 0.3s ease;

      @media (min-width: 1024px) {
        width: 40px;
      }
    }

    &::before {
      position: absolute;
      content: "";
      width: 30px;
      height: 2px;
      margin-top: 7px;
      background: var(--color-navigation);
      transition: all 0.3s ease;

      @media (min-width: 1024px) {
        width: 40px;
      }
    }
    &-wrapper {
      display: flex;
      align-items: center;
      width: 50px;
      height: 50px;

      span {
        visibility: hidden;
      }

      &:hover {
        cursor: pointer;

        span {
          position: absolute;
          visibility: visible;
          margin-left: 40px;
          transition: all 0.5s ease;
          transition-delay: 0.4s;
          @media (min-width: 1024px) {
            margin-left: 50px;
          }
        }
        .header__navbtn {
          &::after {
            margin-top: 0;
            transition: all 0.3s ease;
          }
          &::before {
            margin-top: 0;
            transition: all 0.3s ease;
          }
        }
      }
    }
  }
}
</style>
