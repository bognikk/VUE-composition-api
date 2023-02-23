<template>
  <section class="container">
    <h2>{{ user.userName }}</h2>
    <h3>{{ user.userAge }}</h3>
  </section>
</template>

<script setup>
// import { ref } from 'vue';
import { reactive } from 'vue';

// const userName = ref('Nikola');
// const userAge = ref(30);

const user = reactive({
  userName: 'Nikola',
  userAge: 30
})

setTimeout(function () {
  // userName.value = 'Bogicevic';
  // userAge.value = 33;
  // user.value.userName = "Bogicevic";
  // user.value.userAge = 33
  user.userName = "Bogicevic";
  user.userAge = 33
}, 2000);

</script>

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
  padding: 1rem;
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  text-align: center;
}
</style>