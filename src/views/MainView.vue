<script setup>
import { ref, reactive } from "vue";
import { RouterLink, RouterView } from "vue-router";
import HeaderComponent from "../components/HeaderComponent.vue";
import NavigationComponent from "../components/NavigationComponent.vue";
import BookingComponent from "../components/BookingComponent.vue";
import ScrollParallax from "vue3-parallax/src/components/ScrollParallax.vue";
import YouTube from "vue3-youtube";

const NavStatus = ref("deactive");

function state(n) {
  NavStatus.value = n;
}
</script>

<template>
  <main className="main__content">
    <NavigationComponent :state="NavStatus" />
    <HeaderComponent @toggleNav="(n) => state(n)" />

    <div className="firstpageFrame container p-6 lg:p-12">
      <div className="firstpageFrame__content">
          <p className="subline">DJ & Producer</p>
          <h1>Benedikt <span className="outline">Warnke</span></h1>

          <div className="firstpageFrame__circleFrame mobile">
            <div className="firstpageFrame__circleFrame-circle">
              <img src="../assets/bene.png" />
            </div>
          </div>

          <p class="max-75">
            Benedikt Warnke is an ambitious DJ & Musicproducer from Germany,
            living in The Netherlands. Always smiling and giving his crowd a
            good and happy time! The style is House music, which clearly is
            going to make you dance all night!Benedikt plays at international
            Night & Beach Clubs in Turkey, Spain, The Netherlands, Germany,
            Maldives, Greece and many more are about to come.
          </p>
          <a class="btn"> Explore my passion</a>
      </div>

      <div className="firstpageFrame__circleFrame desktop">
          <div className="firstpageFrame__circleFrame-circle">
            <img src="../assets/bene.png" />
          </div>
      </div>
    </div>
    <BookingComponent />
  </main>
</template>

<style lang="scss">
.firstpageFrame {
  background: transparent;
  display: grid;
  width: 100%;
  align-items: center;
  justify-items: center;
  grid-template-columns: 76% 23%;
  height: 100vh;
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;

  @keyframes pulse {
    0% {
      width: 0;
      height: 0;
      opacity: 0;
    }
    100% {
      width: 100px;
      height: 100px;
      border: 3px solid transparent;
    }
  }

  @media (max-width: 1024px) {
    grid-template-columns: 1fr;
  }

  .btn {
    padding: 1rem;
    padding-left: 1.5rem;
    padding-right: 1.5rem;
    border-radius: 25px;
    font-size: 1.2rem;
    letter-spacing: 0.1rem;
    text-align: center;
    font-weight: 400;
    cursor: pointer;
    background: linear-gradient(
      90deg,
      rgb(229, 0, 255) 0%,
      rgb(130, 0, 255) 100%
    );
    box-shadow: rgb(103 0 255 / 40%) 0px 10px 60px 0px;

    @media (max-width: 1024px) {
      font-size: 0.8rem;
      padding: 0.8rem;
      padding-left: 1.5rem;
      padding-right: 1.5rem;
      letter-spacing: auto;
      margin-top: 2rem;
    }
  }

  &__content {
    overflow-wrap: normal;
    z-index: 5;
    @media (max-width: 1024px) {
      text-align: center;
    }
  }
  &__circleFrame {
    left: -20px;
    @media (max-width: 1024px) {
      left: 0;
    }
    &.desktop {
      display: block;
      top: 70px;
      @media (max-width: 1024px) {
        display: none;
      }
    }
    &.mobile {
      display: none;
      @media (max-width: 1024px) {
        display: block;
        margin-top: -2rem;
        margin-bottom: 2rem;
        display: grid;

        img {
          width: 100%;
          max-width: none;
          margin-top: 50px;
        }
      }
    }
    .yt_video_bg {
      position: absolute;
      z-index: -1;
      width: 100%;
      height: 100%;
      opacity: 0.2;
    }
    &-circle {
      top: -50px;
      z-index: -1;
      width: 550px;
      height: 550px;
      border-radius: 50%;
      overflow: hidden;
      clip-path: circle(100% at 50% 50%);
    
      background: linear-gradient(
        90deg,
        rgb(229, 0, 255) 0%,
        rgb(130, 0, 255) 100%
      );
      -webkit-box-shadow: rgb(103 0 255 / 40%) 0px 10px 60px 0px;
      box-shadow: rgb(103 0 255 / 40%) 0px 10px 60px 0px;
      background-image:url("../assets/benebooking1.gif");
      background-size:cover;
      background-position:center;
      animation: circleAnim 5s infinite;

      @media (max-width: 1024px) {
        width: 250px;
        height: 250px;
        top: 0;
        align-self: center;
        justify-self: center;
      }

      img {
        width: 110%;
        max-width: none;
        margin-top: 100px;
        z-index:200;
        
      }

      &::after {
        content:"";
        top:0;
        left: 0;
        position: absolute;
        width: 550px;
        height: 550px;
        opacity: 0.5;
        background: linear-gradient(
        90deg,
        rgb(229, 0, 255) 0%,
        rgb(130, 0, 255) 100%
      );
      }
    }
  }

  h1 {
    text-transform: uppercase;
    letter-spacing: 0.1rem;
    font-size: 8.5rem;
    margin-top: -2rem;
    pointer-events: none;
    user-select: none;

    @media (max-width: 1024px) {
      font-size: 2.5rem;
      margin-top: -0.5rem;
    }
  }

  p {
    &.max-75 {
      max-width: 50%;
      margin-bottom: 4rem;
      @media (max-width: 1024px) {
        max-width: 80%;
        margin: 0 auto;
        margin-bottom: 2rem;
        font-size: 0.8rem;
      }
    }
    &.subline {
      font-size: 1.4rem;
      letter-spacing: 0.4rem;
      font-weight: 400;
      margin-top: 0;
      margin-bottom: 0;
      line-height: 33px;
      letter-spacing: 3px;
      color: rgb(229, 0, 255);
      pointer-events: none;
      user-select: none;

      @media (max-width: 1024px) {
        font-size: 0.8rem;
      }
    }
  }
  span {
    &.outline {
      text-transform: uppercase;
      letter-spacing: 0.1rem;
      font-size: 8.5rem;
      color: transparent;
      -webkit-text-stroke: 1px var(--vt-c-white);

      @media (max-width: 1024px) {
        font-size: 2.5rem;
      }
    }
  }
  @keyframes circleAnim {
  50% {box-shadow: 0px 0px 50px    rgba(229, 0, 255, 0.2)}
}
}
</style>
