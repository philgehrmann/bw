<script setup>
import { ref, onMounted } from "vue";
import router from "@/router";

const visiterName = ref("");

function checkVisiterName() {
  const localStorageUsername = localStorage.getItem("bw_user_name");
  if (localStorageUsername !== null) {
    router.push({ path: "/home" });
  }
}

function createVisiterName() {
  const setLocalStorageUser = localStorage.setItem("bw_user_name", visiterName.value);
  console.log(setLocalStorageUser);
  router.push({ path: "/home" });
}
onMounted(() => {
  checkVisiterName();
});
</script>

<template>
  <div
    className="bw_intro h-screen w-full justify-items-center items-center"
  >
    <input
      type="text"
      name="visiterName"
      className="p-6"
      v-model="visiterName"
      maxlength="15"
    />
    <a @click="createVisiterName" className="btn btn-small">Los geht's {{visiterName}}</a>
  </div>
</template>

<style scoped lang="scss">
.bw_intro {
  display: grid;
  background: var(--color-background);
  input {
    border: 0;
    border-bottom: 1px solid var(--vt-c-white);
    background: transparent;
    &:focus {
      border-bottom: 1px solid var(--vt-c-white);
      outline: none;
    }
  }
}
</style>
