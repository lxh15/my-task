<template>
  <div>
    <input type="text" v-model="msg" />
    <br />
    <input type="text" v-model.number="nub" />
    <br />
    <input type="text" v-model.trim="pass" />
    <br />
    <textarea
      name=""
      id=""
      cols="30"
      rows="10"
      v-model.trim.lazy="txt"
    ></textarea>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: '',
      nub: '',
      pass: '',
      txt: '',
    };
  },
};
</script>

<style></style>
