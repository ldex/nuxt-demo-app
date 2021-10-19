<template>
  <div>
    <h2>{{ title }}</h2>
    <p>Welcome to our store!</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Nuxt Store',
    };
  },
  data() {
    return {
      title: 'Home Page',
    };
  },
};
</script>

<style></style>
