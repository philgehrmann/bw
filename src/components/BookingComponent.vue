<script setup>
import { ref } from "vue";
import ScrollParallax from "vue3-parallax/src/components/ScrollParallax.vue";
</script>

<template>
  <div className="bw_events p-6 lg:p-12">
    <div class="content">
      <h1 className="outline">Bookings</h1>
      <p class="subline"> Upcoming Events & Bookings</p>
      <div className="booking_frame">
        <div className="booking_item">
          <div>
            <p>Upcoming...</p>
            <h2>Robinson Nobilis</h2>
            <p>22.12 - 03.01</p>
          </div>
        </div>
        <div className="booking_item">
          <div>
            <p>Januar 2023</p>
            <h2>Robinson Nobilis</h2>
          </div>
        </div>
        <div className="booking_item">
          <div>
            <p>Februar 2023</p>
            <h2>Robinson Nobilis</h2>
          </div>
        </div>
        <div className="booking_item">
          <div>
            <p>March 2023</p>
            <h2>Robinson Nobilis</h2>
          </div>
        </div>
        <div className="booking_item">
          <div>
            <p>April 2023</p>
            <h2>Robinson Nobilis</h2>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.bw_events {
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;

  .subline {
      font-size: 1.4rem;
      text-align: center;
      letter-spacing: 0.4rem;
      font-weight: 400;
      margin-top:-1rem;
      line-height: 33px;
      letter-spacing: 3px;
      color: rgb(229, 0, 255);
      pointer-events: none;
      user-select: none;
      margin-bottom: 7rem;

      @media (max-width: 1024px) {
        font-size: 0.8rem;
        margin-bottom: 3rem;
      }
    }
  .content {
    h1 {
      text-transform: uppercase;
      letter-spacing: 0.1rem;
      font-size: 8.5rem;
      margin-top: -2rem;
      pointer-events: none;
      user-select: none;
      text-align: center;

      @media (max-width: 1024px) {
        font-size: 2.5rem;
        margin-top: -0.5rem;
      }
   

      &.outline {
        text-transform: uppercase;
        letter-spacing: 0.1rem;
        font-size: 8.5rem;
        color: transparent;
        -webkit-text-stroke: 1px var(--vt-c-white);

        @media (max-width: 1024px) {
          font-size: 2.5rem;
          margin-top: -0.5rem;
        }
      }
    }

    .booking {
      &_frame {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        width: 100%;
        grid-gap: 10px;

        @media (max-width: 1024px) {
          grid-template-columns: 1fr;
        }
      }
      &_item {
        background: transparent;
        height: 295px;
        padding: 2rem;
        display: grid;

        @media (max-width: 1024px) {
          height: 125px;
          border-width: 1px;
        }

        &:hover {
          border-image-slice: 1;
          border-width: 5px;
          border-image-source: linear-gradient(to left, #743ad5, #d53a9d);
          &::after {
            content: "";
            position: absolute;
            background: linear-gradient(
              90deg,
              rgb(229, 0, 255) 0%,
              rgb(130, 0, 255) 100%
            );
            height: 100%;
            width: 100%;
            opacity: 0.2;
          }
        }

        p {
          color: #fff;
        }

        h2 {
          font-size: 1.5rem;
        }
        &:hover {
          cursor: pointer;
        }
        &:first-of-type {
          grid-row: 1 / 4;
          height: 600px;
          justify-items: start;
          align-items: end;
          background-image: url("../assets/bene-nobilis.jpg");
          background-size: cover;
          filter: grayscale(100%);
          transition: all 0.7s ease;
          overflow: hidden;
          position: relative;
          border-image-slice: 1;
          border-width: 2px;
          border-image-source: linear-gradient(to left, #743ad5, #d53a9d);

          @media (max-width: 1024px) {
            height: 300px;
          }

          &:hover {
            background-position: center;
            background-size: cover;
            filter: brightness(50%) grayscale(0);
            transition: all 0.7s ease;
          }
        }
      }
    }

    .bubble {
      top: -75px;
      position: absolute;
      z-index: -1;
      width: 250px;
      height: 250px;
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

      @media (max-width: 1024px) {
        width: 75px;
        height: 75px;
        top: 0;
        align-self: center;
        justify-self: center;
        opacity: 0.2;
      }
    }
  }
}
</style>
