<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.number="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="gender">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addBtn">添加/修改</button>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item, index) in arr" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.gender }}</td>
          <td>
            <button @click="delBtn(index)">删除</button>
            <button @click="updBtn(item, index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      arr: [
        {
          name: 'Tom',
          age: 19,
          gender: '男',
        },
        {
          name: 'Jone',
          age: 21,
          gender: '女',
        },
        {
          name: 'liy',
          age: 18,
          gender: '男',
        },
      ],
      name: '',
      age: '',
      gender: '男',
      index: '',
      flag: false,
    };
  },
  methods: {
    addBtn() {
      if (this.flag) {
        this.arr[this.index].name = this.name;
        this.arr[this.index].age = this.age;
        this.arr[this.index].gender = this.gender;
      } else {
        if (this.name.trim == '' || this.age == '' || this.gender.trim == '') {
          return alert('请输入正确信息');
        }
        let name = this.name;
        let age = this.age;
        let gender = this.gender;
        this.arr.push({
          name,
          age,
          gender,
        });
      }
      this.name = '';
      this.age = '';
      this.gender = '';
      this.index = '';
      this.flag = false;
    },
    delBtn(index) {
      this.arr = this.arr.filter((v, ind) => ind != index);
    },
    updBtn(item, index) {
      this.name = item.name;
      this.age = item.age;
      this.gender = item.gender;
      this.index = index;
      this.flag = true;
    },
  },
};
</script>
