<template>
  <div class="wrap-todos">
    <h1 class="todo-heading">Todo List: Vue.js Example</h1>
    <div>
      <input type="text" v-model="newTodo" placeholder="加入新工作" @keyup.enter="add" class="new-item">
    </div>
    <ul>
      <li>
        <input type="checkbox" id="ckbx1" v-model="todos[0].isCompleted">
        <label for="ckbx1" :class="[todos[0].isCompleted ? 'completed' : '']">{{ todos[0].text }}</label>
        <button class="btn">編輯</button>
        <button class="btn">刪除</button>
      </li>
      <li>
        <input type="checkbox" id="ckbx2" v-model="todos[1].isCompleted">
        <label for="ckbx2">{{ todos[1].text }}</label>
      </li>
      <li>
        <input type="checkbox" id="ckbx3" v-model="todos[2].isCompleted">
        <label for="ckbx3">{{ todos[2].text }}</label>
      </li>
    </ul>
    <p>{{ todos }}</p>
    
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld,
  },
  data() {
    return {
      newTodo: '',
      todos: [
        {
          id: 0,
          text: '打掃房間',
          isCompleted: false,
          isEdit: false
        },
        {
          id: 1,
          text: '超市買東西',
          isCompleted: false,
          isEdit: false
        },
        {
          id: 2,
          text: '約小美喝咖啡',
          isCompleted: false,
          isEdit: false
        },
      ],
      finished: []
    }
  }
};
</script>

<style scoped>
.wrap-todos {
  width: 600px;
  height: 500px;
  background: rgb(205, 245, 209);
  border-radius: 5px;
  border: 1px solid #ccc;
  margin: auto;
}

.new-item {
  padding: 5px 15px;
  border-radius: 5px;
  font-size: 16px;
}

ul {
  list-style: none;
  text-align: left;
  padding: 20px 100px;
  outline: 1px red solid;
}

li {
  font-size: 16px;
  padding: 10px 20px;
}

.btn {
  float: right;
  margin-right: 6px;
}

.completed {
  text-decoration: line-through;
}
</style>
