<script setup>
import { ref } from "vue";
let menuActive = ref(false);
const emit = defineEmits(["toggleNav"]);
</script>

<template>
  <div className="header-nav p-6 lg:p-12 grid-cols-2 lg:grid-cols-3">
    <div className="justify-self-start self-center">
      <div
        v-bind:class="[
          menuActive
            ? ' header-nav__navbtn-wrapper'
            : 'header-nav__navbtn-wrapper active',
        ]"
      >
        <div className="header-nav__navbtn"></div>
        <span>Close</span>
      </div>
    </div>
    <div className="justify-self-end lg:justify-self-center header-nav__logo">
      <img src="../assets/benedikt_warnke_logo_black-2.png" className="" />
    </div>
    <div
      className="header-nav__socials justify-self-end hidden lg:block grid-cols-6 gap-x-4 self-center"
    >
      <a
        href="https://www.instagram.com/benediktwarnke/"
        target="_blank"
        className="svg_icon"
        ><img src="../assets/instagram-black.svg"
      /></a>
      <a
        href="https://open.spotify.com/artist/28pLFHvEWVVklo6SFocksn?si=vuYWn93MRZCWS2CK3nvvZg"
        target="_blank"
        className="svg_icon"
        ><img src="../assets/spotify-black.svg"
      /></a>
      <a
        href="https://www.tiktok.com/@benedikt_warnke"
        target="_blank"
        className="svg_icon"
        ><img src="../assets/tiktok-black.svg"
      /></a>
      <a
        href="https://www.youtube.com/@benedikt-warnke"
        target="_blank"
        className="svg_icon"
        ><img src="../assets/youtube-black.svg"
      /></a>
      <a
        href="https://www.twitch.tv/the_bboi"
        target="_blank"
        className="svg_icon"
        ><img src="../assets/twitch-black.svg"
      /></a>
      <a
        href="https://soundcloud.com/benediktwarnke"
        target="_blank"
        className="svg_icon"
        ><img src="../assets/soundcloud-black.svg"
      /></a>
    </div>
  </div>
</template>

<style lang="scss">
.header-nav {
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
    @media (min-width: 1024px) {
      display: grid;
    }
  }
  &__logo {
    width: 100px;

    @media (min-width: 1024px) {
      width: 30%;
    }
  }
  &__navbtn {
    position: absolute;
    z-index: 1;
    width: 30px;
    height: 2px;
    background: transparent;
    @media (min-width: 1024px) {
      width: 40px;
    }

    &::after {
      position: absolute;
      content: "";
      width: 30px;
      height: 2px;
      background: var(--vt-c-black);
      transition: all 0.3s ease;
      transform: rotate(45deg);
      @media (min-width: 1024px) {
        width: 40px;
      }
    }

    &::before {
      position: absolute;
      content: "";
      width: 30px;
      height: 2px;
      background: var(--vt-c-black);
      transition: all 0.3s ease;
      transform: rotate(-45deg);

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
        color: var(--vt-c-black);
      }

      &:hover {
        cursor: pointer;

        span {
          position: absolute;
          visibility: visible;
          margin-left: 40px;
          transition: all 0.5s ease;
          transition-delay: 0.4s;
          color: --vt-c-black;

          @media (min-width: 1024px) {
            margin-left: 50px;
          }
        }
        .header-nav__navbtn {
          &::after {
            margin-top: 0;
            transform: rotate(0deg);
            transition: all 0.3s ease;
          }
          &::before {
            margin-top: 0;
            transform: rotate(0deg);
            transition: all 0.3s ease;
          }
        }
      }
    }
  }
}
</style>
