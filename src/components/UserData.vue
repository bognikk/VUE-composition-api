<template>
  <h2>{{ fullName }}</h2>
  <h2>{{ userAge }}</h2>
</template>

<script setup>
import { computed, defineProps } from 'vue';
import { inject } from '@vue/runtime-core';

const props = defineProps({
  firstName: String,
  lastName: String,
});

const userAge = inject('age')

const fullName = computed(function () {
  return props.firstName + " " + props.lastName;
});

// context.emit('save-data', 1); // this.$emit('save-datam', 1)

// const emit = defineEmits(['change', 'delete'])

// props: ['firstName', 'lastName', 'age'],
//   computed: {
//   userName() {
//     return this.firstName + " " + this.lastName;
//   }
// }
</script>