<template>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h2>{{ user.age }}</h2>
    <hr />
    <button @click="changeName">Change Name</button>
    <hr />
    <button @click="changeAge">Change Age</button>
  </section>
</template>

<script>
import { reactive } from "vue";
export default {
  setup() {
    // const userName = ref("John");
    // const age = ref(27);
    const user = reactive({
      name: "Ali",
      age: 27
    });

    function changeAge() {
      user.age = 32;
    }

    const changeName = () => {
      user.name = "Ali Haider Nadeem";
    };

    // setTimeout(() => {
    //   user.name = "Ali Haider Nadeem";
    //   user.age = 28;
    // }, 2000);

    return { user, changeAge, changeName };
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
