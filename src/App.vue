<template>
  <section class="container">
    <!-- <h3>{{ user.age }}</h3> -->
    <user-data
      :first-name="firstName"
      :last-name="lastName"
      :age="uAge"
    ></user-data>
    <h3>{{ uColor }}</h3>
    <button @click="setAge">Change Age</button>
    <div>
      <input type="text" placeholder="First Name" v-model="firstName" />
      <input type="text" placeholder="Last Name" ref="lastNameInput" />
      <button @click="setLastName">Set Last Name</button>
    </div>
  </section>
</template>

<!-- ══════════════════════════════════════════════════════════════════════ -->
<script setup>
import { ref, computed, watch } from 'vue';
import UserData from './components/UserData.vue';

// const userName = ref('Maximilian');
// const age = ref(27);
// const user = reactive({ name: 'Maximilian', age: 27 }); // NOTE: reactive()
const uAge = ref(31);
const uColor = ref('red'); // NOTE: ref()
const firstName = ref('');
const lastName = ref('');
const lastNameInput = ref(null);

// ______________________________________________________________________
const uName = computed(() => {
  return firstName.value + ' ' + lastName.value;
});

watch([uAge, uName], (newVals, oldVals) => {
  console.log('New age: ', newVals[0]);
  console.log('Old age: ', oldVals[0]);
  console.log('New name: ', newVals[1]);
  console.log('Old name: ', oldVals[1]);
});

// ______________________________________________________________________
const setAge = function SetNewAge() {
  // user.age++;
  uAge.value++;
  uColor.value = 'blue';
};

// ______________________________________________________________________
const setLastName = function SetNewLastName() {
  lastName.value = lastNameInput.value.value;
};

// console.log(uAge, user);
// console.log(isRef(uAge.value));
// console.log(isRef(uAge));
// console.log(isReactive(user.name), user.age);

// const userRefs = toRefs(user);
// console.log(userRefs);
// console.log(userRefs.name, userRefs.age);
// console.log(userRefs.name.value, userRefs.age.value);

// return { userName: uName, age: uAge };

// watch: {
//   age(val) {
//     console.log(val);
//   }
// }
</script>

<!-- ══════════════════════════════════════════════════════════════════════ -->
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
