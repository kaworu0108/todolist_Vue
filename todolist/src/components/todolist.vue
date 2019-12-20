<template>
  <div class="hello">
    <h1 class="text-primary">{{ msg }}</h1>
    <div>
      <span>目前清單裡有<span class="text-success">{{list.length}}</span>
        項事情，請新增你的待辦事項</span>
    </div>
    <br>
    <!-- 新增 -->
    <div class="form-inline justify-content-center">

      <div class="form-group mx-sm-3 mb-2">

        <input type="text"
          class="form-control"
          placeholder="請輸入待辦事項"
          v-model="newtodo"
          @keydown.enter="addTodo">
      </div>
      <button type="submit"
        class="btn btn-primary mb-2"
        @click="addTodo">新增</button>
    </div>
    <!-- list -->
    <div class="w-75 m-auto">
      <ol class="list-group list-group-flush">
        <li v-for="item in list"
          :key="item.name"
          class="list-group-item text-left">
          {{item.name}}
          <!-- deletebutton -->
          <input type="button"
            value="x"
            @click="del(key)"
            :id="item.id">
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  name: "todolist",
  props: {
    msg: String
  },
  data() {
    return {
      newtodo: "",
      list: [
        {
          name: "練習vue.js",
          finish: false
        },
        {
          name: "練習切版",
          finish: false
        }
      ]
    };
  },
  methods: {
    addTodo: function() {
      this.list.push({
        name: this.newtodo,
        finish: false
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>