<template>
  <div>
    <!-- v-bind的练习 -->
    <a v-bind:href="url">点击去百度</a>
    <br />
    <a :href="url">点击去百度简写</a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      url: 'http://www.baidu.com',
    };
  },
};
</script>

<style></style>
