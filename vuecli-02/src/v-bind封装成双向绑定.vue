<template>
  <div>
    双向绑定： <input type="text" v-model="msg" />
    <br />
    单项转双向：<input type="text" v-bind:value="val" @input="strFn" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: '',
      val: '',
    };
  },
  methods: {
    strFn(e) {
      this.val = e.target.value;
    },
  },
};
</script>

<style></style>
