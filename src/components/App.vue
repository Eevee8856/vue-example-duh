<template>
  <div id="app">
    <header>
      My app
    </header>
    <main>
      <input v-model="newTodo" type="text" placeholder="Today I need to..." />
      <button v-on:click="addTodo">Add</button>
      <div v-for="item in items">
        <input type="checkbox" :checked="item.done"/>{{item.todo}}  
      </div>
    </main>
    <footer></footer>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      newTodo: null,
      items: [{
        todo: "Eat cake", done: false
      }]
    }
  },
  
  methods: {
    addTodo: function() {
      this.items.push({
        todo: this.newTodo,
        done: false
      })
    }
  }
}
</script>

<style>
  @import "../style/normalize.css";
  
  body {
    margin: 0;
  }
  
  main {
    padding: 1rem;
  }
  
  header {
    padding: 1rem;
    background: whitesmoke;
  }
  
  button {
    padding: .5rem 1rem;
    border: 1px solid #ddd;
    background: transparent;
  }
</style>