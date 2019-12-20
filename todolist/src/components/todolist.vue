<template>

  <div class="todolist">
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
    <div class="container mt-4">
      <div class="row justify-content-center">
        <div class="col-5 border-info border p-4 mr-1">
          <h3>Todo</h3>
          <ol class="list-group list-group-flush">
            <li v-for="item in list"
              :key="item.name"
              class="list-group-item text-left">
              <!-- checkbox -->
              <input type="checkbox"
                name="finish"
                :id="item.id"
                v-model="item.finish"
                @check="changelist(key)">
              <label :for="item.id"> {{item.name}}</label>

              <!-- deletebutton -->
              <input type="button"
                value="x"
                @click="del(key)">
            </li>
          </ol>
        </div>
        <!-- done -->
        <div class="col-5 border-info border p-4">
          <h3>Done</h3>
          <ol class="list-group list-group-flush"
            v-if="donelist.name">
            <li v-for="item in donelist"
              :key="item.name"
              class="list-group-item text-left">
              <input type="checkbox"
                name="finish"
                :id="item.id"
                v-model="item.finish">
              {{item.name}}
              <!-- deletebutton -->
              <input type="button"
                value="x"
                @click="del(key)">
            </li>
          </ol>
        </div>
      </div>
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
          id: 1,
          name: "練習vue.js",
          finish: false
        },
        {
          id: 2,
          name: "練習切版",
          finish: false
        }
      ],
      donelist: [
        {
          id: 1,
          name: "",
          finish: true
        }
      ]
    };
  },
  methods: {
    addTodo: function() {
      if (this.newtodo.length > 0) {
        this.list.push({
          name: this.newtodo,
          finish: false
        });
      } else {
        alert("請輸入待辦事項");
      }

      this.newtodo = "";
    },
    del: function(key) {
      this.list.splice(key, 1);
    },
    changelist: function() {
      this.donelist.push({
        name: this.item,
        finish: true
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 0;
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