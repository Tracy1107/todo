<template>
  <div class="wrap-todos">
    <h1 class="todo-heading">Todo List: Vue.js Example</h1>
    <div>
      <input
        type="text"
        v-model="newTodo"
        placeholder="加入新工作"
        @keyup.enter="add"
        class="new-item"
      />
    </div>
    <ul>
      <todo-item
        v-for="(todo, index) in todoList"
        :key="todo.id"
        :todo_prop="todo"
        :index="index"
        @remove="remove"
      ></todo-item>
      <!-- <li>
        <input type="checkbox" id="ckbx1" v-model="todos[0].isDone">
        <label for="ckbx1" :class="[todos[0].isDone ? 'completed' : '']">{{ todos[0].text }}</label>
        <button class="btn">編輯</button>
        <button class="btn">刪除</button>
      </li>
      <li>
        <input type="checkbox" id="ckbx2" v-model="todos[1].isDone">
        <label for="ckbx2">{{ todos[1].text }}</label>
      </li>
      <li>
        <input type="checkbox" id="ckbx3" v-model="todos[2].isDone">
        <label for="ckbx3">{{ todos[2].text }}</label>
      </li> -->
    </ul>
    <p>{{ todoList }}</p>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import TodoItem from '@/components/TodoItem.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld,
    TodoItem,
  },
  data() {
    return {
      newTodo: '',
      todoList: [
        {
          id: 111111,
          text: '打掃房間',
          isDone: false,
          isEdit: false,
        },
        {
          id: 222222,
          text: '超市買東西',
          isDone: false,
          isEdit: false,
        },
        {
          id: 333333,
          text: '約小美喝咖啡',
          isDone: false,
          isEdit: false,
        },
      ],
      finished: [],
    }
  },
  methods: {
    add() {
      console.log(+new Date())
      this.todoList.push({
        id: +new Date(),
        text: this.newTodo,
        isDone: false,
        isEdit: false,
      })
      this.newTodo = ''
    },
    remove(index) {
      this.todoList.splice(index, 1)
    },
  },
}
</script>

<style scoped>
.wrap-todos {
  width: 600px;
  height: 600px;
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
}
</style>
