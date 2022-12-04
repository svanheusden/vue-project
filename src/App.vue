<script etup lang="ts">
let id=0

export default {
data() {
  return {
    newTodo: '',
    todos: [
      {
        id: id++,
        text: 'Learn Vue 3',
        
      },
      {
        id: id++,
        text: 'Learn Vue Router',
        
      },
    ],
    titleClass: 'title',
    message: 'Welcome to Your Vue.js App',
    count: 0,
    awesome: true,
    text:''
    }
  },
  methods: {
    increment() {
      this.count++
    },
    toggle() {
      this.awesome = !this.awesome
    },
    addTodo() {
      this.todos.push({
        id: id++,
        text: this.newTodo    
      })
      this.newTodo = ''
        },
      removeTodo(todo) {
        this.todos = this.todos.filter((t) => t !== todo)
      }
       }      
      }
    

</script>


<template>
  <button @click="toggle">toggle</button>
<h1 v-if="awesome" :class='titleClass'>{{ message }}</h1>
<h1 v-else>Oh no</h1>
<input v-model="text" placeholder="Type here"/>
<p>{{ text }}</p>


<form @submit.prevent="addTodo">
  <input v-model="newTodo" placeholder="Add a new todo">
  <button type="submit">Add</button>
</form> 

<ul>
  <li v-for="todo in todos" :key="todo.id">
    {{ todo.text }}
    <button @click="removeTodo(todo)">X</button>
  </li>



</ul>



</template>

<style>
.title {
  font-size: 40px;
  font-weight: 200;
  color: red;
}
</style>