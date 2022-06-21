<template>
  <section class="container">
    <h2>{{ userName }}</h2>
  </section>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const userName = ref("John");
    setTimeout(() => {
      userName.value = "Ali Haider Nadeem";
    }, 2000);
    return { userName: userName };
  }
};
</script>

<style>
.container {
  background: #f5f5f5;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
