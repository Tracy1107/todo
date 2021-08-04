<template>
  <li>
    <input type="checkbox" v-model="todo.isDone">
    <label :class="[todo.isDone ? 'completed' : '']">{{ todo.text }}</label>
    <button class="btn" @click="remove(index)">刪除</button>
    <button class="btn">編輯</button>
  </li>
</template>

<script>
export default {
  props: [ 'todo_prop', 'index' ],
  data() {
    return {
      todo: this.todo_prop
    }
  },
  methods: {
    remove(index) {
      this.$emit('remove', index)
    }
  }

}
</script>

<style scoped>
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