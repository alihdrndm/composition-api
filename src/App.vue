<template>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h2>{{ age }}</h2>
    <hr />
    <button @click="changeAge">Change Age</button>
    <hr />
    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />
  </section>
</template>

<script>
import { ref, computed, watch } from "vue";
export default {
  setup() {
    // const userName = ref("John");
    const age = ref(27);
    const firstName = ref("");
    const lastName = ref("");

    // const user = reactive({
    //   name: "Ali",
    //   age: 27
    // });

    function changeAge() {
      age.value = 32;
    }

    // function setFirstName(ev) {
    //   firstName.value = ev.target.value;
    // }

    // function setLastName(ev) {
    //   lastName.value = ev.target.value;
    // }

    const userName = computed(function () {
      return firstName.value + " " + lastName.value;
    });

    watch([age, userName], function (newValues, oldValues) {
      console.log("oldAge:", oldValues[0]);
      console.log("newAge:", newValues[0]);
      console.log("oldName:", oldValues[1]);
      console.log("newName:", newValues[1]);
    });

    // const changeName = () => {
    //   user.name = "Ali Haider Nadeem";
    // };

    // setTimeout(() => {
    //   user.name = "Ali Haider Nadeem";
    //   user.age = 28;
    // }, 2000);

    return { age, changeAge, firstName, lastName, userName };
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
