<script etup lang="ts">
export default {
data() {
  return {
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
<button @click="increment">{{ count }}</button>
</template>

<style>
.title {
  font-size: 40px;
  font-weight: 200;
  color: red;
}
</style>