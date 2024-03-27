<template>
  <!-- <h2>{{ userName }}</h2> -->
  <h2>{{ uName }}</h2>
  <h3>{{ age }}</h3>
</template>

<script setup>
import {
  defineProps,
  computed,
  inject,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from 'vue';

// _________________________  NOTE: inject() __________________________
const age = inject('userAge');

// _________________ COMPOSITION API - LIFECYCLE HOOKS _________________
onBeforeMount(() => {
  console.log('onBeforeMount');
});
onMounted(() => {
  console.log('onMounted');
});
onBeforeUpdate(() => {
  console.log('onBeforeUpdate');
});
onUpdated(() => {
  console.log('onUpdated');
});
onBeforeUnmount(() => {
  console.log('onBeforeUnmount');
});
onUnmounted(() => {
  console.log('onUnmounted');
});
// ______________________________________________________________________

// ________________________ NOTE: defineEmits() ________________________
/*
import { defineEmits } from 'vue'
// define event to emit
const emits = defineEmits([
  'greet'
])

function greetAlert() {
  // emit 'greet' event to parent
  emits('greet')
} 
*/

// ______________________________________________________________________
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
