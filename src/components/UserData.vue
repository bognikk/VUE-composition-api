<template>
  <h2>{{ uName }}</h2>
  <h2>{{ age }}</h2>
</template>

<script setup>
import { computed, defineProps } from 'vue';

const props = defineProps({
  firstName: String,
  lastName: String,
  age: Number,
})


// props: ['firstName', 'lastName', 'age'],
//   computed: {
//   userName() {
//     return this.firstName + " " + this.lastName;
//   }
// }

const uName = computed(function () {
  return props.firstName + " " + props.lastName;
})


</script>