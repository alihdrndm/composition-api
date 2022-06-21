<template>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h2>{{ user.age }}</h2>
  </section>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    // const userName = ref("John");
    // const age = ref(27);
    const user = ref({
      name: "Ali",
      age: 27
    });

    setTimeout(() => {
      user.value.name = "Ali Haider Nadeem";
      user.value.age = 28;
    }, 2000);

    return { user };
  }
};
</script>

<style>
.container {
  background: #f5f5f5;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
