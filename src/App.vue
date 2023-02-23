<template>
  <section class="container">
    <h2>{{ userName }}</h2>
  </section>
</template>

<script>
export default {
  data() {
    return {
      userName: 'Nikola',
    };
  },
};
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