<template>

  <div class="hello">
<<<<<<< HEAD
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
=======

    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org"
        target="_blank"
        rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel"
          target="_blank"
          rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint"
          target="_blank"
          rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org"
          target="_blank"
          rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org"
          target="_blank"
          rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org"
          target="_blank"
          rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs"
          target="_blank"
          rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org"
          target="_blank"
          rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org"
          target="_blank"
          rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org"
          target="_blank"
          rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools"
          target="_blank"
          rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org"
          target="_blank"
          rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue"
          target="_blank"
          rel="noopener">awesome-vue</a></li>
    </ul>
>>>>>>> 897349dca1464cff814f580cd2d2da6caf41b75c
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