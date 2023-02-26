<template>
  <section class="container">
    <h2>{{ uName }}</h2>
    <h3>{{ user.userAge }}</h3>
    <button @click="setNewAge">Change Age</button>
    <div>
      <input type="text" placeholder="First Name" v-model="user.firstName">
      <input type="text" placeholder="Last Name" v-model="user.lastName">
    </div>
  </section>
</template>

<script setup>
// import { ref } from 'vue';
import { reactive, computed, watch } from 'vue';

// const userName = ref('Nikola');
// const userAge = ref(30);

const user = reactive({
  // userName: 'Nikola',
  userAge: 30,
  firstName: '',
  lastName: ''
})

// setTimeout(function () {
//   // userName.value = 'Bogicevic';
//   // userAge.value = 33;
//   // user.value.userName = "Bogicevic";
//   // user.value.userAge = 33
//   user.userName = "Bogicevic";
//   user.userAge = 33;
// }, 2000);

function setNewAge() {
  user.userAge = 33
}

const uName = computed(function () {
  return user.firstName + " " + user.lastName;
})

watch(() => user.userAge, function (newValue, oldValue) {
  console.log('Old age: ' + oldValue);
  console.log('New age: ' + newValue);
});
</script>

<style lang="scss">
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
  background-color: #cee4fc;

  h2 {
    min-height: 28px;
    width: 100%;
    border-radius: 5px;
    background-color: #d3ffeb;
  }

  button,
  a {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    margin-right: 0.5rem;
    border: 1px solid #35495e;
    border-radius: 30px;
    color: #fff;
    font: inherit;
    font-weight: 700;
    text-decoration: none;
    background-color: #35495e;
    cursor: pointer;

    &:hover,
    &:active,
    &:focus {
      color: #35495e;
      border-color: #42b883;
      background-color: #42b883;
      outline-color: #35495e;
    }

    &:focus {
      outline: 2px solid webkit-focus-ring-color;
      outline-offset: -2px;
    }
  }

  input {
    display: block;
    max-width: 100%;
    width: 100%;
    margin: 0.5rem 0;
    padding: 0.5rem;
    border-radius: 5px;
    border: 1px solid #ccc;
    font: inherit;

    &:focus {
      border-color: #42b883;
      background-color: #d3ffeb;
    }

    &:focus-visible {
      outline-color: #42b883 !important;
    }
  }
}
</style>