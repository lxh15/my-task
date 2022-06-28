<template>
  <div>
    <h1>{{ str }}</h1>
    <button @click="btn">翻转</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      str: 'Hello, Vue!',
    };
  },
  methods: {
    btn() {
      this.str = this.str.split('').reverse().join('');
    },
  },
};
</script>

<style></style>
