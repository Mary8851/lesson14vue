<template>
  <h1>Список покупок</h1>
  <div class="wrapper">
    <div class="list">
      <div class="list-item" v-for="(list, index) of lists" :key="index">
        <li @click="deleteTodo(index)">
          {{ list }}
        </li>
      </div>
      <p v-show="lists.length === 0">
        Список пустой. Добавьте, пожалуйста, товар
      </p>
    </div>
    <div class="add-item">
      <input type="text" v-model="input" />
    </div>
    <div class="add-btn">
      <button @click="addItem">Добавить в список покупок</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lists: ["Iphone", "Macbook", "Ipad", "Apple Watch", "iMac"],
      input: "",
    };
  },
  methods: {
    addItem() {
      this.lists.push(this.input);
      this.input = "";
    },
    deleteTodo(index) {
      this.lists.splice(index, 1);
    },
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: #4d244e;
  padding: 30px;
  height: 100vh;
}
h1 {
  font-size: 50px;
  color: #fff;
  text-align: center;
  margin-bottom: 15px;
}
.wrapper {
  margin: auto;
  padding: 20px;
  box-sizing: border-box;
  max-width: 800px;
  width: 100%;
  box-shadow: 0px 0px 10px 0px rgb(254, 252, 252);
}
p {
  text-align: center;
  color: rgb(233, 202, 202);
  font-size: 26px;
}
.list {
  padding: 30px;
  box-shadow: 0px 0px 5px 0px rgb(249, 248, 248);
  &-item {
    margin-bottom: 20px;
    padding: 10px;
    font-size: 20px;
    font-style: italic;
    color: #100404;
    background: #b079b1;
    box-shadow: 0px 0px 5px 0px rgb(249, 248, 248);
  }
  &-item:hover {
    background: #eacdea;
  }
}
.add-item {
  margin: auto;
  text-align: center;
  max-width: 400px;
  width: 100%;
}
input {
  width: 100%;
  height: 35px;
  padding: 10px;
  margin: 30px 0;
  border: none;
  border-radius: 20px;
  box-shadow: 0px 0px 5px 0px rgb(249, 248, 248);
  outline: none;
  font-size: 18px;
}
.add-btn {
  margin: auto;
  text-align: center;
}
button {
  padding: 15px;
  color: #0d033e;
  font-weight: 700;
  cursor: pointer;
  background: #eacdea;
  border: 2px solid rgb(36, 4, 35);
  font-size: 16px;
  border-radius: 15px 50px;
}
button:hover {
  background: rgb(14, 3, 49);
  color: #d97fd9;
  border: none;
  transition: 0.2s;
}
</style>
