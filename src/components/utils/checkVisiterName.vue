<script setup>
import { ref, onMounted } from "vue";
import router from "@/router";

const visiterName = ref("");

function checkVisiterName() {
  console.log(router)
  const localStorageUsername = localStorage.getItem("bw_user_name");
  if (localStorageUsername !== null) {
    router.push({ path: "/home" });
  }
}
</script>

<template>
    
</template>

<style lang="scss"></style>