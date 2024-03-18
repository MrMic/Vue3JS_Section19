<template>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h3>{{ user.age }}</h3>
  </section>
</template>

<!-- ╾────────────────────────────────────────────────────────────────────╼ -->
<script setup>
import { reactive } from 'vue';

// const userName = ref('Maximilian');
// const age = ref(27);
// const uAge = ref(31);
const user = reactive({ name: 'Maximilian', age: 27 });

// console.log(uAge, user);
// console.log(isRef(uAge.value));
// console.log(isRef(uAge));
// console.log(isReactive(user.name), user.age);

setTimeout(() => {
  // userName.value = 'Max';
  // age.value = 32;
  // user.value = { name: 'Max', age: 32 };
  user.name = 'Max';
  user.age = 32;
}, 2000);

// const userRefs = toRefs(user);
// console.log(userRefs);
// console.log(userRefs.name, userRefs.age);
// console.log(userRefs.name.value, userRefs.age.value);

// return { userName: uName, age: uAge };
</script>

<!-- ╾────────────────────────────────────────────────────────────────────╼ -->
<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
