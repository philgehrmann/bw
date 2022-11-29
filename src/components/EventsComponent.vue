<script setup>
import { ref } from "vue";
</script>

<template>
  <div className="bw_events p-6 lg:p-12">
    <div class="content">
      <h1>Bookings</h1>
    </div>
  </div>
</template>

<style lang="scss">
.bw_events {

  .content {
  }
  h1 {
    text-transform: uppercase;
    font-size: 2rem;
    @media (min-width: 1024px) {
      font-size: 7rem;
    }
  }
}
</style>
