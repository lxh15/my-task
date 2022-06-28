<template>
  <div @click="father">
    <!-- v-on -->
    <a :href="url" @click.prevent>点击组织默认事件</a>
    <p @click.stop="pFn">阻止冒泡</p>
    <button @click.once.stop="btn">只执行一次</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      url: 'http://www.baidu.com',
    };
  },
  methods: {
    father() {
      console.log('father');
    },
    pFn() {
      console.log('p');
    },
    btn() {
      console.log('button');
    },
  },
};
</script>

<style></style>
