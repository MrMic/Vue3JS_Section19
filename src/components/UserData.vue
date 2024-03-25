<template>
  <!-- <h2>{{ userName }}</h2> -->
  <h2>{{ uName }}</h2>
  <h3>{{ age }}</h3>
</template>

<script setup>
import { defineProps, computed } from 'vue';

const props = defineProps(['firstName', 'lastName', 'age']);

const uName = computed(() => {
  return props.firstName + ' ' + props.lastName;
});
// ______________________________________________________________________
// export default {
//   props: ['firstName', 'lastName', 'age'],
//   // computed: {
//   //   userName() {
//   //     return this.firstName + ' ' + this.lastName;
//   //   },
//   // },
// };
</script>
